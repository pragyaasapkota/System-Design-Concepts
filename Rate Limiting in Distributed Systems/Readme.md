# Rate Limiting in Distributed Systems

![Rate Limiting in Distributed Systems](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*YH6EOXG3vv0a5bRdkecnDQ.jpeg)

Rate limiting is great with [distributed systems](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System) but not without some complications. We already read about [rate limiting](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Rate%20Limiting) and distributed systems before and now we will discuss the problems with them coming together.

### 1. Inconsistencies

When you have a distributed system with [clusters](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Clustering) of multiple nodes, a global rate limit policy is preferred since tracking of rate limit by each node might lead a consumer to exceed the global limit of sending requests to different nodes altogether. This is even riskier when there are even more nodes.

To solve this, we can use sticky sessions in load balancers which will result in each user being sent to exactly one node. However, this means there will be no fault tolerance and more scaling problems. Likewise, we can use a centralized data store like [Redis](https://redis.io/) as well. Then, it has more latency and causes race conditions.

### 2. Race Conditions

Further, race conditions occur when a naïve “get-then-set” approach is used. Under the operation, the current rate limit counter is retrieved, followed by an increment and push to the data store. The issue here is that the new requests can come through in the time it takes to perform a full cycle of read-increment-store, each trying to store the increment counter with an invalid (lower) counter value. This way, the user can send more requests to bypass the rate-limiting controls.

To solve this problem, implementing distributed locking mechanism around the key might be a good way. It prevents other processes from gaining the access to the operations to write on the counter. However, the lock here transforms into a bottleneck and doesn’t scale well.

In addition, you can also use the alternative “set-then-get” approach that increments and checks the counter values quickly without letting the atomic operations get in the way.

## Conclusion

Rate limiting can be a great deal with [distributed systems](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System) if the complications can be handled. However, it might be difficult if those complications increase repeatedly.
