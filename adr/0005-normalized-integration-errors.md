# ADR-0005: Normalized Integration Errors

## Status

Accepted.

## Context

Remote integrations may fail through HTTP errors, network failures, authentication problems, business rejections, serialization errors or unexpected responses.

## Decision

Normalize failures at the SDK boundary instead of exposing only low-level client/library exceptions.

## Consequences

Consumers gain more meaningful integration semantics, while the SDK assumes responsibility for interpreting and sanitizing remote failure information.
