# OSI Model

![OSI Model](https://miro.medium.com/max/720/1*GMhZMOe2QxJ51RAIQcM4pQ.webp)

The ISO (International Organizations for Standard) OSI (Open System Interconnection) started developing in the late 1970s. By the year 1984, it was approved, and the model started implementing in real-time systems.

The OSI model is a logical and conceptual model that opens an interconnection between any two systems. It uses various layers of protocols and describes the computer packet transfer very effectively. You can take the OSI model as the universal language for computer networking. However, the OSI model is not directly implemented on the TCP/IP networks these days, but it can be taken over which will also help you with troubleshooting and identifying threats across the tasks. In addition, security is a high priority in the OSI model and also separates a complex function into simpler components which makes it easier.

There are seven layers in the OSI model. These layers have broken functionality and tasks among each other to reduce the complexity of the tasks. Each layer communicates with its software and hardware but services the layer above it. Among the seven layers, the lower four help with the flow of data via the network while the other three are dedicated to the services of the application.

![Layers of OSI Model](https://miro.medium.com/max/720/1*oEYfdnBcsB9OnzN2WIbdLA.webp)

### Layer-7 [Application Layer]

The application layer directly interacts with the data from the user and provides services to the user. It supports user applications like software for file transfers, database access, emails, and web browsers. Every message inside the OSI model enters and exits via the application layer. However, client software applications are not included in this layer but use protocols and data manipulation for the data from the user so that a valid result is received.

The protocols embedded in this layer are HTTP (Hyper Text Transfer Protocol), FTP (File Transfer Protocol), DNS (Domain Name System), and SMTP (Simple Mail Transfer Protocol) as well.

### Layer — 6 [Presentation Layer]

Next comes the presentation layer the gives the rules that specify the formats based on which the data transfer is done. In a way, the presentation layer is a translator or an interpreter. Whenever a different system needs to interact, the data needs to be translated and we can even do the byte reordering. For the sender, the data is translated to an intermediary format that can be understood by the receiver which will then translate the data into something that the application layer can use.

The presentation layer converts protocols, translates the data, encrypts/decrypts the data, expands graphics commands, and so on. The data is extracted from the application layer and further manipulated.

### Layer — 5 [Session Layer]

Further, we have the layer that provides the logical connection between two systems — the session layer. It creates, manages, and terminates the sessions. The sessions are open till the data transfer is made and are abruptly closed when the resources might be getting wasted. Likewise, the data transfer is synchronized with the checkpoints which adds security.

Session layers are good for dialogue management. There are three types of dialogues: -

1. Simplex — one-way communication like a radio

2. Half-Duplex — Two-way communication, but one at a time like a walkie-talkie

3. Full- Duplex — Two-way simultaneous communication like a telephone

### Layer — 4 [Transport Layer]

The transport layer gives a medium for data transfer between computers. The data received by this layer is converted into small data units called segments that include a port number, acknowledge number, sequence number, etc. The transfer is error-free and delivered in the original sequence. There are multiple connections possible for a single channel and the connection management is done by the layer itself.

It provides both Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) connections.

Handshaking is also supported in the transport layer. Handshaking generates a signal that establishes a connection between the computers before transferring the data.

The steps are: -

1. TCP connection request (syn A to B)

2. TCP connection reply (ack B to A)

3. Data Transfer (A to B)

![Handshaking](https://miro.medium.com/max/720/1*bc-oDqntpXIwlx06VfqMzA.webp)

### Layer — 3 [Network Layer]

The segments from the transport layer earlier are now converted to IP packets in the network layer where each packet has an IP header with Source IP, Destination IP, and other details about the packet. The [IP addresses](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol) help the packets travel between the networks with the help of the network layer which routes the packets. The congestion on the network is also handled by the layer followed by the rules that tell the way to define the way of making the packet of the right size to accommodate different media.

If the communicating systems are within the same network, this layer is not required.

### Layer — 2 [Data Link Layer]

Moving on, the data link layer further converts the packets from earlier to frames with a frame header that includes the source and destination MAC address. It provides good communication for the physical layer with the creation and detection of frame boundaries. Flow control and error control (parity, Hamming code) is implemented with the data link layer with the support of simplex, half-duplex, and full-duplex communication. It even has point-to-point (unicasting) support alongside broadcast communication.

The difference between the network layer and the data link layer is that the data link layer can have devices to communicate in the same network.

### Layer — 1 [Physical Layer]

Finally, we have reached the physical layer where the frames are further converted to bits (0/1) so they can transmit easily. The physical interface is then provided for the transmission where the rules are set by which the bits are passed from one system to another. All the aspects of physical communication like mechanical, electrical, functional, and procedural are covered by the physical layer for the tasks like voltage levels, physical data rates, etc.

## TCP/IP Reference Model

Also known as the Internet Reference Model, TCP/IP reference model is a four-layered architecture.

1. Application Layer

2. Transport Layer

3. Internet Layer

4. Network Access Layer (Network Interface Layer)

### Application Layer

- Like the application, presentation, and session layer of the OSI model.
- Application programs using the network

### Transport Layer

- Like the transport layer of the OSI model
- Works with TCP protocol only
- End-to-end message transmission management
- Error detection
- Error correction

### Internet Layer

- Like the network layer in the OSI model
- IP address
- Routing and congestion of packets

### Network Access Layer

- Like Data link and Physical layer of the OSI Model
- Cost-effective management
- Reliable data delivery
- Physical networks access
- Physical Media

## TCP/IP Reference Model Vs. OSI Model

| TCP/IP                                     | OSI                                          |
| ------------------------------------------ | -------------------------------------------- |
| 4 layered architecture                     | 7 layered architecture                       |
| Designed for internet only                 | Designed for general network                 |
| Supports TCP only                          | Supports both TCP and UDP                    |
| Limited to protocols only                  | Both functions and protocols in the layers   |
| Very hard to change the protocol in future | Easily replaceable protocols (mostly hidden) |

![OSI Vs. TCP/IP](https://miro.medium.com/max/720/1*c3gNZu3dBn76NA-4RiXHQA.webp)
