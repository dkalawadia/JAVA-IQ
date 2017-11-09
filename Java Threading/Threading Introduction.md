# Java Threading

> Adapted from the [Oracle tutorial](https://docs.oracle.com/javase/tutorial/essential/concurrency/index.html) on Java concurrency.

In concurrent programming, there are two basic units of execution - processes & threads. A process has a self-contained execution environment and is often seen as synonymous with programs and applications (though this may not be true). Inter-process communication usually happens via pipes or sockets as processes have their own memory space. Threads, on the other hand, exist within a process (each process has at least one) and share the process's resources. From the application programmer's point of view, you start with just one `main` thread (not counting "system" threads for memory management, signal handling etc.), which has the ability to create new threads.

## Why do you use Threads in Java ?

- To make a task run in parallel to another task e.g Editing the Word document and auto saving the document
- Multiple threads in Java is to used to improve throughput of the application by utilizing full CPU power.
- You can also use multiple threads to reduce response time by doing fast computation by dividing a big problem into smaller chunks and processing them by using multiple threads.

## What are the different ways to create Thread in Java?

There is exactly one way to create a new thread in Java and that is to instantiate `java.lang.Thread` (to actually run that thread you also need to call `start()`).

Everything else that creates threads in Java code falls back to this one way behind the cover (e.g. a `ThreadFactory` implementation will instantiate `Thread` objects at some point).

There are two different ways to specify which code to run in that Thread:

- Implement the interface `java.lang.Runnable` and pass an instance of the class implementing it to the `Thread` constructor.
- Extend `Thread` itself and override its `run()` method.

The first approach (implementing Runnable) is usually considered the more correct approach because you don't usually create a new "kind" of Thread, but simply want to run some code (i.e. a Runnable) in a dedicated thread.

## What is difference between Thread class `start()` and `run()` method in Java?

- Main difference is that when program calls `start()` method a new Thread is created and code inside `run()` method is executed in new Thread while if you call `run()` method directly no new Thread is created and code inside run() will execute on current Thread.
- Another difference between `start()` vs `run()` in Java thread is that you can not call `start()` method twice on thread object. once started, second call of `start()` will throw IllegalStateException in Java while you can call `run()` method twice.

