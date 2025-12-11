# Cache

Persists the data set in some storage. The storage type can be tweaked by specifying/combining parameters.

Overall, the configuration gives the ability to define:

1. Whether to use memory.

2. Whether to drop the RDD to disk if it falls out of memory.

3. Whether to keep the data in memory in a serialized format.

4. Whether to replicate the RDD partitions on multiple nodes.

By default the cache parameters are set to reflect StorageLevel.MEMORY_AND_DISK mode.

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Use disk** | `useDisk` | Save data on disc. |
| **Use memory** | `useMemory` | Data should be saved in RAM. |
| **Use off heap** | `useOffHeap` | Objects will be managed by garbage collector. |
| **Deserialized** | `deserialized` | Objects should be automatically serialized. |
| **Replication** | `replication` | Replicate the RDD partitions on multiple nodes. |

