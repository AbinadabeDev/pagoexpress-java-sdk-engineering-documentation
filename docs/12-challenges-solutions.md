# Engineering Challenges and Solutions

## 1. Converting a remote API into a Java developer experience

### Challenge

A remote payment API naturally exposes HTTP endpoints and JSON documents.

Java consumers should not be required to think in raw HTTP details for every operation.

### Engineering response

The SDK creates a Java-oriented boundary composed of operations and typed integration models.

### Value

Remote integration logic becomes reusable and consistent.

---

## 2. Authentication without duplication

### Challenge

Protected payment operations require authentication context.

Reimplementing that logic in every consumer increases security and maintenance risk.

### Engineering response

Authentication is treated as a centralized integration responsibility.

### Value

Consumers invoke payment capabilities without owning low-level authentication construction.

---

## 3. Handling payment lifecycle rather than only requests

### Challenge

A payment request can return before the final financial state is known.

### Engineering response

The design considers querying, state transitions and asynchronous notifications as part of the same integration domain.

### Value

Consumers are not forced into the false assumption that “HTTP success” equals “payment completed”.

---

## 4. Error semantics

### Challenge

Remote integrations fail for many different reasons.

A timeout is not the same as invalid credentials, and invalid credentials are not the same as a payment business rejection.

### Engineering response

Failures are classified and normalized at the integration boundary.

### Value

Consumers can react according to the actual category of failure.

---

## 5. Multiple payment methods

### Challenge

PIX, boleto and card-related operations do not necessarily share the same lifecycle and data requirements.

### Engineering response

The SDK keeps a consistent integration boundary while preserving payment-method-specific semantics.

### Value

Consumers gain a uniform developer experience without flattening meaningful domain differences.

---

## 6. Sensitive diagnostics

### Challenge

Integration failures require logs, but payments and authentication contain information that should not be exposed.

### Engineering response

The project applied masking/safe-logging concerns and avoided treating raw payload dumping as a normal debugging strategy.

### Value

Operational troubleshooting becomes safer.

---

## 7. Avoiding architecture confusion across deliverables

### Challenge

The PagoExpress ecosystem later included multiple e-commerce plugins and platform-specific HTTP clients.

### Engineering response

The SDK remains documented as an independent artifact.

### Value

The architecture presented here reflects the SDK instead of incorrectly merging later Magento, WooCommerce, PrestaShop or Shopify decisions into it.
