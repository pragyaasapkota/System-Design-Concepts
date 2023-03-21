# Distributed Transactions

![Distributed Transaction](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*mC4Z4yqO3zHiWvnaXz8t9A.jpeg)

Distributed transactions are those operations held over the data across two or more databases. When there are multiple nodes spanning over different databases of the same server that are connected via a single network, distributed transactions can help coordinate the operations over it. These transactions help alter the data on the multiple databases — unlike the [ACID](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Relational%20Database) transactions that happen in a single database. However, the processing of distributed transactions can be complicated since the database must work with the committing or rollback of the changes in a [transaction](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Transactions) as a self-contained unit. In short, the nodes should abort and the [transaction](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Transactions) rolls back giving the operation the name — distributed transactions.

There are two solutions for distributed transactions.

## Two-Phase Commit

The first solution for the complications of the distributed transactions is a two-phase commit where the processes are coordinated to participate in a distributed transaction on whether to commit or abort the operation. Two-phase commit is widely used these days since it even works when there is a temporary system failure. But, it sometimes cannot handle the possible failure configuration and sometimes we might need manual intervention for the outcome.

![Two-Phase Commit](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*5heQ0FxA2CyO3Xwt3jo4Jg.jpeg)

There is a coordinator node in the commit which coordinates the transactions across the nodes. It even tries to form a consensus among the set of processes in the two phases — Prepare Phase and Commit Phase.

#### Prepare Phase

There is a coordinator node in the preparation phase that collects the consensus from each node in the process. If all nodes are prepared, the transactions are processed and aborted if not.

#### Commit Phase

After the coordinator knows the nodes are ready to participate, it asks them to commit to the transaction. If there are any kind of failures, the transactions will then be rolled back.

### Problems with two-phase commit

- The coordinator node can crash.
- Any one of the participant nodes can crash.
- A two-phase commit is a blocking protocol.

## Three-Phase Commit

Three-phase commit extends the two-phase commit by splitting the commit phase into two phases namely the pre-commit and commit phase. The split helps with the blocking problem of the two-phase commit.

![Three-Phase Commit](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ijST1tasK0-VEUpaYFBVig.jpeg)

#### Prepare Phase

The preparation phase of the three-phase commit is like the two-phase commit. There is a coordinator node that collects the consensus from each node to know if they are prepared for the transaction.

#### Pre-commit Phase

This phase has the coordinator issue the pre-commit message that the nodes can acknowledge. In case any node fails to receive the message in time, the transaction is aborted.

#### Commit Phase

Even the commit phase is the same as the two-phase commit — the coordinator asks the nodes to commit to the transaction which if failed, the transaction gets rolled back.

### Why do we need the pre-commit phase?

- If a node is in a pre-commit phase, that means it cleared the first phase meaning that the preparation phase is guaranteed.
- Each phase can have a time-out and avoid indefinite waits.

## Sagas

When there is a sequence of local transactions, we called it a saga. Each of these local transactions updates the database followed by the message/event publishing that triggers the next transaction in the saga.

In case any local transaction fails due to some business rule, saga can execute a series of compensating transactions. They will undo the changes made by the preceding local transactions.

![Sagas](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*kZoD98fiNngo0hPFR49glw.jpeg)

There are two ways a saga can implement.

#### Choreography

In choreography, each of the local transactions publishes domain events. Their trigger other local transactions in the service.

#### Orchestration

Likewise, in the orchestrator, the participants are told what local transactions are to execute.

### Demerits of Saga

- The risk of cyclic dependency between the participants is risky.
- Durability challenges occur due to no data isolation by the participants.
- They are difficult to debug.
- Testing is hard since all services run to simulate a transaction.
