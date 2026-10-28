![[Pasted image 20261027155455.png]] 
## 1. What is Event-Driven Architecture (EDA)?

Event-Driven Architecture is a design pattern where services communicate by producing and reacting to events instead of directly calling each other.

An event represents something that has happened, such as `OrderCreated`, `PaymentCompleted`, or `UserRegistered`.

Example: When a user places an order, the system publishes an `OrderCreated` event. Other services react to it independently.

## 2. What is Pub/Sub?

Pub/Sub (Publish/Subscribe) is a messaging pattern used in event-driven systems.

- Publisher: Produces and publishes events.
- Subscriber: Receives events it has subscribed to.
- Message Broker: Routes messages from publishers to subscribers

![[Pasted image 20261027160128.png]]
## 3. How does it work?

1. The Order Service publishes an `OrderCreated` event.
2. The message broker receives the event.
3. The broker delivers it to interested subscribers.
4. The Payment Service processes the payment.
5. The Notification Service sends an order confirmation.

The Order Service does not need to know how these services work.

## 4. Advantages

- Loose coupling: Services don't depend directly on each other.
- Scalability: Subscribers can scale independently.
- Asynchronous processing: The publisher doesn't need to wait for subscribers to finish.
- Extensibility: New subscribers can be added without changing the publisher.

## 5. Pub/Sub vs Direct API Calls

|Pub/Sub|Direct API call|
|---|---|
|Usually asynchronous|Often synchronous|
|One event can reach multiple subscribers|Usually targets a specific service|
|Services are loosely coupled|Caller depends on the called service|
|Good for background tasks|Good for immediate responses|

Important: Pub/Sub does not guarantee that every message will be delivered. Delivery guarantees depend on the broker and its configuration. For example, Redis Pub/Sub is generally at-most-once, while Kafka can retain events for later consumption.

## 6. Common tools

- RabbitMQ: Message broker with queues and routing.
- Apache Kafka: Distributed event streaming platform.
- Redis Pub/Sub: Lightweight real-time messaging.
- AWS SNS + SQS: Managed pub/sub notifications and durable queues.

`Remember: Publisher → Event → Broker → Subscribers.`

![[Pasted image 20261027160904.png]]
