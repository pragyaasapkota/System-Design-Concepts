# Enterprise Service Bus (ESB)

![ESB](https://miro.medium.com/max/1100/1*s7YuUjTWlhQrIaIq8FnpuA.webp)

Enterprise Service Bus or ESB is one of the architectural patterns where a centralized software element performs integrations between applications. It is responsible for data model transformation, connectivity handling, message routing, communication protocol conversion, and multiple request composition management. All these integrations and made which are followed by transformations of the service interface so that it can be reused by a new application.

Some common examples of ESB are Azure Service Bus, IBM App Connect, Apache Camel, Fuse ESB, etc. Theoretically, a centralized ESB can standardize and simplify communication, messaging, and integration between services across the system. However, in some of the systems, it may be seen as a bottleneck.

## Advantages of ESB

1. Using ESB facilitates developers to upgrade new technologies into one part of an application without disturbing the other parts. As a result, it improves productivity.

2. Since the elements of the system can be scaled independently in the ESB pattern, it is more cost-effective based on [scalability](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Scaling).

3. If an element fails in the system, others are not affected. Each microservice can look for its availability requirements without disrupting the other elements.

## Disadvantages of ESB

1. A single point of failure can hamper communication entirely.

2. Maintenance Complexity

3. High Configuration

4. Since ESB is centrally managed, it makes cross-team collaboration challenging.

5. When you make changes to one integration, it could destabilize others using the same integration.

6. Any update to the ESB impacts the existing integrations which means significant testing is required to perform any update.
