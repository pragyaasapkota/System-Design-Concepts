# HTTPS: Is it better than HTTP?

![HTTPS](https://miro.medium.com/max/1050/1*F3kuJ3QBSn9ZkVgb--vnyg.jpeg)

**HTTPS** stands for Hypertext Transfer Protocol Secure which is just an extension of the **HTTP** (Hypertext Transfer Protocol). The HTTPS is the more secure data transmission factor that uses Transport Layer Security (**TLS**) to address the encrypted data. This means that if a hacker tries to get into the system, all they get is binary data and not valid data.

This is a secure way of data transmission.

HTTPS starts with the client and the server. When they form a **TCP** (Transmission Control Protocol) connection, a server receives a “client hello” from the client which embeds the set of required encryption algorithms like Cipher suites and the latest TLS version where it can reside.

After that, the server generates a “server hello” message to let the client know whether it can support the given algorithms or the TLS version.

Immediately after, the client also picks up the SSL certificate with a public key, hostname, expiry dates, etc. This was sent by the server so that the client would validate it and generate a session key. This session key is encrypted using the public key and then the server key gets this session key which it will decrypt using the private key.

![HTTPS Vs. HTTP](https://miro.medium.com/max/1050/1*DbG7EO1nOy6jqPO5EYiwwA.jpeg)

Now we get to see symmetric encryption since both the client and the server hold the same session key. The encrypted data is transmitted in a secure bi-directional channel.

This is far more secure than what we have previously seen with the HTTP protocols.

However, it still uses symmetric encryption when the asymmetric gives far more advantage to our cause. There are a few reasons for this,

1. Symmetric encryption gives no security if the server tries to send the encrypted data back to the client since anyone will be able to decrypt it using the one session key. But that is not the case in asymmetric encryption.

2. When we need to transmit data in long sessions, asymmetric encryption gives us many mathematical overheads. This is avoided when we use symmetric encryption.

Wrapping up, HTTPS is a secure extension of HTTP and now, it is more prevalent than ever.