# Functional Scope

## Scope objective

Expose PagoExpress payment and transaction capabilities to Java consumers through a reusable SDK boundary.

## Capability matrix

| Capability | SDK responsibility |
|---|---|
| Authentication | Establish authenticated context for protected API operations |
| PIX | Support PIX payment-related operations |
| Boleto | Support boleto payment-related operations |
| Card | Support card-related operations present in the original SDK delivery |
| Transaction query | Retrieve and interpret payment/transaction state |
| Capture | Support capture-related transaction behavior where applicable |
| Cancellation | Support eligible cancellation operations |
| Reversal / refund | Support eligible reversal-related operations |
| Payment status | Map and expose transaction state |
| Webhook concerns | Support integration around asynchronous payment notifications |
| Serialization | Convert Java structures to/from remote JSON payloads |
| Error handling | Normalize remote, transport and serialization failures |
| Idempotency | Consider duplicate-sensitive payment operations |
| Logging | Produce useful diagnostics without exposing secrets |
| Sandbox validation | Validate behavior against non-production integration environment |

## Explicitly outside this public repository

The documentation does not disclose:

- private endpoint paths;
- complete request schemas;
- complete response schemas;
- merchant credentials;
- production configuration;
- private status-code contracts;
- proprietary implementation classes.

## Card V2 boundary

A later Card V2 evolution was developed as a separate change for e-commerce integrations.

It must not be presented as though it were automatically part of the original SDK delivery.

This repository therefore documents only the card capability at the level supported by the original SDK project and does not disclose later Card V2 contracts.
