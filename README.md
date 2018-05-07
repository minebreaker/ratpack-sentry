Using Sentry in Ratpack application

* [Ratpack](https://ratpack.io)
* [Sentry](https://sentry.io)

Sentry by default uses `ThreadLocalContextManager`,
which means Ratpack context very well.
`RatpackSentryContextManager` provides `Context`s per
Ratpack Execution.
If not in Execution, returns singleton `Context`.


## Set up

Specify `SentryClientFactory` for `RatpackSentryClientFactory`.

Manually call `Sentry.init()`

```java
public class Main {
    // your application entry point
    public static void main(String[] args){
        Sentry.init(new RatpackSentryClientFactory());

        RatpackServer.start( /* ... */);
    }
}
```

or specify `factory` parameter in `sentry.properties`

[Docs](https://docs.sentry.io/clients/java/config/#custom-functionality)

```properties:sentry.properties
factory
```
