# Latancy and Throughput

![Latency and Throughput](https://miro.medium.com/max/720/1*l-_egrC5G_iXRelmYajz6g.jpeg)

You might have heard of latency and throughput many times during your tenure as a system designer. This is a very basic topic that can be confusing for some people due to the reason that it tends to use these terms while staying out of context. So, here we are going to discuss latency and throughput in detail so that we will be clear next time we hear any one or both topics.

## Latency

Latency is nothing but the duration it takes to complete any operation. When you want to access data or move data from one place to another place in a system or among various systems then the time or the duration it takes to complete that work is called latency. You can simply state it as a lag which is a more common word, we use daily. It’s a simple logic that tells you how long the distance from your website is to get to the server and have a response back from it.

If you are looking into any website, then you want it to be fast and smooth and you would never want it to lag. To lag means it has high latency. This plays a very important role in the experience of your clients who checks your site for anything. People will naturally move towards the site with low latency if they want their work done nicely. Even you search for those websites whose response is fast.

![Loading](https://miro.medium.com/max/720/1*ytrDkRGy88OXMEgZizd3fg.jpeg)

For example, if you take an array and you have to go to a certain element you need to move over each element one by one until you find the one you need but if you have to find a value in a hash table you just need to look for a key and the data will be with you without having to go one by one with them.

The most familiar we can be with this topic is from the game PUBG. In the game, if it lags even for a bit then there’s a possibility that you might get killed by your opponents. That’s why you must have smooth gaming that will let you handle your enemies accordingly.

Latency is the inverse of speed. This means that you want higher speeds teamed up with low latency. We mostly use HTTP on our browser for our operations where the speed of your site is determined by the distance as well. This means that it will take more time to ping a server that is far away than to ping the one that is stored in your memory system.

This is the reason why latency is a very interesting topic in the computing world.

## Throughput

Throughput walks along with latency and is defined as the maximum capacity of a system. You might have heard of throughput since it is used in factories to calculate how much work can be done in a specific time. For example, if the task is making candies and you can make around 25 candies per hour then that is your throughput. So, to understand throughput in the computing world, you need to keep this example in mind and think about the candy at the data and the hour as it is — the unit of time. If you have a 40Mbps Internet connection in your home, then that means 40Mbps is the throughput of your Internet.

If your website receives 100 requests per second and then gives a response to only 60 of them then the throughput of your site is 60 per second. Now when you change this into the number of bits then the result might be or around N bits per second.

A server always has its limits. For example, if a server can handle 100 bits per second, then that is its limit, and it cannot respond to any more requests than that. This is referred to as a term — bottleneck which is the constraint on the system. If a system has three servers, with three different bits per second respectively, then it doesn’t matter if the first server has very high bits per second but if the other has the lowest then the system will be operating at the lowest because this would be the constraint. This means the slowest one will hold the speed of other servers in that system.

![Throughput](https://miro.medium.com/max/1100/1*L2exMUY75lVtZFz2pegMyQ.webp)

What we should take from this is that if we want to increase the throughput of our system then we should increase the throughput of our lowest bottleneck first. This can be done by using more hardware or increasing the capacity and performance of our existing hardware. You can see some different other ways but the one about the hardware we just mentioned might be the ultimate one.

However, increasing the throughput is only the short-term solution and if you want to have a good system then you might consider splitting up the requests and distributing them across your resources.

## Conclusion

Latency and throughput are very simple topics. They are not correlated to each other, but they have a certain effect on your system and since your intention is for your system to run smoothly without any delay then you should keep both topics in mind and work your way through both. So, I hope the next time you hear any of the topics between latency and throughput, you will be able to explain it to someone else without any confusion.
