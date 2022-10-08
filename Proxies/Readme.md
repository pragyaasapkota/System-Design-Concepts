# Proxies

![Proxies](https://miro.medium.com/max/720/1*0HhBVffy8nJg-3qN6pMZOA.jpeg)

Proxy is the word we hear a lot. In the English dictionary, it means a substitute — providing the power of authority to act like the one. In the computing world, a proxy means a middleman between a client and a server. A client originates a request which is received by the middleman who then transfers it to a server for the data and then goes to the middleman again before the client receives it. The middleman here is a proxy.

The proxy servers are very useful when you design a system. The principle of VPNs is based on proxy. When you use a proxy, it can sometimes mask the identity of a client which leads to having the IP address of the proxy in the server instead of the originating client itself. We might have experienced this in this while we access the restricted data or try to download things via torrent.

When we use the word proxy, we usually mean ‘forward proxy’. It is the proxy that acts on the behalf of the client while the interaction between the client and the server is made. This is different than the ‘reverse proxy’ which acts on the behalf of the server. The data flow or the diagram — all look the same.

![client-proxy-server](https://miro.medium.com/max/720/1*fteXDHNx4Q04_RA3IIW7eQ.jpeg)

But how do distinguish between ‘forward proxy’ and ‘reverse proxy’?

If the server is unknown about the client’s request and its response traveling via the proxy, it’s a forward proxy. But, if the client is unknown about the request and response via the proxy, it’s a reverse proxy. This makes the whole ideology behind the proxy sneaky.

## Conclusion

When you are up for designing a system, proxies might be a life savior. Especially, the reverse proxies. It can act like a gatekeeper or a screener or a load-balancer or an all-around assistant. If you don’t want your main server handling some minor tasks, it might be passed on to the proxies.

So, it is important to understand the reason for the existence of the proxies while also knowing what they do.
