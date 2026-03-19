```mermaid
sequenceDiagram
actor Customer
participant UI as Order UI
participant Service as Order Service
participant Payment as Payment Service

Customer->>UI: submitOrder()
activate UI

UI->>Service: createOrder()
activate Service

Service->>Payment: validatePayment()
activate Payment

Payment-->>Service: ok
deactivate Payment

Service-->>UI: orderConfirmed()
deactivate Service

UI-->>Customer: confirmation
deactivate UI
```
