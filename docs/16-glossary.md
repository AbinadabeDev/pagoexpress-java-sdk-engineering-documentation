# Glossary

## API

Application Programming Interface. In this project, the remote PagoExpress integration interface consumed by the SDK.

## SDK

Software Development Kit. The Java artifact that exposes reusable PagoExpress integration capabilities to Java consumers.

## DTO

Data Transfer Object. A typed structure used to carry integration request/response data between layers or systems.

## REST

Architectural style used for the remote HTTP integration.

## JSON

Data representation used in request and response payloads.

## Authentication context

The credentials/token information required for protected remote operations.

## PIX

Brazilian instant-payment method supported by the integration.

## Boleto

Brazilian bank-slip payment method supported by the integration.

## Capture

A payment lifecycle action associated with completing/confirming an authorized transaction where supported.

## Cancellation

Operation that terminates an eligible transaction before it reaches a state where reversal is required.

## Reversal

Compensating financial action applied after an eligible transaction has progressed beyond simple cancellation.

## Webhook

Asynchronous notification sent by the payment platform to a consumer endpoint when relevant events occur.

## Idempotency

Property that helps ensure repeated delivery/retry of an operation does not create unintended duplicate effects.

## Sandbox

Non-production environment used to validate integrations safely.

## ADR

Architecture Decision Record. A document that records the context, decision and consequences of an engineering choice.
