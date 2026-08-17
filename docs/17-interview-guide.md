# Technical Interview Guide

This file provides concise talking points for discussing the project in an interview.

## “Was this a real project?”

Yes.

It was a functional commercial Java SDK developed and delivered for PagoExpress. The implementation is not public because the source belongs to the client.

## “Why did you create a public repository without the code?”

To document the engineering work without violating the client's intellectual property.

The repository explains architecture, responsibilities, payment flows, authentication, error handling, testing, security and design decisions using independently written documentation and synthetic diagrams.

## “What problem did the SDK solve?”

It prevented every Java consumer from reimplementing the same payment API integration concerns — authentication, HTTP communication, JSON mapping, payment operations, transaction state and error handling.

## “What was your role?”

I implemented the Java SDK integration deliverable, including API mapping, request/response modeling, authentication, REST/JSON communication, payment operations, error handling, safe logging concerns, sandbox validation and Maven packaging.

## “What technologies did you use?”

The documented stack includes Java 17, Spring Boot, Maven, RestTemplate, Jackson/ObjectMapper, REST and JSON, with authentication using Basic Auth in the authentication flow and token-based protected operations.

## “What made it more complex than calling an endpoint?”

A payment SDK has to deal with authentication lifecycle, multiple payment methods, typed contracts, errors, transaction state, asynchronous updates, cancellation versus reversal, idempotency and sensitive information.

## “Did the Magento/WooCommerce/PrestaShop/Shopify plugins use this exact architecture?”

They are separate deliverables and should not be conflated with the SDK.

Platform-specific integrations can have different runtime and HTTP-client decisions.

## “What would you improve today?”

I would review the SDK against current Java HTTP-client options, stronger contract testing, structured observability, automated compatibility tests, explicit resilience policies and modern secret-management practices while preserving the principle of keeping the remote API behind a stable SDK boundary.

This answer deliberately describes improvement directions rather than claiming that technologies added later were part of the original implementation.
