# CQRS

![CQRS](https://miro.medium.com/max/1100/1*7TXSv0r8A5_PV-L-T7GfcQ.webp)

The term CQRS was first explained by Greg Young as “Command and Query Responsibility Segregation”. A formal definition of CQRS would be an architectural pattern to divide each action of the system into commands and queries. A command act as an instruction, a directive to perform a specific task. It is specially designated to change something and doesn’t return a value but only gives an indication of the change — succeeded or failed. Likewise, a query requests information but does not affect the system — no state changes.

CQRS goes on with a theory of separating commands and queries that performs different roles in the system and keeping them separate keeps them optimized which can be a big asset to [distributed systems](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System).

## CQRS with Event Sourcing

We can see CQRS walking alongside the [Event Sourcing](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Event%20Sourcing) pattern where the source of events is the write model and is the official source of information. As per the read model, it materializes the views of the data. These are usually highly [denormalized](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Denormalization) views.

## Advantages of CQRS

- Scaling is easy — can be done independently on read-and-write workloads.

- Effortless architectural changes

- Smooth optimizations

- Loose coupling leads to closer business logic

- Complex joins can be avoided when queries are made

- The system behavior has clear boundaries between them

## Disadvantages of CQRS

- Application design is complex

- System maintenance efforts should be increased

- There is a risk of message failures and duplicate messages

- We might face difficulty while we face eventual consistency

## Use cases of CQRS

There are some use cases where CQRS might be the best option to go for. Let’s see some of them.

- If your system requires better security so that only the right domain entities can perform a write operation on data.

- If the system has the chance to evolve somehow. There can be multiple versions of the model or the business rules change regularly in the system.

- If you are sure to integrate your system with others when working with [event sourcing](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Event%20Sourcing). In this case, the failure of one subsystem has no impact on the availability of others.

- If the data reads performance and data writes performance needs to be adjusted separately.
