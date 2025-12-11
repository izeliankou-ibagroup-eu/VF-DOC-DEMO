# Cache Stage.

The *Cache* stage persists dataset in some storage. You can tweak the storage type by specifying parameters.

The configuration gives you the ability to define:

* Whether to use memory.
* Whether to drop the RDD to disk if it falls out of memory.
* Whether to keep the data in memory in a serialized format.
* Whether to replicate the RDD partitions on multiple nodes.

![](../../../../assets/user-guide-img/image38.png)
