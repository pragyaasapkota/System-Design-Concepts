# Event Sourcing

![Event Sourcing](https://miro.medium.com/max/1100/1*IthY9tNDVBNKVyisQGcSgg.webp)

As a learner, many of us are confused between [Event Driven Architecture](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Event%20Driven%20Architecture) and Event Sourcing. We have already discussed the former here and this article is especially for Event Sourcing.

## What is Event Sourcing?

For the formal definition, we can say that event sourcing is a special arrangement to store data as events in an append-only log. However, it doesn’t limit there but keeps the context of the events as well. It lets you know if and why an invoice was sent from a single data piece. This means that the append-only store is a replacement for storing the current data in a domain. The store is a system of record that can be used to unfold the domain objects.

You can simplify the work in complex domains because, in event-sourcing, there is no need to synchronize the data model and the business model but still have a great improvement in performance, scalability, and responsiveness. To top it off, the system can have transactional data with consistency while the full audit trails are maintained, and the history is open for enabling compensating actions at any time.

## What is different from Event-Driven Architecture?

The [event-driven architecture](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Event%20Driven%20Architecture) uses events to maintain communication within the system where the sections are unaware of each other. Likewise, event sourcing uses the events as a state which is a different approach to storing data. To note, event sourcing is one of the patterns for implementing [EDA](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Event%20Driven%20Architecture) in your system if your use case requires it.

## Advantages of Event Sourcing

- Flexible — can store any kind of message
- Real-time data reporting is well accomplished in event sourcing
- Audit logs for high compliance systems can also be easily achieved
- Fail-safety is good — you can reconstruct data from the event store

## Disadvantages of Event Sourcing

- Each event will have an individual payload
- Requires complex network infrastructure
- Need to have a separate way to control the message formats. E.g., Schema registry.
