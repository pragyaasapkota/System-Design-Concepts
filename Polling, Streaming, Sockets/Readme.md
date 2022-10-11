In the modern age of continuous updates, push notifications, streaming content and real-time data, it is important to grasp the basic principles that underpin these technologies.  To have data in your application updated regularly or instantly requires the use of one of the two following approaches.



*Polling

    This one is simple. If you look at the wikipedia entry you may find it a bit intense.  So instead take a look at its dictionary meaning, especially in the context of computer science.  Keep that simple fundamental in mind.

Polling is simply having your client check on a server by sending it a network request and asking for updated data.  These requests are typically made at regular intervals like 5 seconds, 15 seconds, 1 minute or any other interval required by your use case.

Polling every few seconds is still not quite the same as real-time, and also comes with the following downsides, especially if you have a million plus simultaneous users:

almost-constant network requests (not great for the client)
almost constant inbound requests (not great for the server loads - 1 million+ requests per second!)
So polling rapidly is not really efficient or performant, and polling is best used in circumstances when small gaps in data updates is not a problem for your application.

For example, if you built an Uber clone, you may have the driver-side app send driver location data every 5 seconds, and your rider-side app poll for the driver's location every 5 seconds.



*Streaming

    Streaming solves the constant polling problem.  If constantly hitting the server is necessary, then it's better to use something called web-sockets.

This is a network communication protocol that is designed to work over TCP. It opens a two-way dedicated channel (socket) between a client and server, kind of like an open hotline between two endpoints.

Unlike the usual TCP/IP communication, these sockets are "long-lived" so that its a single request to the server that opens up this hotline for the two-way transfer of data, rather than multiple separate requests. By long-lived, we meant that the socket connection between the machines will last until either side closes it, or the network drops.

You may remember from our discussion on IP, TCP and HTTP that these operate by sending "packets" of data, for each request-response cycle.  Web-sockets mean that there is a single request-response interaction (not a cycle really if you think about it!) and that opens up the channel through which two-data is sent in a "stream".

The big difference with polling and all "regular" IP based communication is that whereas polling has the client making requests to the server for data at regular intervals ("pulling" data), in streaming, the client is "on standby" waiting for the server to "push" some data its way. The server will send out data when it changes, and the client is always listening for that. Hence, if the data change is constant, then it becomes a "stream", which may be better for what the user needs.  

For example, while using collaborative coding IDEs, when either user types something, it can show up on the other, and this is done via web-sockets because you want to have real-time collaboration.  It would suck if what I typed showed up on your screen after you tried to type the same thing or after 3 minutes of you waiting wondering what I was doing!

Or think of online, multiplayer games - that is a perfect use case for streaming game data between players!

To conclude, the use case determines the choice between polling and streaming.  In general, you want to stream if your data is "real-time", and if it's OK to have a lag (as little as 15 seconds is still a lag) then polling may be a good option. But it all depends on how many simultaneous users you have and whether they expect the data to be instantaneous. A commonly used example of a streaming service is Apache Kafka.
