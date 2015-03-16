---
layout: post
title: Netflix Stack - Hystrix
---

## What does it do?

### 1) Latency and Fault Tolerance
Fallbacks and graceful degradation. Fail fast and rapid recovery. Thread and semaphore isolation with circuit breakers.

### 2) Realtime Operations
Realtime monitoring and configuration changes. Watch service and property changes take effect immediately as they spread across a fleet. Be alerted, make decisions, affect change and see results in seconds.

### 3) Concurrency
Parallel execution. Concurrency aware request caching. Automated batching through request collapsing.

Sample:

```java
public class CommandHelloWorld extends HystrixCommand<String> {
    private final String name;

    public CommandHelloWorld(String name) {
        super(HystrixCommandGroupKey.Factory.asKey("ExampleGroup"));
        this.name = name;
    }

    @Override
    protected String run() {
        return "Hello " + name + "!";
    }
}
```

This command could be used like this:

```java
String s = new CommandHelloWorld("Bob").execute();
Future<String> s = new CommandHelloWorld("Bob").queue();
Observable<String> s = new CommandHelloWorld("Bob").observe();
```


## References

- https://github.com/Netflix/Hystrix