# Network Protocols

![Network Protocols](https://miro.medium.com/max/720/1*if-dJwDaMHtGxU8CnEvxSg.jpeg)

Protocols are the rules and regulations that are required to administer something within a boundary. Communications need to have some structure among the networks. A network protocol is when you have rules that bind the communication in a structure. The most common network here would be WWW (World Wide Web) and the protocols are TCP/IP, HTTP, etc.

Let’s get ourselves familiar with some of these protocols.

### 1. Internet Protocol (IP)

The first one for us to discuss is [Internet Protocol](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol) (IP) which is the fundamental layer of protocols. This tells us how to implement communication across the internet networks.

Under this protocol, the data are transmitted in packets — small bundles of information (2¹⁶ bytes). There are two components in each packet: -

a) The Header

b) The Data

The header holds the metadata about the packet where it states the IP address of the source and the destination.

**NOTE**: An [IP address](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol) is a numeric label each device gets when connected to a computer network. It consists of two addresses — Private and Public with [two versions](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/IPv4%20Vs.%20IPv6) — IPv6 which is getting widely used since IPv4 is running out of numerical addresses.

### 2. Transmission Control Protocol (TCP)

![TCP Data Transfer](https://miro.medium.com/max/720/1*RiJJoBPYCHCa7Iteeh-19A.jpeg)

Data transmits via packets in the IP (Internet Protocol) which is small which means there would be multiple packets that can lead to lost or even disordered packets which corrupts the data leading to so many problems. TCP or Transmission Control Protocol was created on top of IP to solve this problem where the data packets are transmitted in order. Its header holds the information about the ordering of the packets.

We refer to this protocol as TCP/IP since it’s built on top of the IP. Here, TCP first establishes a connection between the two parties before transmitting the data.

### 3. Hyper Text Transfer Protocol (HTTP)

![HTTP](https://miro.medium.com/max/720/1*EaoOXBisyZ46M6dLxco76w.jpeg)

Moving on, we have HTTP or Hyper Text Transfer Protocol which is an abstraction built on top of TCP/IP protocol. It uses the request-response system which we see in the client-server architecture. This is what we have been seeing on the internet these days. Here, we have moved past the TCP/IP protocol since the requests and responses here have headers and bodies where the data is set by the developers.

HTTP methods also have some commands like “GET”, “POST”, “PUT”, “DELETE”, and “PATCH”.

## Conclusion

These protocols govern the communication between machines and software lying in the given network. Knowing about this always helps to understand the complex topics we will discuss in the upcoming articles.
