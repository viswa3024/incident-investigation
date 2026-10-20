# Incident Investigation Copilot — Hackathon Submission Pack

**Tagline:** From production failure to an evidence-based investigation plan.

This pack contains a submission-ready architecture document, a timed demo script, a presentation outline, an evaluation worksheet, and a final submission summary. Replace bracketed placeholders with your team's details and record only evaluation results you actually observe.

## Project concept
Incident Investigation Copilot is a Copilot-native workflow for helping an engineer investigate an incident using the incident description, application logs, and deployment notes already in the repository. It produces a structured investigation report with a timeline, confirmed facts, ranked hypotheses, evidence gaps, and safe diagnostic checks.

## Suggested live invocation
Try the prompt in VS Code Copilot Chat:

`/investigate-incident examples/spring-boot-db-timeout`

Slash-command discovery and passing folder arguments depend on the GitHub Copilot version and setup. If this does not work, open `.github/prompts/investigate-incident.prompt.md`, copy its instructions into Copilot Chat, and explicitly ask Copilot to read the three files in `examples/spring-boot-db-timeout/`.

## Before presenting
- Verify the prompt works in the environment you will demo.
- Use synthetic or sanitized evidence only.
- Do not claim measured time savings or accuracy improvements unless you measured them.
- Make clear that hypotheses are not confirmed root causes.
- Keep all production actions human-approved; the demo should recommend read-only checks, not execute changes.

## Pack contents
- `submission/architecture.md` — architecture, flow, components, safety boundaries.
- `submission/demo-script.md` — six-minute walkthrough with speaker notes and prompts.
- `submission/presentation-outline.md` — eight-slide deck content and presenter cues.
- `submission/final-submission.md` — concise written project submission.
- `evaluation/results-template.md` — worksheet to record real test results.









incident-investigation-copilot/
├── .github/
│   ├── copilot-instructions.md
│   └── prompts/
│       └── investigate-incident.prompt.md
├── examples/
│   ├── spring-boot-db-timeout/
│   │   ├── incident.md
│   │   ├── application.log
│   │   └── deployment.md
│   ├── kubernetes-crashloop/
│   │   └── incident.md
│   └── airflow-task-failure/
│       └── incident.md
├── templates/
│   └── incident-report.md
├── evaluation/
│   ├── test-scenarios.md
│   └── results.md
├── submission/
│   ├── architecture.md
│   └── demo-script.md
└── README.md


```

incident-investigation-copilot/
├── .github/
│   ├── copilot-instructions.md
│   └── prompts/
│       └── investigate-incident.prompt.md
├── examples/
│   ├── spring-boot-db-timeout/
│   │   ├── incident.md
│   │   ├── application.log
│   │   └── deployment.md
│   ├── kubernetes-crashloop/
│   │   └── incident.md
│   └── airflow-task-failure/
│       └── incident.md
├── templates/
│   └── incident-report.md
├── evaluation/
│   ├── test-scenarios.md
│   └── results.md
├── submission/
│   ├── architecture.md
│   └── demo-script.md
└── README.md
```


/investigate-incident examples/spring-boot-db-timeout
