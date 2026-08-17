# ADR-0006: Synchronous and Asynchronous Payment Concerns

## Status

Accepted.

## Context

Payment creation can return before the final transaction state is known.

Later status changes may arrive asynchronously.

## Decision

Treat synchronous request/response behavior and asynchronous transaction updates as parts of the same payment lifecycle.

## Consequences

Consumers are encouraged to distinguish “request accepted” from “payment completed” and to implement safe state transitions for later notifications.
