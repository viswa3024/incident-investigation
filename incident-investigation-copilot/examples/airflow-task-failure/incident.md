# Incident: Airflow task failure

## Reported symptoms
A scheduled Airflow DAG did not complete successfully because one task failed.

## Supplied evidence
No task log, DAG definition, dependency graph, retry history, upstream data status, or exception details have been supplied.

## Investigation objective
Create a prioritized investigation checklist and identify the minimum additional evidence required. Do not invent an exception or assert a cause.

## Useful next evidence
- DAG ID, run ID, task ID, execution date, and task state
- Task logs and exception traceback
- Upstream/downstream task states
- Retry history and task duration
- Recent DAG, dependency, connection, permission, or input-data changes
