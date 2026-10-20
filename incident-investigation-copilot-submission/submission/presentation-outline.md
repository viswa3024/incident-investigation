# Presentation Outline — 8 Slides

Designed for a short hackathon pitch. Use a clean layout, one idea per slide, and screenshots from your actual working demo. Replace bracketed text with your details.

## Slide 1 — Incident Investigation Copilot
**Subtitle:** From production failure to an evidence-based investigation plan.
- Team: [Team name]
- Event: JHackathon
- One-line value: Turn incident artifacts into a structured, evidence-linked investigation workflow.

**Speaker cue:** “We help engineers organize evidence faster without pretending a hypothesis is a confirmed root cause.”

## Slide 2 — The problem
- Incident context is scattered across logs, deployment notes, and symptom reports.
- Manual correlation takes attention during high-pressure incidents.
- Unverified AI answers can introduce risk.

**Speaker cue:** Emphasize evidence organization and uncertainty—not replacing engineers.

## Slide 3 — The solution
- A reusable Copilot prompt guides the investigation.
- Repository instructions enforce consistent output and safety rules.
- A report template produces timeline, facts, hypotheses, gaps, and checks.

**Speaker cue:** Show a small before/after: raw artifacts → structured report.

## Slide 4 — Architecture
Show the flow:
`Incident files → VS Code + Copilot Chat → repository instructions + investigation prompt → evidence-linked report → engineer review`

Call out: synthetic scenarios, no automatic remediation, human validation.

## Slide 5 — Live demo
- Scenario: Spring Boot / PostgreSQL timeout.
- Inputs: incident description, application log, deployment notes.
- Output: timeline, facts, ranked hypotheses, evidence gaps, read-only checks.

**Speaker cue:** Highlight one source-backed fact and one hypothesis clearly labelled as unconfirmed.

## Slide 6 — Evaluation
Assess each scenario against:
- Evidence accuracy and traceability
- Timeline correctness
- Fact/hypothesis separation
- Actionability and prioritization
- Uncertainty handling
- Safety and report readability

**Results:** [Insert actual observed results. If not measured, say “qualitative prototype evaluation.”]

## Slide 7 — Safety and roadmap
**Safety today:** synthetic/sanitized data, no invented evidence, read-only checks, human-approved actions.

**Next:**
- Better evidence citations and automated checks
- Approved integrations with logs/metrics/traces
- Historical incident benchmark
- Team-specific report templates and access controls

## Slide 8 — Close
**Message:** “Less time organizing incident context; more time validating the next best step.”

**Ask:** Feedback on evidence traceability, useful checks, and what observability source to integrate first.

## Visual guidance
- Use a simple architecture diagram rather than dense paragraphs.
- Keep slide body text to 3–5 bullets.
- Include screenshots only from your actual tool run.
- Do not add fabricated metrics, logos, or claims of production readiness.
