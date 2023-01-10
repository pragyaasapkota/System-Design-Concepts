# IP Address: A concept we must know

![Internet Protocol](https://miro.medium.com/max/720/1*-7JIeMEDsM041e0NYr1hsA.webp)

We previously looked at IP (Internet Protocol) briefly when we discussed [Network Protocol](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Network%20Protocols). In this article, we will check out the concept of IP addresses in a little more detail.

Starting with the definition, the IP protocol is a fundamental layer of protocols that tells us how to implement communication across internet networks. They are the rules that look out for the data format that is transmitted within the network. Likewise, an IP address is a unique address that keeps the track of devices that joined the internet or the local network. They help us identify the types of data that are communicated between devices. These addresses have location info which allows the information transmission. In addition, IP addresses help the internet work efficiently by differentiating between the devices like computers, routers, smartphones, tablets, etc.

## Types of IP addresses

There are four types of IP addresses in existence.

1. Public

2. Private

3. Static

4. Dynamic

Let’s see them individually for a better understanding.

### Public IP Address

With a Public IP address, there is a single primary address for the whole network. All the connected device has one IP address. We can think of it as the IP address your router gets from the ISP provider during installation.

### Private IP Address

Further, there is a Private IP address which is a unique code your router assigns to the devices within your network. These are the devices you use in the local internet network like laptops, computers, smartphones, tablets, etc.

### Static IP Address

Moving on, we have a Static IP Address, an IP address that can never be changed. It is created manually and can never be assigned. That’s why it is expensive which is later balanced out by reliability. Common examples of static IP addresses would be server hosting services, geo-location services, etc.

### Dynamic IP Address

Finally, we have reached a Dynamic IP address where the IP address can be changed when required and is not the same as the time change. The IP addresses here are generally assigned by Dynamic Host Configuration Protocol (DHCP) server that is supported by the IPv4 version of IP addresses. Right now, the dynamic IP address is the most used because of the cheap deployment costs and reusable features. The IP address can be used and reused within the network as much as it is required. They are commonly used in personal cases and consumer equipment.

## Versions of IP addresses

There are [two versions](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/IPv4%20Vs.%20IPv6) of IP addresses to date.

### IPv4

The IPv4 was the original IP version that was deployed in 1981. It uses a 32-bit numeric dot-decimal representation with 4.29×10⁹ address space. It was all good and better until the internet use grew and the IP address version needed to be updated. E.g.: - `101.11.192.181`

### IPv6

When the number of people using the internet started growing, we needed an update on IPv4 which introduced us to a new version of IP addresses in 1998. However, IPv6 was brought into use only in the mid-2000s. It uses a 128-bit alphanumeric hexadecimal representation that can provide about ~340e+36 IP addresses. In simple terms, we have about 3.4×10³⁸ address space in the IPv6. This is a much larger amount that might last many years to come. E.g.: - `1221:0000:4235:0000:0000:7t8c:10g8`
