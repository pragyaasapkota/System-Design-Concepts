# Transmission Control Protocol (TCP) and User Datagram Protocol (UDP)

![TCP Vs. UDP](https://miro.medium.com/v2/resize:fit:720/format:webp/1*wWNoVkUu6H7aptppwKp2Yw.jpeg)

## TCP

The Transmission Control Protocol (TCP) is a connection-oriented service where the data transmission is on both sides after the connection is established. It has an in-built system to check on the errors as well. In addition, the system also guarantees that the data get delivered in the order it was sent.

This is the better option for transferring information such as data files, web pages, images, etc. However, the feedback mechanisms result in a larger overhead that helps for the good use of available bandwidth on the network.

![TCP and UDP](https://miro.medium.com/v2/resize:fit:720/format:webp/1*XhzK01sbbMrlaALr1uVusQ.jpeg)

## UDP

Further, the User Datagram Protocol (UDP) is a connectionless internet protocol. In the UDP, neither recovery nor error-checking checking services are needed. The data is repeatedly sent to the receiver whether the receiver is ready or not and is not responsible for end-to-end communication.

There is no overhead to open, maintain, or terminate a connection. We can see the protocol in real-time communications like broadcast transmissions or multicast network ones. Comparatively, UDP is faster than TCP and is much more efficient.

## TCP Vs. UDP

| S.N. | TCP                                            | UDP                                         |
| ---- | ---------------------------------------------- | ------------------------------------------- |
| 1.   | This is connection-oriented.                   | This is connectionless.                     |
| 2.   | This is reliable.                              | This is unreliable.                         |
| 3.   | The data delivery is guaranteed.               | The data delivery is not guaranteed.        |
| 4.   | TCP is comparatively slower than UDP.          | UDP is comparatively faster than TCP.       |
| 5.   | Broadcasting is not supported.                 | There is broadcasting support.              |
| 6.   | Lost packets can be retransmitted.             | Lost packets cannot be retransmitted.       |
| 7.   | It has sequence delivery.                      | It has no sequence delivery.                |
| 8.   | It has acknowledgment.                         | It has no acknowledgment.                   |
| 9.   | It has handshaking.                            | There is no handshaking signal.             |
| 10.  | Use cases: - (HTTP & HTTPS & SMTP & POP & FTP) | Use cases: - (Video Streaming & DNS & VoIP) |
