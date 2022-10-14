# Long Polling

Long Polling is the simplest way of maintaining a persistent connection with a server. It essentially holds the request until it has a response to send back. If it doesn't have a response, the connection will simply hang until something gets sent back.

This is a variation of the traditional polling which allows the server to push information to a client whenever the data is available. With Long Polling, the client requests infromation from the server exactly as normal polling, but with the expectation that the server may not respond immediately. That's why the technique is sometimes referred to as a "Hanging GET".

# Long Polling Structure


![Screenshot 2022-10-14 101858](https://user-images.githubusercontent.com/69753609/195764900-388ba99b-0dc5-49b0-81ec-112b5eabc673.png)

Something you might notice is how the browser doesn't repeatedly have to send queries to find the status of it's requests. This is one of the major advantages of Long Polling.

# Advantages
* Easy to implement
* Universal support

# Disadvantages
* Only one directional, any information sent from client to server must be done through a normal HTTP request
* Excess load on server by constantly tearing down HTTP connections and re-establishing them
* Possible race condition of multiple requests from same client receiving messages out of order (two tabs open)

# Conclusion

Each Long Poll request has a timeout. If the traffic is low between client and server, means messages are not sent on a very frequent interval, then Long Polling is a good choice. 

Long polling maybe a good strategy when you need a simple implementation for regularly updating clients with new information, like updating a dashboard every minute with new data.
