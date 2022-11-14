# Event-Driven Architecture

![EDA](https://miro.medium.com/max/720/1*OwYTBsS6J8VBY3Y9lKMLOg.jpeg)

Event-Driven Architecture or EDA is defined as an architectural pattern that uses events to maintain communication within a system. It leverages a message broken to publish and consume events asynchronously. Both producers and consumers are unaware of each other. In simple words, Event Driven Architecture is a method by which we can achieve loose coupling between services within the system.

## Events: Definition

An event is a data point to represent state changes in a system. Whenever a consumer makes a change, an event is formed. However, there is no specification as to what and how the state change should happen.

## Components of Event-Driven Architecture (EDA)

The Event-Driven Architecture has three components under it. Let’s see them individually.

1. **Event Producers**: They produce an event for the router.

2. **Event Routers**: The event routers filter and push the events produced by producers to the consumers.

3. **Events Consumers**: They consumers events to reflect the state changes in the system.

## Patterns of Event-Driven Architecture (EDA)

There are numerous ways for implementing EDA in your system depending upon your use case. Let’s see some of them:

- Sagas

- [Publish-Subscribe](https://github.com/aygarp-modsiw/System-Design-Concepts/tree/master/Messaging%20and%20Pub-Sub)

- Event Sourcing

- Common and Query Responsibility Segregation (CQRS)

## Advantages of Event-Driven Architecture (EDA)

- Producers and Consumers are unaware of each other.

- The system becomes highly scalable and distributed.

- Agility is improved.

- Guaranteed delivery

- Adding new consumers is easy.

## Challenges of Event-Driven Architecture (EDA)

- Error Handling is difficult.

- The system integrated with EDA is complex in general.

- Exactly once, in-order processing of events.

## Conclusion

Where the way of Event-Driven Architecture depends on the use case, there are various use cases like Metadata and Metrics, Server and Security Logs, Integrating heterogenous systems, Fanout and parallel processing, etc. In addition, we can check out some of the examples of the architecture in NATs, Apache Kafka, Amazon EventBridge, Amazon SNS, Google PubSub, etc.