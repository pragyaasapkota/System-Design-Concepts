# Monoliths

![Monoliths](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*AusMzE9rByhpiFGWKjmB3g.jpeg)

Monoliths are self-contained independent applications that are built as a single unit. It doesn’t work just for a single problem but cares for each step of the business need required on the application.

## Modular Monoliths

Further, we have modular monoliths where we build and deploy a single application. It breaks the code into independent modules for each feature required in the system. The good thing about modular monoliths is that it reduces the dependencies of a module since they can improve a particular module without affecting the other.

However, if the modular monoliths are implemented correctly, it helps lessen the complexity that grows as time goes by and the system grows consequently.

## Distributed Monolith

Moving on, there is distributed monolith that resembles the microservice architecture in many ways. But the difference is that the monolithic application is tightly coupled. Choosing microservices over monoliths is better but when we might get the monoliths while we still go for the microservices.

Let’s see some ways we know that our microservice is the distributed monolith.

- Tightly coupled system.
- [Scaling](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Scaling) is difficult.
- Dependency between the services.
- Shares the same resources as the database.
- Low-latency communication is needed.

The main purpose for the use of microservices instead of monoliths is to have [scalability](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Scaling) in a loosely coupled application where every service is independent. With the distributed monolith, the complexity is increased since all the services depend on one another.

## Advantages of monoliths

- Developing is simple and easy.
- Communication is fast and reliable.
- Debugging is easy.
- Easy monitoring and testing.
- [ACID transactions](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Relational%20Database) are supported.

## Disadvantages of monoliths

- If the codebase grows larger, maintenance might be difficult.
- The application redeploys each time there is an update.
- The applications are hard to extend because of the tightly coupled feature.
- It requires a commitment to a particular technology stack.
- A single bug can cause the whole system failure — no reliability.
- Might be a nightmare if we need to scale or adopt new technologies.
