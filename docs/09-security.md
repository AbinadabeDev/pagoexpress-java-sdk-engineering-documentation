# Security Engineering

## Domain sensitivity

Payment integrations manipulate information that can be operationally and financially sensitive.

The SDK therefore requires security considerations even when it does not itself store full payment-system state.

## Credential management

Credentials belong to configuration, not source code.

Expected practices:

- external configuration;
- environment separation;
- no secrets committed to Git;
- no credentials in documentation;
- no real credentials in tests.

## Authentication data

The following must never be logged publicly:

- passwords;
- Basic Auth values;
- access tokens;
- authorization headers;
- API keys.

## Sensitive logging

Integration logs should prioritize operational usefulness without exposing confidential data.

A safe-log strategy should:

- mask secret values;
- avoid dumping complete payment payloads;
- avoid logging authorization headers;
- reduce exposure of personal information;
- preserve enough context for troubleshooting.

## Environment separation

Sandbox and production must be treated as separate environments.

Public examples in this repository are synthetic and are not copied from either environment.

## Webhooks

Inbound asynchronous notifications must not be trusted solely because they reach a known URL.

Webhook handling should consider:

- authenticity/integrity controls available in the contract;
- expected payload validation;
- known transaction correlation;
- idempotent processing;
- duplicate delivery;
- invalid state transitions;
- safe acknowledgement.

## Idempotency

Duplicate processing in payment systems can produce financial side effects.

Idempotency is therefore an architectural concern for operations that can be retried or delivered more than once.

## Public-repository security

This documentation repository follows a stricter rule than a normal code sample:

**if publishing a detail is not necessary to demonstrate engineering ability, and the detail may expose private client information, the detail is omitted.**
