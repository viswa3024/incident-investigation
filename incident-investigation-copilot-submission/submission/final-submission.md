# Final Hackathon Submission

## Project
**Incident Investigation Copilot**

**Tagline:** From production failure to an evidence-based investigation plan.

## Problem
During an incident, engineers must correlate symptoms, application logs, and deployment changes while under time pressure. The context is often scattered, and an AI-generated explanation is unsafe if it does not distinguish observed facts from assumptions.

## Solution
Incident Investigation Copilot is a Copilot-native workflow in VS Code. A reusable prompt and repository-level instructions guide GitHub Copilot Chat through a consistent investigation process. Given an incident description, logs, and deployment notes, it produces a structured Markdown report with a timeline, evidence-backed facts, ranked hypotheses, evidence gaps, and prioritized read-only diagnostic checks.

## How it works
1. The engineer selects a scenario or incident folder.
2. Copilot reads the supplied incident artifacts under repository guidance.
3. The workflow extracts events and constructs a timestamped timeline.
4. It separates confirmed facts from hypotheses and records supporting evidence.
5. It identifies missing evidence and proposes safe checks that can distinguish hypotheses.
6. It creates a report for human review; remediation remains under engineer control.

## Technology
- VS Code and GitHub Copilot Chat
- Repository-level Copilot instructions
- Reusable prompt file
- Markdown report template
- Synthetic scenarios covering Spring Boot/PostgreSQL timeouts, Kubernetes CrashLoopBackOff, and Airflow task failure
- Manual evaluation worksheet

## Differentiation
The prototype is designed around traceability and uncertainty rather than just summarizing logs. It asks for source evidence, labels hypotheses, identifies what is missing, and prefers read-only checks. If evidence is insufficient, the correct output is “Root cause not confirmed.”

## Evaluation plan
Evaluate the same scenarios for evidence accuracy, timeline correctness, fact/hypothesis separation, actionability, evidence-gap handling, safety, and report quality. Record actual observations in the included worksheet. No performance or accuracy gains are claimed without measurements.

## Limitations and next steps
This is a prompt-driven prototype and depends on the quality and completeness of supplied evidence. It does not autonomously query production systems or execute remediation. Next steps include approved observability integrations, stronger automated evaluation, and testing against a larger set of sanitized historical incidents.

## Demo
The six-minute demo uses the Spring Boot/PostgreSQL timeout scenario, then a sparse-evidence Kubernetes scenario to show uncertainty handling. See `demo-script.md` for timing and presenter notes.
