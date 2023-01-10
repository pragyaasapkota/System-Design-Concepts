# IPv4 Vs. IPv6

![IPv4 Vs. IPv6](https://miro.medium.com/max/720/1*1m03P3W8aXmDGmXVPhLH_w.webp)

Previously, we talked about IP addresses, their types, and the versions [here](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol). Now, we will see the differences between the two versions of [IP addresses](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol) — IPv4 and IPv6.

In the table of the difference between IPv4 and IPv6 presented below, we will discuss around 22 differences including deployment date, address space, checksum, conversion, Variable Length Subnet Mask (VLSM), DNS Records, example, and so on.

Let’s see all of them in one table.

| S.N. | Factors                                | IPv4                                                         | IPv6                                                                                |
| ---- | -------------------------------------- | ------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| 1.   | Deployment Date                        | 1981                                                         | 1998                                                                                |
| 2.   | Address Length                         | 32-bit (4 bytes)                                             | 128-bit (16 bytes)                                                                  |
| 3.   | Address Space                          | 4.29×10^9                                                    | 3.4×10^38                                                                           |
| 4.   | Address Representation                 | Dot-decimal                                                  | Alphanumeric Hexadecimal                                                            |
| 5.   | Required Bytes                         | 576                                                          | 1280                                                                                |
| 6.   | Header                                 | 20-60 bytes                                                  | 40 bytes fixed                                                                      |
| 7.   | IPSec                                  | Optional – depends on application                            | Inbuilt IPSec                                                                       |
| 8.   | Connection Integrity                   | Unachievable                                                 | Achievable                                                                          |
| 9.   | Configuration                          | DHCP (Dynamic Host Configuration Protocol) and Manual        | Auto and renumbering                                                                |
| 10.  | Checksum                               | Available                                                    | Not available                                                                       |
| 11.  | Packet Fragmentation                   | Routers and sending hosts                                    | Sending hosts                                                                       |
| 12.  | Packet Flow Identification             | Not available                                                | Available (also uses the flow label field in header)                                |
| 13.  | Encryption and authentication facility | Absent                                                       | Present                                                                             |
| 14.  | IP to MAC                              | Broadcast Message Transmission Scheme [Broadcast ARP]        | Multicast and anycast message transmission scheme [Multicast Solicitation Neighbor] |
| 15.  | Conversion                             | Can be converted to IPv6                                     | Only a few can be converted to IPv4                                                 |
| 16.  | Fields Count                           | Four fields separated by dot (.)                             | Eight fields separated by colon (:)                                                 |
| 17.  | Variable Length Subnet Mask (VLSM)     | Supports VLSM                                                | Doesn’t support VLSM                                                                |
| 18.  | Local Subnet Management Group          | Internet Group Management Protocol (ICMP)                    | Multicast Listener Discovery (MLD)                                                  |
| 19.  | Address Reuse                          | Addresses must be reused and masked.                         | Every device can have unique address.                                               |
| 20.  | DNS Records                            | Pointer (PTR) records + IN-ADDR + ARPA DNS Domain            | Pointer (PTR) records + IP6.ARPA DNS Domain                                         |
| 21.  | Class                                  | Five classes - [Class A, Class B, Class C, Class D, Class E] | No classes                                                                          |
| 22.  | Example                                | 192.22.181.111                                               | 3111:0000:2928:dfei:0057:0000:0000:fefb                                             |

> Note: — The raw version of the table is available publicly on GitHub gist. Please click the [Difference.csv](https://gist.github.com/pragyaasapkota/901308cb4c6de240a6827e973fe32532) in the bottom left side of the table if you want to take a look at it.
