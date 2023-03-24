# Rate Limiting

![Rate Limiting](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ZSkLMFoltg1txVnXCyYs3A.jpeg)

We briefly discussed rate limiting in [Endpoint Protection](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Endpoint%20Protection). Let’s see it in detail here.

Rate Limiting is defined as a way that prevents the overflow of frequency of any operations than a defined limit. The main functionality of rate limiting in [distributed systems](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System) is to maintain availability by sharing resources evenly. They even protect the underlying services and resources on large-scale systems, so they function properly. In addition, your API can stay safe from overuse since the number of requests is limited to reach the API in each time gap.

## Algorithms

### 1. Leaky Bucket

It is a simple algorithm that handles rate limiting via a queue by adding the requests at the end of the queue for the first in, first out (FIFO) time interval. In a case where the queue is full, new requests are discarded.

### 2. Token Bucket

This uses the concept of a bucket where a request comes in and the bucket provides a token to process. The request is refreshed occasionally, and if the token expires, you need to request again.

### 3. Fixed Window

There is a window size of n seconds that looks for a fixed window algorithm rate. When a request is made, the window counter is incremented which is discarded in case the counter exceeds the threshold.

### 4. Sliding Log

This tracks the time-stamped logs for each request stored in a time-sorted hash table. The new requests follow calculating the sum of logs that help find out the request rate. When the timestamps lie beyond the threshold, it discards those logs and when the request would exceed the threshold rate, it is held.

### 5. Sliding Window

Further, we have a hybrid approach — a sliding window. It combines the fixed window and sliding log algorithms to bring together the low processing cost and better boundary conditions. We can even counter for each fixed window. Then, we look at the weighted value of the previous window’s request rate based on the current timestamps that smoothen the traffic bursts.

## Advantages

- Denial of Service (DoS) attacks helps prevent resource starvation.
- Rate limiting helps as a defense wall against some attacks.
- Rate limiters can control the flow of data when there are large amounts of processed data.
- Operational costs are controlled with the virtual cap on the auto-scaling of resources. This is vital because if not they are not kept in check, there might be even more exponential bills.
