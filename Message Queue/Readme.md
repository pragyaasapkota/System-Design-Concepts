# Message Queue

![Message Queue](https://miro.medium.com/max/1100/1*efl3v2bZkTRYcBJj9mylUw.jpeg)

If we go by definition, Message Queue is the asynchronous service-to-service communication used in serverless and microservices architecture. In large systems, there are so many microservices running across systems, and the communication between these microservices become difficult. We need a system to communicate our data from one microservice to another microservice. So here comes Message Queue. In our systems the most famous Message Queue we use is Apache Kafka.

So we publish all the messages / data into Apache Kafka. Now, Kafka will automatically notify the consumer and it will receive the data.

A queue is a line of things waiting to be taken care of — in sequential order from the beginning of the line. A Message Queue is a queue of messages sent between applications.

A message is the data delivered between the sender and the receiver application.

# How Message Queue works

- Messages are stored on the queue by Producer until they are processed by Consumer and deleted.
- Each message is proceesed only once, by a single consumer.
- Queues are also used as fault tolerance; In case of any service outage, they can retry the requests

Examples of message queue : Amazon SQS, Apache Kafka, Apache RocketMQ, JORAM, and RabbitMQ.

A messaging queue has several advantages:

- Improved performance
- Reliability
- Scalability
- Easy decoupling
- Rate limiting

# Conclusion

Many producers and consumers use the message queue . Message queues enables different parts of a system to communicate and process asynchronously. A message queue provides a lightweight intermediary which temporarily stores messages. Messages are mostly small, and maybe like requests, replies, error messages, or plain information.
