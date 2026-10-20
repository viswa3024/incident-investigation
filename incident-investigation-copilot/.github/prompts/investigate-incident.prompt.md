
---
name: investigate-incident
description: Read incident evidence from the workspace and generate an evidence-based investigation report.
agent: agent
---

# Incident Investigation

The user's message contains the incident directory path.

Example:
`/investigate-incident examples/spring-boot-db-timeout`

## Mandatory procedure

1. Resolve the supplied path relative to the current workspace root.
2. Use available workspace tools to list the directory and recursively discover its files.
3. If workspace tools cannot list files, use the terminal to verify the workspace root and directory.
4. Read these files when present:
   - `incident.md`
   - `application.log`
   - `deployment.md`
5. Read any other relevant text files discovered in the incident directory.
6. If a path is not found, verify the workspace root before concluding that the files are missing.
7. Never invent file contents or claim to have read files that were not accessible.
8. If the folder cannot be accessed, explain the exact path and access failure. Do not generate a fabricated investigation.

## Analyze the evidence

Separate observed facts from hypotheses.

- Build a timestamped timeline from the actual logs.
- Identify the observed symptoms and known impact.
- Consider database query latency, connection-pool exhaustion, database availability, and recent deployment changes only where relevant.
- For each hypothesis, give supporting evidence, missing or contradicting evidence, confidence, and a diagnostic check.
- Do not claim a confirmed root cause without sufficient evidence.
- Use `UNKNOWN` when the incident state cannot be established from available evidence.

## Generate the report

Read `templates/incident-report.md` and follow its structure.

Create or update `results.md` inside the supplied incident directory.

Include:
- Status
- Summary and impact
- Timeline
- Evidence with source file paths
- Ranked root-cause hypotheses
- Recommended diagnostic checks
- Missing evidence
- Files actually inspected

Preserve source evidence. Do not modify application logs, deployment records, or incident metadata.

Use available file-writing tools to save the report. Confirm success only after the write operation succeeds.

## Final response

Report the resulting status, strongest evidence, likely causes, and the path to the generated report. Explicitly state any access or write failures.
