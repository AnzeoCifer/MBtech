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
   * ### Temportal Caching Technique
     * Caching technique based on the frequency of the data usage.
     * Creates a data set at faster levels of cache memory.
     * Based on the theory that the most frequently data set might be required further down the process.
     * Imports a data set, then based on the usage of the data, keeps the most used data in faster levels of the cache memory.
   * ### Distributed Caching Technique
     * A combination of both spatial and temporal caching techniques.
     * In distributed caching, multiple applications retrieve data from a server cache. Therefore, to process such requests at a higher speed multiple instances of the cache memory must be created. Those instances are then used to cater to the needs of the requesting applications.
     * It is used to reduced the load on the server database.
     * The instances created in the process are saved at multiple nodes to which the applications are connected to.
     * The theory behind this type of caching technique is "**Low latency, high volume**" i.e., complete processing of data for multiple applications in the lowest time frame possible.
     
  ## Eviction Policy

We have discussed so many concepts of caching….now you might have one question in your mind. When do we need to make/load an entry into the cache and which data we need to remove from the cache? 

The cache in your system can be full at any point in time. So, we need to use some algorithm or strategy to remove the data from the cache, and we need to load other data that has more probability to be accessed in the future. To make this decision we can use some cache eviction policy. Let’s discuss some cache eviction policy one by one…
 * #### LRU (Least Recently Used)

LRU is the most popular policy due to several reasons. It is simple, has good runtime performance, and a decent hit rate in common workloads. As the name suggests this policy evicts the least recently used item first from the cache. When the cache becomes full, it removes the least recently used data and the latest entry is added into the cache. 

Whenever you need to add the entry to the cache keep it on the top and remove the bottom-most entries from the cache which is least recently used. The top entries are going to be maybe seconds ago and then you keep going down the list minutes ago, hours ago, years ago and then you remove the last e
(which is least recently used). 

Consider the example of any social media site, there is a celebrity who’s made a post or made a comment and everyone wants to pull that comment. So you keep that post on the top of the cache and it stays on the top of the cache depending on how latest the post is. When the post becomes cooler or people stop looking or viewing that post, it keeps getting pushed at the end of the cache, and then it is removed completely from the cache. 

We can implement the LRU using a doubly-linked list and a hash function containing the reference of the node in the list. 
 * #### LFU (Least Frequently Used)

This policy counts the frequency of each requested item and discards the least frequent one from the cache. So here we count the number of times a data item is accessed, and we keep track of the frequency for each item. When the cache size reaches a given threshold we remove the entry with the lowest frequency. 

In real life, we can take the example of typing some texts on your phone. Your phone suggests multiple words when you type something in the text box. Instead of typing the whole word, you have the choice to select one word from these multiple words. In this case, your phone keeps track of the frequency of each word you type and maintains the cache for it. Later the word with the lowest frequency is discarded from the cache when it’s needed. If we find a tie between multiple words then the least recently used word is removed. 
 * #### MRU (Most Recently Used)

This approach removes the most recently used item from the cache. We give preference to the older item to remain in the cache. This approach is suitable in cases where a user is less interested in checking out the latest data or item. Now you might be thinking that most often users are interested in the latest data or entries so where it can be used? Well, you can take the example of the dating app Tinder where MRU can be used.

Tinder maintains the cache of all the potential matches of a user. It doesn’t recommend the same profile to the user when he/she swipes the profile left/right in the application. It will lead to poor user experience if the same profile will be recommended again and again. So tinder removes the profile from the cache which is observed most recently i.e. either left/right-swiped profiles.

* #### Random Replacement

As the name suggests we randomly select an item and discard it from the cache to make space whenever necessary. 

