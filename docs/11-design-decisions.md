# Design Decisions

This document summarizes the main public engineering decisions.

Detailed rationale is recorded as ADRs in [`../adr/`](../adr/).

## SDK as a separate artifact

Decision:

Keep the Java SDK as its own deliverable instead of merging its implementation with the e-commerce plugins.

Reason:

Java applications and PHP/e-commerce platforms have different runtime constraints, packaging models and integration architectures.

## Typed integration models

Decision:

Represent remote request/response information through Java models rather than making consumers work with arbitrary JSON structures.

Reason:

Typed models improve clarity, refactoring safety, IDE support and contract visibility.

## Centralized HTTP integration

Decision:

Keep remote communication behind the SDK integration layer.

Reason:

Consumers should depend on payment operations, not on the selected HTTP client or endpoint-construction details.

## Centralized authentication

Decision:

Treat authentication as SDK infrastructure.

Reason:

Credential and token behavior should not be duplicated by every payment operation and every consuming application.

## Error normalization

Decision:

Interpret remote and technical failures through an integration-oriented error boundary.

Reason:

Consumers should not be forced to understand HTTP-client and JSON-library exceptions to determine what happened.

## Explicit asynchronous concern

Decision:

Treat asynchronous payment updates as part of the payment lifecycle.

Reason:

Payment completion can occur after the original HTTP request has returned.

## Security-conscious logs

Decision:

Prefer sanitized operational information over dumping raw requests and responses.

Reason:

Payment and authentication information may be sensitive.
