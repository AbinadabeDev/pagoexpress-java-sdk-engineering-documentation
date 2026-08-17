# Technology Stack

## Core documented stack

### Java 17

Primary implementation language for the SDK delivery.

### Spring Boot

Used within the Java ecosystem of the SDK delivery.

### Maven

Responsible for build and dependency management and for preparing the Java artifact for consumption.

### REST / HTTP

Communication model used with the PagoExpress remote service.

### JSON

Payload representation used by the integration.

### RestTemplate

HTTP client technology documented for the integration stack.

### Jackson / ObjectMapper

JSON serialization and deserialization technology.

### Basic Auth + token-based authenticated operations

Authentication stack used to establish the authorization context required by payment operations.

## Integration concepts

The project also required knowledge of:

- DTO modeling;
- request/response mapping;
- API client design;
- authentication lifecycle;
- exception design;
- payment state;
- idempotency;
- webhooks;
- secure logging;
- sandbox testing.

## Delivery ecosystem

GitHub Actions and Docker were used in the broader delivery/validation ecosystem documented for the project.

They are not presented as business capabilities of the SDK.

## Technologies deliberately excluded from this SDK page

The following may exist in other PagoExpress projects but should not be attributed to this SDK unless independently verified for the SDK itself:

- Magento-specific technologies;
- WooCommerce / WordPress APIs;
- PrestaShop APIs;
- Shopify application architecture;
- Redis;
- RabbitMQ;
- OpenSearch;
- PHP/Composer plugin internals;
- later platform-specific PagoExpress API clients.
