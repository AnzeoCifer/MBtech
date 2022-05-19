# Caching
     Cache is a technique of storing a copy of data temporarily in rapidly accessible storage memory. Cache stores most recently used words in small memory to increase the speed at which data is accessed. It acts as a buffer between RAM and CPU and thus increases the speed at which data is available to the processor. 

Whenever a Processor wants to write a word, it checks to see if the address it wants to write the data to, is present in the cache or not. If the address is present in the cache i.e., Write Hit. 

We can update the value in the cache and avoid expensive main memory access. But this results in Inconsistent Data Problem. As both cache and main memory have different data, it will cause problems in two or more devices sharing the main memory (as in a multiprocessor system). 
This is where Write Through and Write Back comes into the picture. 

  ## Aim of caching.
   * Increase efficiency
   * Reduce process time
   * Avoid load on database
   * Save network call
  ## Different types of caching techniques
   * ### Spatial Caching
     * Caching technique based on locality of data and the 
     * Imports data from the local cluster of the previous hit.
     * Based on the theory that the next required data set would be available in the current data cluster.
     * Makes hits on the local cluster based on the most recenlty used data.
   * ### Temportal Caching
     * Caching technique based on the frequency of the data usage.
     * Creates a data set at faster levels of cache memory.
     * Based on the theory that the most frequently data set might be required further down the process.
     * Imports a data set, then based on the usage of the data, keeps the most used data in faster levels of the cache memory.
   * ### Distributed Caching
     * A combination of both spatial and temporal caching techniques.
     * In distributed caching, multiple applications retrieve data from a server cache. Therefore, to process such requests at a higher speed multiple instances of the cache memory must be created. Those instances are then used to cater to the needs of the requesting applications.
     * It is used to reduced the load on the server database.
     * The instances created in the process are saved at multiple nodes to which the applications are connected to.
     * The theory behind this type of caching technique is "**Low latency, high volume**" i.e., complete processing of data for multiple applications in the lowest time frame possible.

