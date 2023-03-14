# Message Brokers

![Message Brokers](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*-ecBwUOTylhxwwoAYrvc7w.jpeg)

Message brokers are a system that eases the communication between different applications, systems, and services to exchange information by translating them between formal messaging protocols. With these brokers, the interdependent services can interact even if they are in different languages or are implemented on different platforms. These messages can be validated, stored, routed, or delivered to the designated receiver.

Message brokers are the intermediate medium between various applications where the senders are not aware of the receivers. The message is sent without any knowledge about the receivers or their locations. With this, it decouples the processes and services within the system.

Some of the common examples of message brokers are NATS, Apache Kafka, RabbitMQ, ActiveMQ, etc.

## Models

There are two models of message brokers.

### 1. Point-to-Point Messaging

[Message queues](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Message%20Queue) implement a point-to-point messaging pattern where there is a one-to-one relationship between the one who sends and the one who receives.

### 2. Publish-Subscribe Messaging

There is a producer of each message topic and consumers subscribe to topics to receive the message. This pattern is called the [Publisher-Subscriber](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Messaging%20and%20Pub-Sub) pattern — [pub/sub](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Messaging%20and%20Pub-Sub).

## Message Brokers Vs. Event Streaming

| S.N. | Factors               | Message Brokers                                                     | Event Streaming                                 |
| ---- | --------------------- | ------------------------------------------------------------------- | ----------------------------------------------- |
| 1.   | Messaging Patterns    | Two - Message Queues and Publisher-Subscriber distribution patterns | Only Publisher-Subscriber distribution patterns |
| 2.   | Scalability           | Less Scalable                                                       | More Scalable                                   |
| 3.   | Message Delivery      | Guaranteed                                                          | Not Guaranteed                                  |
| 4.   | Fault Tolerance       | More suited with message queues and pub\sub                         | Message Resending procedure                     |
| 5.   | Message Routing       | Better than event streaming                                         | Limited                                         |
| 6.   | Queuing Capabilitites | Better than event streaming                                         | Limited                                         |

## Message Broker Vs. Enterprise Service Bus (ESB)

| S.N. | Message Broker                                     | [Enterprise Service Bus (ESB)](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Enterprise%20Service%20Bus%20(ESB)>) |
| ---- | -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| 1.   | Comparatively less complex                         | More complex                                                                                                                              |
| 2.   | Integration is easy.                               | Integration is challenging.                                                                                                               |
| 3.   | Maintenance is cost-effective.                     | Maintenance is expensive.                                                                                                                 |
| 4.   | Updating is easy for inter-service communication.  | Updating can be mind-wrecking.                                                                                                            |
| 5.   | Troubleshoot is easy.                              | Difficult to troubleshoot when problems occur in production environments.                                                                 |
| 6.   | More suitable for the microservices architectures. | ESB is falling out of favor.                                                                                                              |
