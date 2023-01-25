# Quadtrees

![Quadtrees](https://miro.medium.com/max/1100/1*WWrYsI6rQ35iJIzOKw5y4A.webp)

We might have heard about Octrees a few times. It is a tree data structure that is used for the partition of three-dimensional space. What most of us don’t know is that octrees also have a two-dimensional analog called Quadtrees. Where octrees had eight children for each node, quadtrees limits to four. A two-dimensional space is repeatedly divided into four quadrants where each of which acts as a node with spatial information. The longitude and latitude are represented as cartesian coordinates (x, y), and search the points efficiently.

## When we already have latitudes and longitudes, why do we need quadtrees?

This is a question many people have on their minds. Let’s see what’s the difference when we use quadtrees over longitude and latitude.

While using coordinates of latitude and longitude, we need to use Euclidean distance to calculate close location points. However, when there are large data sets, it shows CPU-intensive nature. This makes the use of coordinates in the real-time system not scalable.

Geohashing also helps us save extra computational operations because it only divides a node after a certain threshold. In addition, with the use of some mapping algorithms like the Hilbert Curve, the range query performance is also improved.

![Quadtrees](https://miro.medium.com/max/1100/1*2ygRFNFxcxp9JVT1Kkg8xw.webp)

## Types of Quadtrees

The types of quadtrees depend on the data that needs to be represented like areas, points, lines, curves, etc. Some of the most common quadtrees types are listed below: -

- Edge Quadtrees
- Point Quadtrees
- Point-region (PR) Quadtrees
- Compressed Quadtrees
- Polygonal Map (PM) Quadtrees

## Use Cases of Quadtrees

Let’s view some of the use cases of quadtrees.

- Spatial Indexing
- Range Queries
- InDriver, Pathao, etc. (location-based services)
- Mesh Generation
- Computer Graphics
- Sparse Data Storage
- Image representation, processing, and compression
