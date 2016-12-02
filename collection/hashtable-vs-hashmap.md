#What is the difference between HashTable and HashMap in Java?

Both `HashTable` and `HashMap` are java collections and implements `java.util.Map` interface. _Difference between HashTable and HashMap_ is the most common interview question. Many of the candidates who face the interview struggle to answer this question.

Here we will not only see the differences between `HashTable` and `HashMap` but also similarities between these two.

##Difference between `HashTable` and `HashMap` in Java

- **Thread Safe:** `HashTable` is thread-safe and can be shared between multiple threads but `HashMap` is not thread-safe and cannot be shared between multiple threads without proper synchronization. To use `HashMap` in multi-threading you need to synchronize the `HashMap` as `Collections.synchronizeMap(hashMap)` or if you are using Java 5+ then you can consider `ConcurrentHashMap`.

- **Null Keys and Values:** Another comparison point here is whether these java collection allows you to null Keys and Values. `HashTable` don't allow you to use null Keys and Values whereas `HashMap` allows you to null keys and values.

- **Order of the Elements:** `HashMap` does not guarantee you the order of the map i.e the order in which you have added the elements in the `HashMap` cannot be retrieved. HashTable retains the order in which it is added.

- **HashTable Enumerator vs HashMap Iterator:** Important difference between `HashTable` and `HashMap` is that Enumerator in `HashTable` is not fail-fast whereas Iterator in `HashMap` is a fail-fast iterator.
 
 **_NOTE:_** _Fail-fast feature is of Iterators. If the map is structurally modified at any time after the iterator is created, except                 through the iterator's own remove method, the iterator will throw a ConcurrentModificationException. Thus, in case of                     concurrent modification, the iterator fails quickly and cleanly, rather than risking arbitrary, non-deterministic behavior                 at an undetermined time in the future. Fail-fast behaviour of iterator is not a guaranteed behavior and will be done by JVM               on best effort._
 
- **Performance of HashTable Vs HashMap:** As `HashMap` is sychronized and thread-safe, performance of `HashTable` is compromised whereas `HashMap` gives better performance than `HashTable` because of lack of sychronization. In single-threaded environment it is recommended to use `HashMap` over `HashTable`.
        
