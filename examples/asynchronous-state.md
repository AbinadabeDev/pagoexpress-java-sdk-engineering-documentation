# Conceptual Asynchronous State Handling

Synthetic illustration:

```text
1. Consumer creates payment through SDK.
2. Remote platform accepts the request.
3. Consumer stores the external transaction correlation.
4. Transaction remains pending.
5. A later query or webhook provides a new state.
6. Consumer validates the transition.
7. Duplicate notifications are treated idempotently.
8. Local state is updated.
```

This illustrates the payment lifecycle concern without reproducing private webhook payloads or endpoint contracts.
