# Load Balancing: Why do we need them?

![Load Balancing](https://miro.medium.com/max/720/1*oIL6DdarITKsX98k-6lwWg.jpeg)

We have seen concepts of system design like [proxies](https://github.com/aygarp-modsiw/system-design-concepts-hacktoberfest2022/tree/master/Proxies), [caching](https://github.com/aygarp-modsiw/system-design-concepts-hacktoberfest2022/tree/master/Caching), [network protocols](https://github.com/aygarp-modsiw/system-design-concepts-hacktoberfest2022/tree/master/Network-Protocols), etc. in my previous articles. In [latency and throughput](https://github.com/aygarp-modsiw/system-design-concepts-hacktoberfest2022/tree/master/Latency-and-throughput), we discussed how the increasing number of requests in the server leads to slow responses that are low throughput and high latency that can ultimately lead to system failure — no availability. To solve this problem, you can either give more muscle power to the server (vertical scaling) or you can add more servers (horizontal scaling). However, you might notice the problem of figuring out the way of distribution of the incoming requests among the servers. You’ll have to evaluate how you balance and allocate the load by the incoming requests.

ENTER Load Balancers.

As by the term itself, you can guess that it means it balances the load. It is made up of two words — load and balance. It sits between the client and the server to work out the way to distribute the incoming requests across the various servers so that the end-user as a client can receive fast and reliable service. To note, the load balancers can also be inserted in other places than between the client and server.

You can also think of the load balancers as traffic managers who direct the traffic which leads to the availability and throughput on the street.

Load balancers can be thought of as reverse proxies with the exception that, unlike the reverse proxies, they can be inserted anywhere like your server and the database as well.

## The Balancing Act- Server Selection Strategies

When you add a new server, the load balancer needs to know that there is an added aspirant to which you can route the requests. The removal of a server should be in the knowledge of the load balancer too.

A load balancer needs to know how many servers are on work so that they can be informed about the load levels, status, availability, and the current task of each server. If the balancer is well acquainted with this knowledge, it can easily redirect the request to a server and the proper distribution is done among all the servers.

The balancer can randomly pick a server and direct the traffic, but this can create a problem and the ‘unbalanced’ allocations. Some servers might get loaded here while some might just be left out. This affects the system’s performance in a bad way.

## Round Robin and Weighted Round Robin

Round Robin is a process we process lists as a loop. We start at the first item on the list and move along it but when we reach the last, we move back to the first item again — forming a loop. The load balancer can do this by looping via the available servers in a particularly fixed sequence. This helps the load to be evenly distributed among the servers.

Moving on, we can also give more weight to some servers than others leading some of the servers to have high power and some to have low. When this is done, the traffic is split proportionally so the balance is maintained.

## Load-based server selection

A load balancer can have the current capacity, performance, and the load of the servers in their go-to list so they can dynamically allocate the servers to the incoming requests to finally calculate the highest throughput and lowest latency. This is done by monitoring the performance of each server to decide the ones that can handle the specific request and the ones that can’t.

## IP Hashing-based Selection

The incoming requests can be hashed using the IP address and the obtained hash value will determine the server it needs to be directed to. For example, if there are five different servers, the hash function will be designed so it returns one of the five hash values to choose one of the servers that will then process the request.

This is very helpful when you request from a certain region to get the server's data to address the needs within that region. Or you can also have the data from your server’s cache requests so that they can be processed fast. You just need to make sure that the request goes to the same server that previously cached the similar request, so the response time has a speed.

If each of the servers maintains its independent cache and the load balancer doesn’t consistently send identical requests to the same server, the servers will just re-do the work that has already been done in the previous request by another server. This leads us to lose the optimization that hoes with the caching data.

## Path or Service based selection

Furthermore, the path or function or service being provided can be used to get the load balancer to route the requests as well. For example, if you are buying clothes online — the browsing of the clothes can be handled by one server while the payments will be handled by the other. If one in fifty visitors buys the clothes — a small server can look out for the payments while the big one can look out for traffic.

## Mixed Bag

We are quite aware that things get more complicated when it gets higher in levels. There can be multiple load balancers that have different server selection strategies. If your system is large and highly trafficked, you can also use load balancers for load balancers. This means you keep adding the pieces to your system until your performance is tuned to your needs.
