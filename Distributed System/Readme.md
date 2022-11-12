# Distributed system: The definition

![Distributed System](https://miro.medium.com/max/1100/1*1vYQfOU-iKGzSldPWjnfRA.jpeg)

“Distributed system” or “Distributed computing” is a system made with multiple structures that communicate with each other for their actions so that all of them look like one single coherent system to the end user. A distributed system can have computers, servers, or virtual machines. They are interconnected in a network with individual local memory. For communication, they pass messages to each other.

## How does a distributed system function?

A distributed system has both hardware and software elements. Everything in the system is interconnected — CPUs via the network and processes via the communication system. And, they function as,

1. All the elements involved in the system work towards a common goal and the end user can view the result as one cohesive unit.

2. Each element has its end user. The system communicates within was others and shares resources as well.

## Characteristics of a distributed system

Any distributed system has three main characteristics: -

1. All the elements of the system run concurrently.

2. The global dock doesn’t exist.

3. A failure of one element doesn’t affect the others, i.e., they are independent of each other despite working together.

## Benefits of a distributed system

1. One of the main benefits of the distributed system is `horizontal scalability`. The operations or the computing happens independently on each node which makes it easy to add more nodes or functionality.

2. The system can have hundreds of nodes which makes it fault-tolerant. There are rarely any disruptions if a single element fails. This means that distributed systems are highly `reliable`.

3. There are multiple elements in a distributed system among which the workload can be broken up. Thus, the system becomes very `efficient`.

## Challenges of a distributed system

Some of the common challenges of a distributed system are complex architectural design, construction, and debugging process. But besides them, some others can be overwhelming while creating the system.

1. A distributed system must look for the operations — “Which one to run?”, “When to run?”, and “Where to run?”. The `scheduling` should be effective for a smooth run, but the schedulers have limitations. This results in the under-utilization of hardware and the runtimes might be unpredictable.

2. `Latency` and the size of a distributed system is directly proportional. The larger the distributed system, the more latency experience due to communication issues. In this case, a team can trade between availability, consistency, and latency.

3. Gathering, processing, presenting, and monitoring — all fall under `observing` the operation. However, when the cluster is large, this can lead to a problem since keeping track of the hardware usage metrics might be difficult.

## Types of distributed system

Typically, there are four types of distributed systems.

### 1. Client—Server

In the client-server distributed system, the client approaches the server for data and formats it to display for the end user. Then, the end user makes a change from the client side and commits back to the server where it stays permanent.

### 2. Three-tier

There are three tiers in this system where the client information resides in the middle one. This simplifies application deployment when compared to other methods. We can see this in most web applications these days.

### 3. N-tier

When an application or server needs to forward the requests to additional enterprise services on the network.

### 4. Peer-to-peer

The last kind of distributed system is peer-to-peer where no additional elements exist for services and resource management. All the elements are peers with equal responsibility.

## Conclusion

There are numerous use cases for a distributed system. The most common example of the system would be electronic banking systems and sensor networks. In addition, the multiplayer online game also falls under the category of a distributed system.