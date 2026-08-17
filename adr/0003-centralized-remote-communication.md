# ADR-0003: Centralized Remote Communication

## Status

Accepted.

## Context

If every SDK capability directly manages its own HTTP details, transport behavior becomes duplicated.

## Decision

Keep remote communication as a centralized SDK responsibility.

The documented stack uses REST/HTTP with RestTemplate and JSON mapping with Jackson/ObjectMapper.

## Consequences

Consumers remain isolated from transport details, while the SDK becomes responsible for maintaining that infrastructure consistently.
