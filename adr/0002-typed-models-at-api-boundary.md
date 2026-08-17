# ADR-0002: Typed Models at the API Boundary

## Status

Accepted.

## Context

Remote payment operations exchange structured JSON data.

Using unstructured maps throughout consumer code would reduce compile-time safety and make the integration contract harder to understand.

## Decision

Represent integration requests and responses using typed Java models/DTOs.

## Alternatives considered

- raw JSON strings;
- generic maps;
- typed DTOs.

## Rationale

Typed models provide explicit contracts, IDE support, safer refactoring and clearer validation boundaries.

## Consequences

The SDK contains more mapping structures and those structures must evolve when the remote contract changes.
