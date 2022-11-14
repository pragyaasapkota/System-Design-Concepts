# Hashing

![Hashing](https://miro.medium.com/max/720/1*sYSkRUQwau8wtD-6Mg60iA.jpeg)

Previously, we discussed hashing briefly under the section IP hashing-based selection in the article — [Load Balancing](https://github.com/aygarp-modsiw/system-design-concepts-hacktoberfest2022/tree/master/Load-Balancing). However, it might be a little tricky for some which are why this is an article with the basic concept of hashing.

## What is hashing?

The internet has been growing in its content rapidly. The content on the internet doubles every six months making it very difficult to find a particular one. The usual array and linked lists used to store data lead to a hard time when the data is large.

Thus, Enters HASHING.

A certain data of large size in an array takes O(logn) times in a sorted one and O(n) in the unsorted one. It might feel easier if the sorted array uses special techniques like binary search but if it’s not, we might have to use linear search. However, we cannot be sure if the error margin will be minimized. Hence, hashing is used so that we can have the constant time of O(1) on the operations. This is a far more effective method since the time of operation is independent of the data size n.

## Map-The data structure

The word ‘map’ means the relation of two sets — (key, value). The relation between the key and the value is that given a key, you can use a function to get a value. The function is called a hash function.

For a simple understanding, let’s imagine an array where the key is the index, and the value of that index is the required value. The array X with the key “i” gives the value from X[i]. The difference from the concept of an array on hashing is that the concept of a hash table is more generalized in comparison. The latter can have any value as a key instead of having an integer all the time. It can even be a name or an object times according to your requirement. The only trick here is to have a valid hash function to form an index that can store the object at a particular location from where we can later find the object easily.

### Example: -

Let’s imagine a set of strings {“pragya”, “sapkota”, “medium”}. Now we need to store these strings on a table. We need to have a quick update and the operation time should be O(1). We can’t be responsible for the ordering of the operation or even the maintenance.

Now, let’s think of a schema where we number the alphabets like a=1, b=2, c=3,. ….., z=26.

So, let’s have a number for each string.

1. “pragya” = 16+18+1+7+25+1 = 68

2. “sapkota” = 19+1+16+11+15+20+1 = 83

3. “medium” = 13+5+4+9+21+13 = 65

If you have a table of size 4, we can use the hash function as sum mod 4 and thus place it on the table for the table.

1. “pragya” = 68 mod 4 = 0

2. “sapkota” = 83 mod 4 = 3

3. “medium” = 65 mod 4 = 1

The table will look as below: -

| 0 | 1 | 2 | 3 |
| - | - | - | - |
| pragya | medium | | sapkota |

As you can notice from above that the idea is computing a location for a string with the help of a hash function. Here, the hash function is sum of the characters mod Table size.

![graph hash table](https://miro.medium.com/max/720/1*sjnbY7mmlviOmxaA2WF4rA.jpeg)

The way of searching a string with the use of the value is a very effective way of storing words in a dictionary.

## Hashing: The problems

On the above strings {“pragya”, “sapkota”, “medium”} we used the lowercase letters which have the numbers 68, 83, and 65 respectively. However, if we have the permutations of the letters such as “aygarp” for “pragya” or “saPkotA” for “sapkota” or “Medium” for “medium” — the numbers will the same as 68, 83, and 65. This leads to storing more than one string in one location which ultimately leads to what we call on hashing terms — COLLISION.

Likewise, another problem with hashing is determining the size of a hash table. The size is preferred to be a prime number to prevent collisions.

All of this leads us to two points as follows: -

- Picking a good hash function

- Dealing with the collisions

The hash function is supposed to be easy to compute and the one to avoid the maximum collisions.

## Consistent Hashing

If you have five servers and one of the servers dies due to some reason, the hashing function won’t be able to know it by itself. And if you then add a replacement server, it won’t know about it too. But the mod operator still stays 5 despite one server being removed and the other being added. For solving this problem, we have Consistent Hashing.

The concept of consistent hashing was brought to reduce the problem of hashing. However, it doesn’t eliminate those problems. This may not sound much in small-scale data but for large data — this is very important. The function applies to the requests and the servers to result in output in a set range of values. It reduces the problem of failed servers where the traffic still gets routed and the new server that has no allocations.

## Conclusion

Hashing can be an intricate topic when we learn system design. But we can divide each of the terms and mini topics to learn them individually in detail. Consistent hashing is one of the important ones to study and understand so that we understand other system design concepts like [load balancing](https://github.com/aygarp-modsiw/system-design-concepts-hacktoberfest2022/tree/master/Load-Balancing).
