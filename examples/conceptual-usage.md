# Conceptual SDK Usage

The following pseudocode illustrates the intended developer experience of an SDK like the one documented here.

It is not copied from the proprietary implementation.

```java
PaymentSdk sdk = PaymentSdk.configure(
        IntegrationCredentials.fromEnvironment()
);

PaymentRequest request = PaymentRequest.builder()
        .amount(exampleAmount)
        .customer(exampleCustomer)
        .build();

PaymentResult result = sdk.payments()
        .createPix(request);

if (result.isPending()) {
    // Persist the external transaction reference and wait for
    // a later query or asynchronous state update.
}
```

The important architectural point is the boundary:

```text
consumer code
    ↓
payment-oriented Java API
    ↓
authentication / HTTP / JSON / errors
    ↓
remote payment service
```
