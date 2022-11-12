# Long Polling: A easily implemented concept

![Long polling](https://miro.medium.com/max/720/1*axZpmeilRYSnvXUw-WaYJA.jpeg)

Long polling can be conceptualized as the simplest way to maintain a steady connection between a client with a server. Long polling also holds the request for a period if it has no response to send it back.

HTTP long polling is a traditional polling variant that allows the server to push information to a client whenever the data is available. The clients’ requests data from the server and unlike normal polling, it may not receive the response immediately. HTTP long polling is also known as the “Hanging GET” technique since the client can be left hanging for a long time.

We are familiar with the standard HTTP web request where a client opens a connection and makes a data request which is processed by the server for a response to send back to the client. However, in HTTP Long polling, the server holds the request if there are no updated data to send a response. And when the data is finally available, the complete response is sent, and the client resends the request for the information to the server. This will keep the server ready to send another response whenever the data is updated.

## How does HTTP Long Polling proceed?

1. Clients use regular HTTP to make a request and wait for a response.

2. The server holds the response if there is no data update or has a timeout.

3. When there is an update, the server sends a complete response to the client.

4. The client resends the long poll request either immediately or after an acceptable latency period.

5. Each long-pull request has a timeout, and a client has to periodically reconnect again.

## AJAX Polling

Most of the AJAX apps use Polling as a standard technique where the idea is that the client needs to poll a server repeatedly. The client makes a request and waits for the response and if there is no data available, the server returns an empty response — unlike the traditional HTTP Long Polling. The process can be repeated multiple times — as much as we need it.

The problem with AJAX Polling is that the client needs to repeatedly ask the server for the data, and it leads to numerous responses that create HTTP overhead.

## Web Sockets

Web socket is a network-communication protocol that was specially designed to work over Transmission Control Protocol (TCP). The sockets open in a two-way channel — client and server. This creates a hotline between them leading to two endpoints.

It has a different mechanism as compared to TCP/IP communication because instead of multiple separate requests, there is a single request with the two-way transfer of data. And the most important leverage to have with the web sockets is that the connection lasts until either client or the server closes it or if the network drops.

The web socket provides a full-duplex communication channel over a single TCP connection. Once the connection is made, both the client and server can exchange the data. The sockets also provide a protocol where the communication happens with lower overheads, facilitating real-time data transfer from and to the server.

## Server-Sent Events (SSEs)

The next stop is Sever Sent Events (SSEs), a connection where a client establishes a steady and long-term connection with the server. Then, the server uses the connection to send the data. Please note, that the client can’t send data to the server and would require a separate technology if required. A client just uses regular HTTP to make requests and wait for a response.

SSEs are the best options when the server generates the data in a loop and sends multiple events to the clients and if we need real-time traffic from the server to the client.

## Advantages of Long Polling

1. Easy Implementation

2. Universal Support

3. The browser doesn’t have to send queries repeatedly to find the status of its requests.

## Disadvantages of Long Polling

1. This is one-directional. The data transfer from the client to the server can happen via normal HTTP requests only.

2. The server has to bear an excessive load.

3. There is a probable race condition of multiple requests from the same client receiving messages out of order (two tabs open)

## Conclusion
Long Polling is a good idea when a simple implementation for regularly updating clients with new information like updating a dashboard every minute with new data. There might be challenges like when the client needs to use a medium other than normal HTTP web request, there are Web Sockets on the rescue.