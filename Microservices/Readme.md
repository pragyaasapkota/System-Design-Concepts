# Microservices

![Microservices](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*RlAH2DhS-l48WWkUii6ivA.jpeg)

A microservice can be defined as an architecture with a collection of services where each of them is self-contained within itself. They also implement individual business capability within a bounded context — a natural division of business logic with an explicit boundary that includes a bounded context. All services have their separate codebase that can easily be looked at by a small team of developers. The services can be deployed separately and independently while the developers can also update an existing service without redeploying an entire application. This might be a different model than what we had earlier where there was a separate layer to handle the data persistence. In microservices, each service handles its data persistence.

## Characteristics of Microservices

- Services are loosely coupled so it would be easy for independent deployment and scaling. This helps with the decentralization of development teams, so the development and deployment operations are faster. It also results in minimal constraints and operational dependencies.
- Microservices work a charm around business capabilities and priorities.
- Microservices focuses on a single specific problem and can be independent of the underlying architecture.
- The services are easy to maintain and test which saves the re-write operations.
- Resilience and fault tolerance is a priority — the service still works when there are failures or errors.

## Advantages of Microservices

- The services are loosely coupled.
- Each service can be deployed independently.
- Scaling is better since it can be done independently in each service.
- Fault Tolerance is improved.
- Data isolation is better.
- Agile for multiple development teams.
- Long-term commitments are removed.

## Disadvantages of Microservices

- Testing is hard.
- Data integrity
- Maintenance is expensive.
- In the distributed system, complexity is increased.
- Data consistency
- Network Latency
- There are multiple challenges in inter-service communication.
- Network Congestion

## Best Practices of Microservices

- The loosely coupled services with highly functional cohesion.
- The data storage is private to the owner service.
- The API changes are backward compatible.
- Use of [circuit breaker](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Circuit%20Breaker) for fault tolerance.
- Decentralization — each team works for its services. There is no sharing of codes or database schemas.
- The services revolve around the business domain.
- Prevent coupling between services — no shared database schemas or rigid communication protocols.
- Isolation of failures.
- Resilience strategies to avoid failures in the service.
- The communication among the services happens via well-designed APIs — no leaks of implementation details.

## Pitfalls of Microservices

- No idempotency
- No clear ownership
- No business alignment
- Building a distributed system is difficult
- Service boundaries are far from the business domains
- Multiple services with shared database and common dependencies
- Trying [ACID](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Relational%20Database) operations instead of [BASE](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Non-relational-Database)
- If fault tolerance is not included in the design, failures may cascade.

## Service Oriented Architecture (SOA)

The term Service Oriented Architecture (SOA) comes across multiple times over the internet. We might be confused about its similarity with the microservice architecture but in reality — they are different from one another. They are different from their scopes — SOA generates software components reusable via service interfaces to utilize common communication standards and focuses on maximizing application service reusability. At the same time, the microservice architecture makes the collection of multiple small and independent service units work on autonomy and decoupling.

## Are microservices needed?

All the architectures like [monoliths](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Monoliths) and microservices have their merits and demerits. We need to know the requirements to be clear on what kind of architecture we want to implement. For instance, microservice architecture is excellent for solving organizational problems, priorities, teams, and technology while [monoliths](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Monoliths) look for each step of business need required on the application.

Let’s see some conditions you might need to consider if you want to implement a microservice architecture.

- Can the team work effectively on the shared codebase?
- Can microservices deliver clear value to your insight?
- Is the business maturing enough for microservices?
- Are teams blocked on other teams?
- Is the present architecture limited to communication overhead?

It is vital to know that you don’t need to implement microservice architecture unless you want the services to be divided individually. We need to analyze our plan in detail to know if we need microservices. It is not necessary unless you got some complex organizational issues.
