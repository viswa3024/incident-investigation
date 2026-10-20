# Incident: Order API latency and database timeouts

## Service
Order Processing API

## Stack
Java, Spring Boot, PostgreSQL, HikariCP

## Reported symptoms
At approximately 10:15, the Order API experienced increased latency. Some order requests failed. Application logs contain a SQL query timeout and a database connection acquisition timeout.

## Known impact
Some order requests failed according to the supplied logs. The total number of affected requests, customer impact, and incident duration are unknown.

## Evidence files
- `application.log`
- `deployment.md`

## Investigation objective
Identify the observed facts, construct a timeline, rank plausible explanations, and recommend diagnostic checks. Do not assume that the connection pool is the root cause simply because connection timeouts appear.
