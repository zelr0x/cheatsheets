## Tasks
__Runnable__ (functional interface: `run()`) encapsulates a task that runs asynchronously; sort of an asynchronous method with no parameters and no return value. run() should not be called directly - it will execute the task in the same thread. Instead, pass runnable to a `Thread` constructor and call `thread.start()`.


__Callable<V>__ (functional interface: `call()`) similar to a Runnable, but it returns a value. The type parameter is the type of the returned value. To convert `Runnable` to `Callable` (returning `null`) - use static `Executors.callable(Runnable)`


__Future__ (interface) holds the result of an asynchronous computation. You start a computation, give someone the Future object, and forget about it. The owner of the Future object can obtain the result when it is ready. To retrieve the result, Future has blocking `get()` methods (with and without timeout parameter; the one with the timer throws `TimeoutException`). It also has booleans `isDone()` and `isCancelled()`.


A task can be cancelled with `task.cancel()` only if mayInterrupt parameter is set to true. If a Future object does not know on which thread the task is executed, or if the task does not monitor the interrupted status of the thread on which it executes, cancellation will have no effect.


__FutureTask__ implements both the Future and Runnable interfaces. A `Callable` can be wrapped with `FutureTask` and passed to a thread:
```java
Callable<Integer> task = () -> ...;
var futureTask = new FutureTask<Integer>(task);
var thread = new Thread(futureTask); // ok since Thread can accept Runnable
thread.start();
Integer result = futureTask.get(); // InterruptedException and ExecutionException may be thrown
```

## Executors

__Executor__ (functional interface: `execute()`) is more common way to execute a `Callable`. An object that executes submitted `Runnable` tasks. Provides a way of decoupling task submission from the mechanics of how each task will be run, including details of thread use, scheduling, etc.  Normally used instead of explicitly creating threads:
```java
Executor executor = ...;
executor.execute(new RunnableTask1());
```
anExecutor is an object of a class implementing Executor (e.g. `ForkJoinPool`) or one of its subinterfaces such as `ExecutorService`.


__ExecutorService__ (interface, extends `Executor`)
1. Create – call factory method Executors.newX() where X is a name of the thread pool of choice e.g. `CachedThreadPool` (`Executors.newCachedThreadPool()`), `FixedThreadPool`, etc.
2. Run tasks – submit a `Runnable` or `Callable` to an `ExecutorService` with one of the following methods:
```java
Future<T> submit(Callable<T> task);
Future<?> submit(Runnable task); // get() on this one always returns null
Future<T> submit(Runnable task, T result); // returns result upon completion
```
3. Get results – handle Future objects returned by submit. For that results of submit should be stored somewhere
4. Shutdown – when a pool has served its purpose, call `pool.shutdown()` which will wait for the current tasks to complete but will not accept the new submissions.
`pool.shutdownNow()` will try to cancel the tasks.

Executors have more useful methods, for example:
```java
// Submit all tasks and return the result of the first completed.
T executor.invokeAny(Collection<? extends Callable<T>> tasks)
// Submit all tasks and return the results.
List<Future<T>> executor.invokeAll(Collection<? extends Callable<T>> tasks)
```

### ForkJoinPool
// TODO:

__ForkJoinPool__

__ForkJoinTask<V>__ (_abstract_, implements `Future<V>`) –  base class for tasks that run within a ForkJoinPool; a thread-like entity that is much lighter weight than a normal thread. Key methods: `fork()` and `join()` or wrappers such as `invoke()`

__RecursiveAction__ (_abstract_, extends `ForkJoinTask<Void>`): `protected abstract void compute()`, tasks of that type always return null

__RecursiveTask<V>__ (_abstract_, extends `ForkJoinTask<V>`): `protected abstract V compute()`
