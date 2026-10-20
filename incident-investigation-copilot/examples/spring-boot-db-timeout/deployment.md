# Deployment information

## Known
- The incident was observed at approximately 10:15.
- The application uses Spring Boot and PostgreSQL.
- HikariCP manages database connections.

## Unknown
- Whether a deployment occurred shortly before the incident.
- Whether database CPU, locks, active sessions, or connection utilization increased.
- Whether traffic increased.
- Whether connection-pool or timeout settings changed.
- Whether other services experienced database problems.

## Instruction
Do not assume a deployment occurred. Recommend evidence needed to determine whether a recent change contributed to the incident.
