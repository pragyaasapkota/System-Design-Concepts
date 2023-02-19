# Database Indexes

![Database Indexes](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*rQQQGTJaviMUQ3mYRllWBg.jpeg)

The indexes in a database are a data structure that acts like a table of contents to point us toward the data location. It improves data retrieval speed since we can locate the data easily without looking at every row in the database table. However, for speedy data retrieval, the use of indexes compromises with increased storage and slower write operations. The latter includes writing the data and updating the index subsequently.

The indexes can have multiple columns of the database table where there are ordered records for efficient search. These columns have a pointer to the whole row of the index. Further, we can use indexes for giving different views of the same data. For example, if you have a larger dataset, the data can be sorted easily without making multiple copies of them.

An index can either be dense or sparse — depending on its qualities.

## Dense Index

The index is dense if the record is created for every row present in the table. Each record has searched key value and a pointer to the data which means the maintenance work at write-time is increased with a dense index when compared to a sparse index. The database should help it with inserts, updates, and deletes since every row needs an entry. This uses more memory but balances it with letting the search easy with binary search. In addition, the data don’t have extra requirements tasks in the dense index.

## Sparse Index

Moving on, the sparse index works on selected records only. It requires less maintenance since it is just a little subset of all the rows. It consequently speeds up the inserts, updates, and deletes while the memory used is comparatively less. The worse thing about the sparse index is that it slows down the data retrieval process by scanning the page first and following it with the binary search. If you have ordered data, the sparse index can be an option as well.

## Conclusion

Database Indexes are a good way to better data retrieval options and can be used for your large sets of databases as well. With the two columns with the primary key in the first and the pointer in another, the data records search becomes easy and efficient.
