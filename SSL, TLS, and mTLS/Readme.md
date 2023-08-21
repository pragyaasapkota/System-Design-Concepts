# SSL, TLS, and mTLS

![SSL, TLS, and mTLS](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*HoOiWZlwtNRHMKiDoec2DQ.jpeg)

System Design has many background concepts that might not sound so important but are always good to keep in mind. Similar concepts are some communication protocols like SSL, TLS, and mTLS.

## SSL (Secure Sockets Layer)

SSL is a protocol that encrypts and secures communication happening over the internet. Though it was already developed in 1995, it has been deprecated in favor of Transport Layer Security (TLS). However, it is still called an SSL certificate because most of the significant certificate with SSL provides the certificate with the same name.

### Why is SSL essential?

SSL was created so that not everyone can read the data transmitted during communication on the internet. It protects user privacy and doesn’t let anyone intercept the data.

This happens when SSL encrypts the data and stops possible cyber attacks when it prevents attackers in the transit itself.

## TLS (Transport Layer Security)

As mentioned earlier, TLS is a deprecated version of SSL. It works for privacy and data security for communications over the internet between web applications and servers.

The components involved in TLS protocols are: -

### Encryption

It hides the data so it can’t be transferred from or to third parties without proper authentication.

### Authentication

It verifies whether the parties involved are who they claim to be.

### Integrity

It verifies if the data have been tampered with.

## mTLS (Mutual TLS)

Moving on, we have mTLS which means the parties at each end of the network connection need to be authenticated. It happens by checking that they all have the correct private keys. In addition, their individual TLS certificates add to the verification process.

### Why use mTLS?

mTLS are commonly seen in [microservice architectures](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Microservices) and [distributed systems](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System) in a [zero-trust security model](https://en.wikipedia.org/wiki/Zero_trust_security_model) to verify each other. The mTLS ensures the secured traffic on both servers and the client’s part. It has an additional layer of security for the users who log in to the network or applications. Moreover, it verifies the connection with the client who has devices that don’t follow the login process as the Internet of Things (IoT).
