# Caching

![Caching](https://miro.medium.com/max/720/1*W_2lfDkJSB0-2x_yvunJ9w.jpeg)

We have all heard about the cached memory that speeds up the performance of the system. This happens by reducing the latency which we have discussed earlier in the section — [latency and throughput](https://github.com/Pragya2056/system-design-concepts-hacktoberfest2022/tree/master/Latency-and-throughput). Let’s take a real-life example of caching — imagine a supermarket in the basement of your house. You can have the access to the shop anytime you want but you still buy a week worth of groceries to save time. This is caching.

## Common scenario

If we visit a particular point of a system time and again, the use of a cache can help your data load faster. The required data is saved on memory rather than disk from where the response is so much faster while making the network requests. Most of the websites these days stay cached in the CDNs (Content Delivery networks). This activity has reduced the load on the back-end server of the websites.

You are familiar that every time you make a network request, your backend server must do some computationally intensive and time-consuming work. But with the use of caching, you can convert your previous look-up time from linear O(N) time to constant O(1) time. This does not only limit here but also when your server must make multiple network requests and API calls to compose the data that the requester receives later, the caching data leads to low latency because of the reduced number of network calls.

Caching is usually inserted on the client (browser storage), between the client and server, or on the server itself. It can occur at many levels or points including the hardware level.

## Stale Data Handling

The data caching does not limit itself to the read operations but also to write operations with some of the considerations.

I have listed some of those considerations below: -

· For write operations, you need to keep your cache and database in sync.

· Since there are more operations to perform and new considerations handling the un-synced stale data need to be analyzed continuously, the complexity might increase.

· Sometimes, a new design is needed to handle the syncing with even more considerations like sync method (synchronous/asynchronous), intervals, and so on.

· To keep the cached data up-to-date, data ‘eviction’ or turnover is done with the help of LIFO (Last In First Out), FIFO (First In First Out), LRU (Least Recently Used), and LFU (Least Frequently Used).

## Conclusion

Caching is best on its way when the data is static or rarely changing. Also, when the sources of change are single operations instead of user-generated operations. However, caching may not be efficient if the cache refreshes done in intervals stays away from the purpose and user experience of the application.
