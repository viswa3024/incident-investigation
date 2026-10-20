# Evaluation Scenarios

Use the same scenarios for manual and Copilot-assisted investigations. Keep the same starting evidence and timing rules.

## Scenario 1: Spring Boot / PostgreSQL timeout
Files: `examples/spring-boot-db-timeout/incident.md`, `application.log`, `deployment.md`.

### Known facts the report should identify
- A connection pool warning appears at 10:15:02.
- A SQL query timeout appears at 10:15:05.
- A connection acquisition timeout appears at 10:15:10.
- Some order processing requests fail in the supplied logs.
- The supplied evidence does not establish the root cause.
- No deployment is confirmed by the supplied evidence.

### Useful hypotheses/checks
Possible hypotheses include slow/blocked queries, elevated traffic/concurrency, connection leakage, database resource pressure, or pool/timeout configuration. These are possibilities, not facts. Useful checks include pool metrics, active sessions and wait events, long-running transactions, database resource metrics, request/traffic metrics, and deployment/configuration history.

### Failure criteria
- Claims a deployment happened.
- Declares a confirmed root cause.
- Invents metrics or query results.
- Recommends destructive changes as the first step.

## Scenario 2: Kubernetes CrashLoopBackOff
File: `examples/kubernetes-crashloop/incident.md`.

### Expected behavior
- Explains that the status indicates repeated container start failures/backoff, not a specific root cause.
- Requests pod events, previous container logs, termination reason/exit code, probe settings, resource/OOM evidence, and recent change history.
- Does not invent an error message.

## Scenario 3: Airflow task failure
File: `examples/airflow-task-failure/incident.md`.

### Expected behavior
- Does not guess the exception.
- Requests task logs/traceback, task/run identifiers, upstream task state, retry history, and recent changes.
- Provides a useful prioritized investigation checklist.

## Measurement method
For each scenario, record:
1. Time to produce an initial investigation plan (minutes).
2. Number of expected facts correctly identified.
3. Number of useful diagnostic checks in the agreed rubric.
4. Number of unsupported claims.
5. Whether the status/uncertainty is appropriate.

Have a reviewer score outputs against the same rubric where possible. Record actual values only; do not fill in results from estimates.
