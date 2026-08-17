# API Capabilities

## Documentation policy

This file describes capabilities semantically.

Exact private endpoint paths and proprietary schemas are intentionally omitted.

## Authentication

Purpose:

- authenticate the integration;
- obtain the authorization context required for protected operations;
- keep authentication infrastructure outside the consumer's business code.

## PIX

The SDK supports PIX-related payment integration responsibilities.

From the Java consumer perspective, the important behavior is the payment operation and resulting transaction information, not the construction of the remote HTTP request.

Typical lifecycle:

```text
Payment data
    ↓
SDK PIX operation
    ↓
Authentication
    ↓
REST/JSON request
    ↓
Remote processing
    ↓
Typed Java response
```

## Boleto

The SDK maps boleto-specific payment behavior while preserving the same integration principles:

- typed input;
- centralized authentication;
- centralized remote communication;
- typed output;
- normalized errors.

## Card operations

The original SDK delivery included card-related capabilities from the API contract available for that project version.

The later Card V2 e-commerce evolution is deliberately excluded from this repository.

## Transaction query

Query operations allow consuming systems to retrieve remote transaction/payment state without manually constructing the HTTP contract.

## Capture

Where supported by the original contract, capture-related behavior is represented as a transaction capability rather than exposed as raw HTTP logic.

## Cancellation

Cancellation is a state-sensitive operation.

A correct integration must consider whether the current transaction state is eligible for cancellation instead of assuming that every payment can always be cancelled.

## Reversal / refund-related operations

Reversal behavior is separated conceptually from simple cancellation because a payment that has already been processed has a different lifecycle from a still-pending transaction.

## Webhook-related behavior

Payment state may change after the original creation request.

Webhook integration therefore belongs to the broader transaction lifecycle even when the inbound HTTP endpoint is implemented by the consuming application.

The SDK project treated asynchronous state as an integration concern that consumers must be able to represent and process safely.
