---
name: investigate-incident
description: Analyze supplied incident evidence and create an evidence-based investigation report.
agent: ask
---

Investigate the incident using the evidence the user identifies or files available in the current workspace. Follow `.github/copilot-instructions.md` and use `templates/incident-report.md` as the report structure.

Do not assume you can access live logs, dashboards, deployment systems, or production infrastructure. Analyze only evidence actually provided or available in the workspace.

## Workflow

1. **Summarize:** State the affected component, observed symptoms, known impact, and what is unknown.
2. **Timeline:** Extract events in timestamp order. Preserve the source of each event and call out missing timezone or clock information.
3. **Evidence:** List the most relevant log lines, stack traces, code, configuration, or deployment facts. Quote only the minimum necessary.
4. **Hypotheses:** Rank plausible explanations. For each, state:
   - hypothesis;
   - supporting evidence;
   - contradicting evidence or evidence not yet available;
   - confidence (low, medium, or high) with a reason;
   - the next check that would confirm or reject it.
5. **Diagnostics:** Suggest targeted checks that distinguish between hypotheses. Prefer read-only commands or queries, and explain what the results would mean. Do not invent results.
6. **Mitigation and remediation:** Separate immediate mitigation from permanent correction. Include risks and validation steps. Do not recommend a change as certain when the cause is unconfirmed.
7. **Missing evidence:** Prioritize the smallest set of missing facts likely to reduce uncertainty.
8. **Report:** Create a concise report using `templates/incident-report.md`.

## Technology-specific guidance

Apply only what fits the incident:
- **Spring Boot / Java:** inspect exception chains, request latency, thread pools, connection-pool metrics, timeouts, dependency health, and recent changes when evidence supports it.
- **Python:** inspect tracebacks, dependency errors, retries, resource exhaustion, and relevant runtime/configuration.
- **PostgreSQL:** consider active sessions, long-running transactions, locks/waits, query plans, connection usage, and resource metrics. Do not assert a database issue without evidence.
- **Kubernetes:** consider pod events, previous container logs, restart counts, probes, resource limits, image/config changes, and scheduling events.
- **Docker:** consider container exit status, startup logs, health checks, resource constraints, and configuration.
- **Terraform:** review relevant plan/configuration changes and provider errors. Never apply changes as part of the investigation.
- **Airflow:** inspect task state, task logs, dependencies, retries, schedules, and upstream inputs.
- **Dataflow / BigQuery:** consider job/task errors, schema changes, data volume, query/job metadata, permissions, and data-quality checks.
- **React:** distinguish browser/client errors from API failures; check console/network evidence and recent frontend changes.

## Required discipline

- Do not treat correlation as causation.
- Do not infer that a deployment occurred unless evidence says so.
- If the evidence is insufficient, conclude **Undetermined** and state the next best checks.
- Do not execute commands or modify production systems.
