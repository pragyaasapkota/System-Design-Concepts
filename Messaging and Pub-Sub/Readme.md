# Messaging and Pub/Sub

![Messaging](https://miro.medium.com/max/720/1*961yqzyZNWnjV-LoKBU3jg.jpeg)

We need to design all kinds of systems as system designers. This includes small easy systems and large distributed systems. It’s easy to make a small system that runs cohesively and smoothly but when it is large and distributed, sometimes we need to make an extra effort for good maintenance. This is done through adequate communication between the components and the services included in the system. However, this is done with networks with the same weakness as them. And as we are quite aware that network fails are very frequent and unpredictable as well.

Whenever your network fails, the components of the system can’t communicate with each other leading to system failure. This is the main reason why a distributed system needs a robust mechanism — to make sure the communication continues even if the network fails or can also pick up from where it was led down.

Let’s see an example: -

Imagine you found a movie ticket at a decent price and confirm the booking. You used your credit card for the payment and all the procedures have been completed. You are waiting in your inbox to receive the PDF of your ticket, but it’s been hours and it hasn’t yet been received.

You wonder why? Well, in simple words, this happened because the system had a momentary failure which either wasn’t handled properly, or recovery was not done. Generally, a booking system has a connection with the movie hall and pricing APIs that handle the time, price, and similar things. These operations happen when you click through the site’s booking UI. But it needn’t send you the ticket PDF until your payment is confirmed.

After your payment, the API assures you that the ticket will be sent to your inbox in a few moments. As a user, we all have experienced this while booking tickets online — the booking and ticket received don’t always be simultaneous but sometimes — asynchronous. Such a system has a messaging system that assures the PDF is sent to your inbox after your payment is done and the booking is confirmed. These PDFs are auto-generated. If there is a case where the messaging system fails, the email service has no way of knowing about the booking you did for the movie and thus, no ticket will be generated.

## Publisher / Subscriber Messaging

![Pub / Sub](https://miro.medium.com/max/720/1*R3mDIjiajAE55cTFVPXViA.jpeg)

Mostly addressed as Pub/Sub in the general world, Publisher / Subscriber is a common model for messaging. The concept behind the model is that there are two parties in the system — a publisher who publishes a message and a subscriber who subscribes to the message. The most interesting feature of the Pub / Sub messaging is that a subscriber can subscribe to a particular topic only. These topics are dedicated channels where each of the channels handles the message of a particular topic. As a subscriber, you can choose the topic for you and subscribe so that you will only receive the message related to that topic.

In the Pub / Sub system, the publisher and subscriber don’t know about each other and are completely de-coupled. This phenomenon works when the publisher announces a message and the subscriber is listening for the topic they subscribed and if the announced message is from the topic, the subscriber checks it out. Typically, a publisher is a server with channels of different topics which is to be chosen by the consumer or user — maybe another server or a browser or something similar. Since there is no interaction between a subscriber and a publisher — the messages are just data and can be in any form that you need it in. This means that there are four parts in a Pub / Sub messaging: -

1. Publisher

2. Subscriber

3. Topics

4. Messages

## Why use it instead of a database?

We have the option to save the data in the database and access it directly.

But why not do so?

The reason why we can’t do what I just mentioned is that you need a system to queue up the messages. Each message corresponds to a task that needs to be done based on the message’s data.

Let’s look at the movie ticket booking example again.

If 50 people book the ticket in 1 hour, you need to add all those 50 people to the database, and it will not solve the problem of having to email every one of them but will only store the 50 transactions.

Then Pub / Sub comes to the rescue.

They handle the communication and sequence the task while the messages reside in the database. This ensures that the system has the “at least once” feature delivery feature alongside others like persistent storage, ordering of messages, “try-again”, “re-playability” of messages, etc. In the case where there is only a database, you have no way of knowing that the message has been sent after the confirmation was done.

There can be times when the same messages are delivered more than once because the network was down for a moment and the publisher didn’t know the subscriber has consumed the message. Hence, the publisher will re-send the message. This falls under the feature “at least once”.

Now we also know why “once and only once” doesn’t work — in distributed systems, network failures are very frequent and almost unavoidable. There are complications here because the message can trigger an operation on the subscriber side that can change the state of the database. But what if a single operation is repeated a few times where each time it is repeated — the state changes?

## Controlling Outcomes

The problem mentioned above has an easy solution — Idempotency. According to stack-overflow,

`In computing, an idempotent operation has no additional effect if it is called more than once with the same input parameters.'

This means that even when a subscriber processes a message more than once, the overall state of the application on the database stays the same — as it was after the message was processed the first time.

Getting back to our Movie tickets example.

After you entered your credit card details and click on the Pay button a few times, you don’t want to pay the money every time you clicked the button. But since the system was slow, you did click it a few times and now are scared that the payment would be made multiple times. This issue is looked over by Idempotency which makes sure that the system processes the first click and then stops.

To understand this more clearly, think of the ‘applaud’ action in medium — a single person can offer hundreds of applaud but it only increases the number of applaud, not to be one and only applaud. Idempotency was not needed here but was in the movie ticket system.

The messaging model in your system depends on your use case. They are usually referred to as ‘event-based’ architecture and the popular services you can use are Apache Kafka, RabbitMQ, Google Cloud Pub / Sub, and AWS SNS / SQS.

![RabbitMQ](https://miro.medium.com/max/720/1*k1WShD1Zh49sBYw3E5kkkQ.jpeg)