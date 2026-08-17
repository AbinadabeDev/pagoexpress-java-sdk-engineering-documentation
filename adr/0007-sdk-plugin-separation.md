# ADR-0007: SDK and E-commerce Plugins Remain Separate

## Status

Accepted.

## Context

PagoExpress integrations were delivered for multiple environments, including a Java SDK and platform-specific e-commerce integrations.

Those platforms have different runtime, packaging and extension models.

## Decision

Document and treat the Java SDK as an independent artifact rather than presenting it as the internal architecture of every plugin.

## Consequences

The portfolio remains technically accurate and platform-specific decisions can evolve independently.

Later HTTP clients created inside other components are not retroactively attributed to the SDK.
