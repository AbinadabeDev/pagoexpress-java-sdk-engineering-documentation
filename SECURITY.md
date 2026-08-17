# Security Policy

## Purpose

This repository contains public documentation only. It does not contain the proprietary SDK implementation or production configuration.

## Sensitive information

Do not commit:

- passwords;
- API keys;
- access tokens;
- refresh tokens;
- authorization headers;
- private certificates;
- production URLs;
- internal network information;
- customer data;
- transaction data;
- private PagoExpress API documents;
- source code copied from the client project.

## Examples

All examples must use fictional values.

Examples should use values such as:

```text
example-token
merchant-example
transaction-example
customer@example.invalid
```

Never use sanitized-looking values copied from real production data. Replace them entirely with synthetic data.

## Logs

Any logs added as evidence must be recreated or sanitized and must not expose:

- credentials;
- tokens;
- personal information;
- payment information;
- headers;
- internal paths;
- private endpoints.

## Vulnerability reporting

This repository is not the source distribution of the production SDK and therefore cannot receive or patch vulnerabilities in the proprietary implementation.

Potential security issues involving PagoExpress production systems or private software must be reported through the client's official security/support channels rather than through this portfolio repository.
