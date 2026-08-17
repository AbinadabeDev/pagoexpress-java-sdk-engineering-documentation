# ADR-0001: SDK as an Independent Deliverable

## Status

Accepted.

## Context

Multiple Java consumers may need to integrate with the same PagoExpress payment capabilities.

Embedding the complete remote integration separately in each consumer would duplicate authentication, HTTP, JSON, error handling and payment logic.

## Decision

Implement the PagoExpress Java integration as a dedicated reusable SDK artifact.

## Alternatives considered

### Direct integration inside every application

Simpler initially, but duplicates integration behavior and creates inconsistent maintenance.

### Platform-specific integration only

Useful for e-commerce platforms, but not a reusable solution for arbitrary Java consumers.

### Dedicated SDK

Creates a shared Java boundary for the payment contract.

## Consequences

### Positive

- reusable integration;
- centralized remote contract knowledge;
- consistent authentication;
- consistent error handling;
- reduced duplication.

### Trade-offs

- SDK versions must evolve as the remote contract evolves;
- consumers depend on the SDK release lifecycle;
- compatibility must be managed explicitly.
