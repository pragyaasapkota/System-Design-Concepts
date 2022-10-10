# Long Polling

Long polling is a technique used to push information to a client as soon as possible from the server. As a result, the server does not have to wait for the client to send a request.

In Long polling, the server does not close the connection once it receives a request from the client. Instead, the server responds only if any new message is available or a timeout threshold is reached.

Once the client receives a response, it immediately sends a new request to the server to have a new pending connection to send data to the client, and the operation is repeated. With this approach, the server emulates a Realtime Server Push feature.

![Screenshot 2022-10-10 135019](https://user-images.githubusercontent.com/69753609/194824620-fa0bd82d-dcef-4a3e-8c0b-16da4b24dacf.png)

 The steps of Long Polling are:
 * Client(Browser) sends Server and HTTP request for new information
 * Server waits until there’s new information to respond (a “hanging” response)
 * Client repeats the request as soon as it gets the previous response back

Long polling cuts down the number of HTTP requests necessary to transmit the same amount of data to the client. The server has to be able to “hold” unfulfilled client requests, and handle the case where it gets new information to send, but the client hasn’t sent a new request yet.

The benefits of long polling are that it’s part of the HTTP protocol, so it’s widely supported, and it produces less traffic because it takes fewer requests.

There are a few drawbacks to long polling. In some implementations holding unfulfilled requests can take more server resources, and limit the overall number of possible connections. Also if there are multiple open requests from the same client, message ordering can’t be guaranteed, and messages can get lost.

# Conclusion

Long polling is a good strategy when you need a simple implementation for regularly updating clients with new information, like updating a dashboard every minute with new data. It won’t handle high volume data streams, and is still slowed down by the overhead of repeatedly reestablishing a connection between server and client. 

