# Business and Technical Context

## Context

PagoExpress operates in the payments domain and exposes capabilities that external systems need to consume through integration interfaces.

Java consumers integrating directly with a payment API need to solve more than simple HTTP connectivity.

They must coordinate:

- authentication;
- credentials;
- request generation;
- JSON schemas;
- response interpretation;
- remote failures;
- payment state;
- synchronous and asynchronous behavior;
- operational logging;
- security;
- environment configuration.

## Repetition problem

Without an SDK, each Java consumer may independently implement code for the same remote operations.

That creates multiple risks:

### Duplicated integration logic

Every application recreates authentication, transport, payload mapping and error handling.

### Contract inconsistency

Different applications can interpret the same remote API differently.

### Maintenance cost

Remote contract changes must be addressed in several systems.

### Security variance

Credential and logging practices can become inconsistent.

### Developer experience

Consumers are forced to understand low-level remote contracts rather than working through Java-oriented abstractions.

## Project response

The Java SDK was created as a dedicated software artifact whose responsibility was to centralize the integration boundary.

This made the remote PagoExpress platform consumable from Java through structured models and operations.

## Separation from e-commerce plugins

The SDK is not the same product as the Magento, WooCommerce, PrestaShop, or Shopify integrations.

The plugins are platform-specific deliverables.

The SDK is an independent Java artifact intended for Java consumers.

This separation is fundamental to the architecture and is preserved throughout this repository.
