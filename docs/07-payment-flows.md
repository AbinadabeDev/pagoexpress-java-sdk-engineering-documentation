# Payment Flows

## Why payment flows require explicit modeling

Payment operations are not equivalent to generic CRUD operations.

A payment may:

- be requested;
- remain pending;
- complete later;
- fail;
- be cancelled while eligible;
- be reversed after processing;
- receive an asynchronous status update.

## Creation flow

```mermaid
sequenceDiagram
    participant App as Java Consumer
    participant SDK as PagoExpress Java SDK
    participant API as PagoExpress API

    App->>SDK: Create payment
    SDK->>SDK: Build typed request
    SDK->>SDK: Resolve authentication
    SDK->>API: REST/JSON payment request
    API-->>SDK: Payment response
    SDK->>SDK: Deserialize + normalize
    SDK-->>App: Typed payment result
```

## Pending state

A successful request does not necessarily mean the payment is financially completed.

The consuming system must preserve the distinction between:

- request accepted;
- transaction pending;
- transaction processed;
- transaction rejected;
- transaction cancelled;
- transaction reversed.

## Query flow

```mermaid
sequenceDiagram
    participant App
    participant SDK
    participant API

    App->>SDK: Query transaction
    SDK->>API: Authenticated query
    API-->>SDK: Current remote state
    SDK-->>App: Typed state/result
```

## Cancellation versus reversal

These are different lifecycle concepts.

### Cancellation

Used when a transaction is still in a state that permits cancellation.

### Reversal

Used when the financial lifecycle requires a compensating operation after processing.

Treating both as the same operation would hide meaningful domain rules.

## Asynchronous update flow

```mermaid
sequenceDiagram
    participant API as PagoExpress
    participant Consumer as Consumer Webhook
    participant App as Consumer Application

    API->>Consumer: Payment notification
    Consumer->>Consumer: Validate / interpret event
    Consumer->>App: Apply idempotent state transition
    Consumer-->>API: Acknowledge receipt
```

The inbound webhook endpoint belongs to the consumer runtime, while the SDK documentation records the asynchronous payment concern as part of the overall integration model.
