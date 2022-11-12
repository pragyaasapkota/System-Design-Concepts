# Endpoint Protection

![Endpoint Protection](https://miro.medium.com/max/1100/1*8PYrC54b8FBf3HfIkq_JMA.jpeg)

For large systems, sometimes we can have many unnecessary operations that are not so vital for the system. In this case, you want to protect your system. This phenomenon is called endpoint protection.

Think of the time you clicked a button multiple times because the system wasn’t working, and you wanted to make it more responsive. Now, what will happen if the server tries to process each of the clicks? It would make the system even slower. HOW?? Here is an answer — the server can’t ignore the click once it has been made and must process each one of them which thus makes the response even slower.

## Rate Limiting

Endpoint protection is not always about protecting the system but also limiting the operations to have it maintained. For example, imagine a third-party API service that limits your operation to 25 per hour of intervals. If you exceed the limit, then the server will stop processing your requests.

The process limits the rate of your operations for a given time interval and is called rate-limiting. Once the limit exceeds the time, the server returns an error for the new operations until the new window is started. It can be implemented on users, request times, payloads, and other relevant things.

The concept of rate-limiting in endpoint protection sounds like the users are getting restricted from getting the maximum out of the endpoint during the operations. This is true and can be looked at it this way but when the client is malicious — this is the way to prevent your system from these kinds of clients. The malicious clients bomb the server with requests and take down the server. In an easy short term, this is called a Denial of Service (DoS) attack.
However, the Rate of limiting can’t handle it when the attack comes from multiple clients. There is no way of knowing that the requests are related and are being sent by a single malicious agent. This is called distributed Denial of Service attack. Hence, if you want to protect your system from these types of coordinated distributed attacks, use other methods are recommended.

Rate limiting can be used in less complicated use cases. The server first checks the limit conditions and enforces them if needed. That means you need to figure out the data structure and database to make the operations fast for the requests within the limit. You also need to make sure that each request reaches the server so that the limitation will be enforced. To handle this problem, we need to use a service like Redis Service which sits out from the server but holds the user details.

## Conclusion

Endpoint protection implements rate limiting which can complicate as much as it can with the rules you want in your use cases. For a more detailed study, we can keep digging, but for the basic concepts, this will do the work.