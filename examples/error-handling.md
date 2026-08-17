# Conceptual Error Handling

Synthetic illustration only:

```java
try {
    PaymentResult result = sdk.payments().create(request);
} catch (AuthenticationFailure ex) {
    // Integration identity could not be established.
} catch (RemoteApiFailure ex) {
    // The remote service rejected or failed the operation.
} catch (ConnectivityFailure ex) {
    // The remote service could not be reached reliably.
} catch (IntegrationFailure ex) {
    // Unexpected integration problem.
}
```

The original implementation is not reproduced here.

The example exists only to demonstrate the principle of separating failure categories at the SDK boundary.
