# Incident: Kubernetes workload restarting

## Reported symptoms
A deployment's pod is repeatedly restarting and its status is shown as `CrashLoopBackOff`.

## Supplied evidence
No pod events, container logs, exit code, resource metrics, or recent deployment details have been provided yet.

## Investigation objective
Explain what `CrashLoopBackOff` indicates, list the most useful read-only evidence to collect, and provide a prioritized diagnostic checklist. Do not claim a specific root cause without logs or events.

## Expected useful next evidence
- Pod description and recent events
- Current and previous container logs
- Container exit code and termination reason
- Readiness/liveness/startup probe configuration
- Resource requests/limits and OOM events
- Image, environment/configuration, and recent change history
