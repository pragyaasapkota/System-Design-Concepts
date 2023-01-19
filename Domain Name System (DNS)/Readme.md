# Domain Name System (DNS)

![DNS](https://miro.medium.com/max/1400/1*hKJ7Duh-dXlDSyx0TYJs9g.webp)

In my previous article, we discussed [Internet Protocol](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol) and [IP addresses](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol). Where IP addresses helped for the connection between devices, it's easier to remember names like youtube.com than the number `216.58.206.238`. The system that translates IP addresses to a human-readable domain is called Domain Name System. In short, it is a hierarchical and decentralized naming system for [IP addresses](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol).

Let’s see some of the IP addresses of the most common domain names we use.

| S.N. | Domain         | IP Address     |
| ---- | -------------- | -------------- |
| 1.   | google.com     | 142.250.217.78 |
| 2.   | gmail.com      | 142.251.33.69  |
| 3.   | duckduckgo.com | 40.89.244.232  |
| 4.   | facebook.com   | 157.240.3.35   |
| 5.   | youtube.com    | 216.58.206.238 |
| 6.   | ebay.com       | 66.211.175.229 |
| 7.   | yahoo search   | 98.136.144.138 |

## Servers in DNS

The Domain Name System has four servers: -

1. DNS Resolver

2. DNS Root Server

3. TLD Nameserver

4. Authoritative DNS Server

### DNS Resolver

The first server on the Domain Name System is DNS Resolver which is also known as DNS Recursive Resolver. It’s the mediator between the user and DNS nameserver. When the DNS query is received, the resolver either responds with the cached data or sends a request to the next stop on the DNS servers – Root Nameserver. After the nameserver, the request gets transformed into TLD (Top Level Domain) nameserver. Finally, the last stop for the request is the authoritative nameserver which we will discuss soon enough.

When it receives the response from the authoritative nameserver with the requested IP address, the DNS resolver sends the response to the user.

### DNS Root Server

The DNS Root Server, also known as DNS Root Nameserver receives the query from DNS Resolver with a domain name and directs it to the TLD nameserver based on the domain extension like `.com`, `.to`, `.net`, etc. There are 13 root nameservers in total but there are multiple devices associated with them. For example, VeriSign Global Registry, Virginia is one of the DNS Root Nameserver. In addition, there are many copies of each of the 13 root nameservers all over the world. They use the Anycast routing method for accelerated responses.

These root nameservers are usually looked over by a nonprofit organization called [ICANN](https://www.icann.org/). It stands for Internet Corporation for Assigned Names and Numbers.

### TLD Nameserver

Moving on, we have TLD Nameserver where the former stands for Top Level Domain. It keeps up the information for those domains that have the same extension. Those TLD nameservers are managed by [IANA](https://www.iana.org/) (Internet Assigned Numbers Authority). To note, IANA is a branch of [ICANN](https://www.icann.org/) we previously discussed.

IANA distributes the TLD nameserver into two separate groups.

- **Generic top-level domains**
  The common domains like `.com`, `.org`, `.net`, `.edu`, `.gov`, etc.

- **Country code top-level domains**
  Those domains that are specific to a country or state like `.np`, `.in`, `.cn`, etc.

### Authoritative DNS Server

Finally, we have reached the last server – the Authoritative DNS Server which includes the information dedicated to the domain name it serves and sends the response to the DNS Resolver with the IP address found in the DNS A record. Likewise, if the domain has a CNAME record, it will respond to the DNS resolver with the record where the resolver starts a new DNS lookup to procure from an authoritative nameserver which is generally the A record with an IP address. In the case where the domain cannot be found, the NXDOMAIN message is returned.

## How does DNS work?

![DNS Work](https://miro.medium.com/max/1100/1*8Oo5GlWnz5Hw4moDgaImQA.webp)

1. User requests for a site — example.com. The DNS resolver receives the query afterward.

2. The resolver sends queries to the DNS root nameserver recursively.

3. The root nameserver responds to the resolvers with TLD address.

4. Resolver requests the .com TLD

5. TLD returns the IP address of the domain’s nameserver.

6. The resolver sends a query to the domain’s nameserver.

7. The IP address of the site is returned to the resolver from the nameserver.

8. DNS resolver returns the [IP address](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Internet%20Protocol) of the domain to the web browser.

After these steps, the user can request content from the given IP address.

## Types of Queries in DNS System

![DNS Types](https://miro.medium.com/max/1100/1*pj37kNteExrsWJHIl87eXQ.webp)

There are three types of queries in the Domain Name System.

- Recursive Queries
- Non-recursive Queries
- Iterative Queries

### Recursive Queries

The first kind — recursive queries of the Domain Name System have a DNS user that needs a DNS server to respond to the users with requested resources. In case the requested resources are not available, or the resolver couldn’t find them, return an error message.

### Non-recursive Queries

Further, we have non-recursive queries where the DNS resolver saved the data in the local cache or requests the DNS nameserver where the correct IP address for the hostname is saved. Either way, additional queries are not required like the recursive queries. The answer is immediately sent to the user in the non-recursive queries.

### Iterative Queries

The final type of query in DNS is the iterative kind where the DNS user provides a hostname, and the resolver returns the answer as best as it can like if the DNS records are already in the cache. If that is not the case, the DNS user is redirected to the root server which will point to the required DNS zone. After that, the DNS user repeats the query directly against the DNS server it was directed to.

## Record Types (Zone files) in DNS

The DNS records or the zone files are the instructions in authoritative DNS servers with information about the domain. This is the IP address with the domain and the instruction on handling the requests for that domain. There are a few things called DNS Syntax where there are a series of text files. The syntax has characters bonded as the string of commands used to tell the DNS server about the tasks to do. In addition, the DNS records always have TTL (Time-to-live) that tells us the time interval for the DNS server refresh operation.

Let’s check out some common record types in DNS.

- Address Record or **A** record keeps the IPv4 address of a domain.
- **AAAA** (IP Version 6 Address Record) has the IPv6 address of the domain.
- **CNAME** (Canonical Name Record) forwards one domain to another without an IP address.
- **MX** (Mail Exchanger record) that directs mail to an email server.
- **TXT** (Text Record) with an admin store that can record text notes that can be used in email security.
- **NS** (Name Server Records) stores the name server for a DNS entry.
- **SOA** (Start of Authority) with admin information about the domain.
- **SRV** (Service Location Record) to specify a port for a specific service.
- **PTR** (Reverse Lookup Pointer Records) to give up the domain name in reverse lookups.
- **CERT** (Certificate Record) for the public key certificates

## DNS Zones

Moving on, we have DNS Zones, a part of the domain namespace for a specific legal entity like a person, organization, or company. These entities maintain the DNS zone. Further, the DNS zone is also the administrative function that helps provide control of DNS components like authoritative nameservers.

## DNS Caching

Mostly known as DNS resolver cache, this is a temporary database in the operating system with histories like visits and such. The memories are saved for easy configuration later. As discussed earlier, every DNS record has TTL (Time-to-live), we can know the time when the records are cached. The record goes into the cache and the value of TTL gets stored as well. This repeatedly happened — with every changing second. However, the record is either deleted or purged from the cache when it hits zero. If a query is received for that record, the DNS resolution is processed once again.

## Reverse DNS

The reverse DNS means having a query for the domain name related to a given IP address. This opposes the forward DNS lookup to return an IP address related to the domain name. To note, the reverse DNS operations are not used universally because they are not so important functionality on the internet. This phenomenon uses PTR records, and a server can’t have reverse DNS if there are no PTR records. You can usually see them while you check if your email came from a valid server before you have it on your network.

![Reverse DNS](https://miro.medium.com/max/1100/1*vlUqv14WBzOMVt5vEWtS8A.webp)

## What to do when DNS servers go out?

If there is a case where all the DNS servers go out, you must type in the site’s IP address directly. However, if only one DNS server is down, you can try the alternatives. For example, if the Google DNS server is out, there is a primary alternative `8.8.8.8`, and a Secondary one `8.8.4.4`.
