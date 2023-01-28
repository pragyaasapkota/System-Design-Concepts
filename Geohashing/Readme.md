# Geohashing: Encoding the location coordinates

![Geohashing](https://miro.medium.com/max/720/1*iJsX719rBISdBKJTaTj0gQ.webp)

In 2008, Gustavo Niemeyer invented a geocoding method where geographic coordinates (latitude and longitude) were encoded in short alphanumeric strings. The basic idea was first brought on by G.M. Morton in 1996. For a better understanding, let’s see an example,

The latitude and longitude of Kathmandu, Nepal are 27.717245 and 85.323959 respectively and we write the coordinates like (27.717245, 85.323959).

Now, if we represent them in geohash, it becomes short and easy to remember,

`Tuutttg08kgn`

You can easily see geohashing used in some of the databases like MySQL, Redis, Amazon DynamoDB, and Google Cloud Firestore.

## How does Geohashing work?

Geohashing works as a hierarchical spatial index that uses a Base-32 alphabet encoding system. There are 32 cells, and each cell further contains 32 individual cells. The first character in the encoded geohash identifies an initial location that can be understood by thinking of the place as a point. The world is divided into smaller and smaller cells repeatedly until the location is precise. The size of the cell also determines the precision of the location. The points or the location are closer if the prefix matches. The longer the match of the prefix, the closer the location.

For example, `Tuutttg08kgn` and `Tuutttg08kfg` are very close since they share the same prefix `Tuutttg08k`.

In addition, the larger the characters in the string (maximum 12), the more precise the location. This means that we also have anonymity with the use of geohash since only the area is represented in the encoded alphanumeric string.

## Cell Sizes for Geohashing

| Geohash | Cell Height | Cell Width |
| ------- | ----------- | ---------- |
| 1       | 5000 km     | 5000 km    |
| 2       | 1250 km     | 1250 km    |
| 3       | 156 km      | 156 km     |
| 4       | 19.5 km     | 39.1 km    |
| 5       | 4.89 km     | 4.89 km    |
| 6       | 0.61 km     | 1.22 km    |
| 7       | 153 m       | 153 m      |
| 8       | 19.1 m      | 38.2 m     |
| 9       | 4.77 m      | 4.77 m     |
| 10      | 0.596 m     | 1.19 m     |
| 11      | 149 mm      | 149 mm     |
| 12      | 18.6 mm     | 37.2 mm    |

## Use Cases

Let’s see some of the use cases of geo hashing.

- Storing and representing a location in a database is easy and simple.
- Sharing and remembering is easy since it is less complicated than latitude and longitude. It can be represented as a URL.
- We can find out nearby points with string comparison which is very efficient in case we have large indexes.
