# Why is String Immutable or Final in Java?

In java `String` objects are cached in String pool and these cached String literals are shared between multiple thread. If String wouldn't have been immutable or Final then there would have been risk, where one thread's action would affect all other threads.
