# Polling and Streaming

![Polling and Streaming](https://miro.medium.com/max/1100/1*-5Rr2eFkxUgXEtWwqTy9Lw.jpeg)

The internet is growing day by day. Its content is doubled every six months which means there are continuous updates, push notifications, streaming content, and real-time data for us to look at. These operations are carried out by either “Polling” or “Streaming” approaches. Using these technologies can have your application updated regularly or instantly.

## Polling

We have heard of polling in our daily life where it means recording the opinion or vote. The second meaning of the term is to check the status of maybe a device — especially as a part of a repeated cycle.

In the computing world, Polling means having your client check on the server by sending the server a network request. The operation is also followed by the client asking the server for the updated data. These types of requests are made in regular intervals with fixed times — 10 seconds, 20 seconds, 30 seconds, or 1 minute — depending on the prerequisites of your use case. However, having polling with a minimum second interval doesn’t mean it comes close to real-time.

When you have simultaneous users exceeding the number of million, some inconvenience can occur for both client and server.

1. For servers, the loads can be overwhelming with more than a million requests per second. This problem can be addressed as almost-constant network requests.

2. For clients, the almost-constant network requests are a problem.

As we now have an idea that polling with a low interval is less efficient and thus should be used when the small gaps in the data updates will not be a problem for your application. For example, in in-driver, the driver-side app sends the location data every 5 seconds, and the rider-side app polls for the data.

## Streaming

Since polling was less efficient and a little problematic — STREAMING comes to the rescue.

When you need to make network requests to the server in a minimum time interval, we can use “web sockets”.

```
Web socket is a network-communication protocol.
It was specially designed to work over Transmission Control Protocol (TCP).
The sockets open in a two-way channel — client and server.
This creates a hotline between them leading to two endpoints.
It has a different mechanism as compared to TCP/IP communication.
Because instead of multiple separate requests, there is a single request.
It is equipped with the two-way transfer of data.
And the most important leverage to have with the web sockets is that the connection lasts until either client or the server closes
it or if the network drops.
```

We discussed IP, TCP, and HTTP when we looked for [Network Protocols](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Network%20Protocols). We talked about the packets of data for each request-response cycle. However, the web sockets work for a single request-response interaction and open a channel for the data stream. A common example to look for streaming services is Apache Kafka.

## Difference between polling and streaming

In polling, clients make requests to the server by creating a pull to get the data. This happens a regular intervals. Likewise, in streaming, the client can be on standby while the server pushes the data to them. The server is streaming and sends the data every time it changes in any way. The term streaming was given because when the data change is constant, and the server sends the data every time it changes — creates a stream.

For a better understanding, think of online multiplayer video games. If the data is not synced within milliseconds of the change, the game lags, and thus gamers face huge losses.

## Conclusion

Choosing between polling and streaming is your choice which you need to determine by analyzing your use case. If it’s okay for you to have a little lag and don’t care about the real-time sync of data — go for polling but if you need your real-time data — go for streaming. However, all of this depends on your users and the use case.
