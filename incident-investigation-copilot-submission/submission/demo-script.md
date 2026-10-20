# Six-Minute Demo Script

## Demo goal
Show that Incident Investigation Copilot converts a small set of incident artifacts into a structured investigation plan, and that it communicates uncertainty instead of inventing a root cause.

## Preparation checklist
- Open the repository in VS Code.
- Confirm Copilot Chat is signed in and the prompt is available.
- Open `examples/spring-boot-db-timeout/incident.md`, `application.log`, and `deployment.md`.
- Keep `templates/incident-report.md` available.
- Have `examples/kubernetes-crashloop/incident.md` ready for the uncertainty segment.
- Use only synthetic or sanitized evidence.
- If slash-command invocation fails, use the fallback below.

## Timed run of show

### 0:00–0:45 — Problem
**Say:** “During an incident, engineers lose time piecing together logs, deployment notes, and symptoms. A language model can help, but a confident answer without evidence is risky. This project focuses on a traceable investigation plan, not an automatic declaration of root cause.”

**Show:** repository tree and the sample incident files.

### 0:45–1:30 — Architecture
**Say:** “The workflow is native to VS Code and GitHub Copilot. Repository instructions define safety and evidence rules; a reusable prompt guides the investigation; synthetic scenarios make the demo repeatable; and a Markdown template standardizes the output.”

**Show:** `.github/copilot-instructions.md`, `.github/prompts/investigate-incident.prompt.md`, and `templates/incident-report.md`.

### 1:30–3:30 — Main investigation
In Copilot Chat, try:

`/investigate-incident examples/spring-boot-db-timeout`

Ask it to read `incident.md`, `application.log`, and `deployment.md` and fill the report template. Require:
- a timestamped timeline;
- confirmed facts with source references;
- ranked hypotheses with supporting and conflicting evidence;
- evidence gaps;
- five prioritized, read-only diagnostic checks;
- explicit root-cause status.

**Say while reviewing:** “I’m checking whether each factual claim is grounded in a file, whether the timeline follows the timestamps, and whether the assistant separates observed facts from its explanations.”

### 3:30–4:30 — Uncertainty test
Open `examples/kubernetes-crashloop/incident.md` and ask Copilot to investigate only from the supplied evidence.

**Prompt:** “Use only the available incident evidence. List confirmed facts, plausible hypotheses, and the evidence needed to distinguish them. If the root cause is not proven, say so. Do not invent missing logs or run remediation.”

**Say:** “A useful incident assistant must be able to say what it does not know. Here, we evaluate whether it names missing evidence and recommends checks instead of presenting a guess as fact.”

### 4:30–5:30 — Evaluation
Open `evaluation/test-scenarios.md` and `evaluation/results.md` if present, or the included `evaluation/results-template.md`.

**Say:** “We evaluate evidence traceability, timeline correctness, fact-versus-hypothesis separation, actionability, uncertainty, safety, and report quality. These are manual observations for this prototype; we will not claim accuracy or time savings that we have not measured.”

Show one actual observation from your run. Do not invent a score.

### 5:30–6:00 — Close
**Say:** “Incident Investigation Copilot does not replace the on-call engineer. It reduces the friction of organizing evidence into a repeatable investigation plan, while keeping uncertainty visible and remediation under human control. The next step is to connect approved observability sources and evaluate against a larger set of historical, sanitized incidents.”

## Slash-command fallback
Slash-command discovery and folder arguments vary by Copilot version. If the command does not run:
1. Open `.github/prompts/investigate-incident.prompt.md`.
2. Copy its instructions into Copilot Chat.
3. Explicitly ask Copilot to read the three files under `examples/spring-boot-db-timeout/`.
4. Ask it to use `templates/incident-report.md` as the output structure.

## Presenter guardrails
- Do not claim a root cause unless the evidence supports it.
- Do not claim metrics or improvements unless you measured them.
- Do not expose real credentials, customer data, or internal production logs.
- If Copilot makes an unsupported claim, point it out and show how the evidence rules should catch it. This can strengthen the demo if handled honestly.
