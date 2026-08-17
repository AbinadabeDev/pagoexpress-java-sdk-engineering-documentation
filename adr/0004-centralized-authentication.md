# ADR-0004: Centralized Authentication

## Status

Accepted.

## Context

Protected payment operations require authentication.

Allowing every operation or every consumer to rebuild authentication behavior increases security and maintenance risk.

## Decision

Treat authentication and token lifecycle as centralized integration responsibilities.

## Consequences

Payment capabilities can request valid authentication context without duplicating credential handling.

Authentication failures can also be classified independently from payment business failures.
