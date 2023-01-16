# Content Delivery Network (CDN)

![CDN](https://miro.medium.com/max/1400/1*Dx6bXV6tiu8n8B7jTCbXEw.webp)

When there is geographically distributed traffic for the websites, Content Delivery Network (CDN) helps with the fast delivery of the content with the help of a group of servers working together. These files usually have HTML/CSS files, JS files, photos, and so on which are handled by the CDN. This helps improve the security of the data while the content availability and redundancy are also high. To top it off, with the use of CDN, bandwidth cost is also reduced with improved performance levels.

## How does CDN work?

The content distribution is easy from CDN because the data comes from the closest data centers so the original server will have less load. The original server contains the original version of content which is distributed across multiple locations around the world in edge servers. The performance is improved because of the distance between the client and the website server where the cached version of data is received upon request. The original server has less load and scalability is improved as well.

_Example: -_

Let’s imagine someone in Nepal requests a website hosted in Russia. The data will be received from the nearest edge location which might be somewhere in China. This helps with latency since the original server doesn’t need to get the load.

The most common example of CDNs would be Amazon CloudFront, Google Cloud CDN, Cloudflare CDN, and Fastly.

## Types of Content Delivery Network

![Types of CDN](https://miro.medium.com/max/1100/1*gy5EfHIeJkX5jmMkllEkYA.webp)

### Push CDNs

The push Content Delivery Network receives new content whenever changes occur on the server. The changes include uploading new content directly to the network and rewriting URLs that point to it. Whenever content expires or is updated, we configure it — every time a change minimizes traffic or maximizes storage. For the sites that don’t have a large amount of traffic or barely updated content, push CDN works a charm. The content is updated once instead of getting re-pulled at regular intervals.

### Pull CDNs

Further, the pull CDNs deal when the cache is updated based on request. When a client sends a request and CDN fetches it from the original server and fills the cache with the latest data. This improves the maintenance aspect because the cache updates are performed based on the requests sent to the original server. This works great for high-traffic sites with distributed content on the network.

## Problems that might arise

Content Delivery Network (CDN) has a good concept and a good implementation system, but it comes with some issues that need to be looked at.

- It is very expensive when the service has very high traffic.
- Many countries and companies have blocked the domain and IP addresses of many CDNs.
- Sometimes, when the client in a country with no CDN tries to access the data, the distance might be bigger than when they were accessing the original server
