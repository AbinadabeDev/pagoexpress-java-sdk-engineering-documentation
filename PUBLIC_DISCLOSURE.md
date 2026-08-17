# Public Disclosure Policy

This policy defines what may and may not be published in this repository.

The goal is to document the engineering work accurately without disclosing client-owned or confidential information.

## Disclosure matrix

| Information | Public status |
|---|---|
| High-level project purpose | Allowed |
| Commercial-project classification | Allowed |
| My engineering responsibilities | Allowed |
| General technology stack | Allowed |
| High-level architecture | Allowed |
| Generic payment lifecycle | Allowed |
| Generic authentication lifecycle | Allowed |
| Generic testing strategy | Allowed |
| Generic security practices | Allowed |
| Independently written ADRs | Allowed |
| Synthetic pseudocode | Allowed |
| Sanitized diagrams | Allowed |
| Lessons learned | Allowed |
| Client source code | Prohibited |
| Private repository files | Prohibited |
| Exact private package hierarchy | Prohibited |
| Proprietary class implementations | Prohibited |
| Private Swagger/OpenAPI | Prohibited |
| Unpublished endpoint paths | Prohibited |
| Exact proprietary request/response payloads | Prohibited |
| Production URLs | Prohibited |
| Internal IP addresses | Prohibited |
| Credentials / API keys | Prohibited |
| Authentication tokens | Prohibited |
| Authorization headers | Prohibited |
| Real customer data | Prohibited |
| Real transaction identifiers | Prohibited |
| Database dumps | Prohibited |
| Confidential CI/CD information | Prohibited |
| Internal client conversations | Prohibited |
| Contracts and commercial values | Prohibited |
| Unapproved screenshots | Prohibited |

## Endpoint policy

The original project maps concrete PagoExpress API operations.

This public repository documents those operations semantically — for example, “create PIX payment”, “query transaction”, “cancel pending payment”, and “request reversal” — without publishing private endpoint paths unless those paths are already officially public and explicitly safe to reproduce.

## Source-code policy

No original source file should be copied into this repository.

Renaming classes, changing identifiers, deleting comments, or making superficial modifications does **not** make proprietary code safe for publication.

Examples included here must be independently written and synthetic.

## Screenshot policy

Before adding a screenshot, verify that it does not contain:

- repository URLs;
- usernames that should remain private;
- branch names that expose internal information;
- tokens;
- API keys;
- headers;
- customer identifiers;
- transaction identifiers;
- production domains;
- IP addresses;
- private file paths;
- private endpoint paths;
- internal tickets;
- confidential messages.

When in doubt, do not publish the screenshot.

## Pre-publication rule

Every new document, image, diagram, or example must pass the checklist in:

[`evidence/publication-checklist.md`](evidence/publication-checklist.md)
