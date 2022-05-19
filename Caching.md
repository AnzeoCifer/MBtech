# Caching

Cache is a technique of storing a copy of data temporarily in rapidly accessible storage memory. Cache stores most recently used words in small memory to increase the speed at which data is accessed. It acts as a buffer between RAM and CPU and thus increases the speed at which data is available to the processor. Whenever a Processor wants to write a word, it checks to see if the address it wants to write the data to, is present in the cache or not. If the address is present in the cache i.e., Write Hit. We can update the value in the cache and avoid expensive main memory access. But this results in Inconsistent Data Problem. As both cache and main memory have different data, it will cause problems in two or more devices sharing the main memory (as in a multiprocessor system). There are two ways of updating the main memory after using the data in the cache, they are - Write through and Write back.
  
  ##### Write Through
    
In write-through, data is simultaneously updated to cache and memory. This process is simpler and more reliable. But it is mostly efficient when it comes to less amount of changes being made to the caches memory. As data writing creates a latency, multiple changes being made will result in higher latency which goes against the aim of caching.
  
  ##### Write Back
    
The data is updated only in the cache and updated into the memory at a later time. It only updates the main memory when the cache line is ready to be updated. This is risky as there might be unsaved data which maybe lost in the case of a power outage.
    
  ## Aim of caching.
   * Increase efficiency
   * Reduce process time
   * Avoid load on database
   * Save network call
  ## Different types of caching techniques
   * ### Spatial Caching Technique
     * Caching technique based on locality of data and the 
     * Imports data from the local cluster of the previous hit.
     * Based on the theory that the next required data set would be available in the current data cluster.
     * Makes hits on the local cluster based on the most recenlty used data.
     * Based on **Spatial Locality**. In Spatial Locality, nearby instructions to recently executed instruction are likely to be executed soon.**It is also known as locality in space**.	It only refers to data item which are closed together in memory.
   * ### Temportal Caching Technique
     * Caching technique based on the frequency of the data usage.
     * Creates a data set at faster levels of cache memory.
     * Based on the theory that the most frequently data set might be required further down the process.
     * Imports a data set, then based on the usage of the data, keeps the most used data in faster levels of the cache memory.
     * Based on **Temporal Locality**. In Temporal Locality, a recently executed instruction is likely to be executed again very soon. **It is also known as locality in time**. It repeatedly refers to same data in short time span.
   * ### Distributed Caching Technique
     * A combination of both spatial and temporal caching techniques.
     * In distributed caching, multiple applications retrieve data from a server cache. Therefore, to process such requests at a higher speed multiple instances of the cache memory must be created. Those instances are then used to cater to the needs of the requesting applications.
     * It is used to reduced the load on the server database.
     * The instances created in the process are saved at multiple nodes to which the applications are connected to.
     * The theory behind this type of caching technique is "**Low latency, high volume**" i.e., complete processing of data for multiple applications in the lowest time frame possible.
     
  ## Eviction Policy
  
Based on the above caching techniques many eviction policies can be created which can thus be used to update the cache. The following points discuss the various eviction policies:

   * #### LRU (Least Recently Used)

      * LRU is the most popular policy due to several reasons. It is simple, has good runtime performance, and a decent hit rate in common workloads. As the name suggests this policy evicts the least recently used item first from the cache. When the cache becomes full, it removes the least recently used data and the latest entry is added into the cache. 
      * This type of eviction policy can be said to be based losely on the temporal caching technique.
      * We can implement the LRU using a doubly-linked list and a hash function containing the reference of the node in the list. 

   * #### LFU (Least Frequently Used)

      * This policy counts the frequency of each requested item and discards the least frequent one from the cache. So here we count the number of times a data item is accessed, and we keep track of the frequency for each item. When the cache size reaches a given threshold we remove the entry with the lowest frequency. 
      * This type of eviction policy can be said to be based on the temporal caching technique.
 
   * #### MRU (Most Recently Used)

      * This approach removes the most recently used item from the cache. We give preference to the older item to remain in the cache. This approach is suitable in cases where a user is less interested in checking out the latest data or item. 
      * This kind of eviction policy is not suitable for process that require the latest data to complete the task at hand. This is mainly used in cases where the user is more interested in the older data sets. For example, user's inventory in games.

   * #### Random Replacement

      * As the name suggests we randomly select an item and discard it from the cache to make space whenever necessary. 
      * This is an unordered eviction without a proper pattern, thus it is a risk to use this policy.


## References

  * [Caching Techniques](https://www.youtube.com/watch?v=ccemOqDrc2I)
  * [Distributed Caching](https://www.youtube.com/watch?v=U3RkDLtS7uY)
  * [Locality](https://www.geeksforgeeks.org/difference-between-spatial-locality-and-temporal-locality/)
  * [Caches basics](https://www.geeksforgeeks.org/caching-system-design-concept-for-beginners/?ref=gcse)

