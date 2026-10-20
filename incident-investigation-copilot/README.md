# Incident Investigation Copilot

**Tagline:** From production failure to an evidence-based investigation plan.

A Copilot-native starter kit for helping engineers investigate incidents across application, database, infrastructure, and data-pipeline systems. It uses version-controlled instructions, a reusable prompt, synthetic incident evidence, and a lightweight evaluation plan.

## What this prototype does

Given evidence supplied by an engineer, Copilot helps:
- summarize symptoms and known impact;
- build a timeline from supplied timestamps;
- separate observations from hypotheses;
- rank plausible causes with supporting/contradicting evidence;
- recommend specific, preferably read-only diagnostic checks;
- produce a consistent Markdown investigation report.

## What it does not do

- It does not automatically collect logs or query production systems.
- It does not prove root cause from incomplete evidence.
- It does not execute remediation or modify infrastructure.
- It does not replace the incident commander or service owner.

## Repository layout

```text
.github/
  copilot-instructions.md
  prompts/
    investigate-incident.prompt.md
examples/
  spring-boot-db-timeout/
    incident.md
    application.log
    deployment.md
  kubernetes-crashloop/
    incident.md
  airflow-task-failure/
    incident.md
templates/
  incident-report.md
evaluation/
  test-scenarios.md
  results.md
```

## Quick start in VS Code

1. Open this repository as a folder in VS Code.
2. Ensure GitHub Copilot Chat is enabled and your organization permits use of the provided sample data.
3. Open `.github/prompts/investigate-incident.prompt.md` and confirm the prompt-file format is supported by your installed Copilot version.
4. Open one of the incident files and its related evidence files.
5. In Copilot Chat, invoke the `investigate-incident` prompt if available. Otherwise, paste the prompt's instructions into Copilot Chat and ask it to use the repository's Copilot instructions and the example evidence.
6. Ask Copilot to create a report using `templates/incident-report.md` as the format.
7. Validate every finding against the supplied evidence. Keep all production actions under human control.

## Suggested demo

Use `examples/spring-boot-db-timeout/`:
- Read `incident.md`, `application.log`, and `deployment.md`.
- Run the investigation prompt.
- Check whether the result separates observed timeouts from hypotheses.
- Check whether it asks for useful missing evidence instead of inventing a deployment or claiming a confirmed root cause.

Then run the Kubernetes or Airflow scenario.

## Measuring impact

Use `evaluation/test-scenarios.md` and record actual results in `evaluation/results.md`. Compare the manual baseline and Copilot-assisted workflow using the same scenarios. Measure elapsed time, useful checks, important evidence identified, and unsupported claims. Do not present estimates as measured outcomes.

## Safety and privacy

Use sanitized, approved incident data only. Never paste secrets, access tokens, customer personal data, or unapproved production logs into an AI assistant. Redact sensitive values before analysis. Prefer read-only diagnostic steps. Do not execute commands or apply changes merely because the assistant suggested them.

## Adaptation for your organization

Replace the example guidance with approved engineering standards, service-specific runbooks, known monitoring tools, and incident severity definitions. Validate the prompt format and available Copilot features in your organization's environment before the demo.
