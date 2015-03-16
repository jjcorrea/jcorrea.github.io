---
layout: post
title: Google Guice
---

> Guice (pronounced 'juice') is a **lightweight dependency injection framework** for Java 6 and above, brought to you by Google

Wiring up the application dependencies and handling all the dependency-related complexity, which comes in several flavors, as 

- **boilerplate code** in sense of maintainability
- a strong upfront **type checking** for antecipating potential issues 
- as well as managing **cross-cutting concerns** (Transactions, Security, Performance...), **scopes**, etc

For solving these sort of problems there is Google Guice.

## Binder

A Binding refers a mapping for an **Interface to its corresponding Implementation**.

## Injector

Injectors take care of **creating and maintaining objects** that are used by the Clients.

```java
Add addObject = injector.getInstance(Add.class)
```

## Module

Modules are objects which will **maintain the set of Bindings**, which defines **how dependencies are resolved**. It is possible to have multiple Modules in an Application. Injectors, in turn, will interact with the Modules to get the possible Bindings. Module is represented by an interface with a method called Module.configure() which should be overridden by the Application to populate the Bindings.


```java
class MyModule extends AbstractModule{
    public void configure(Binder binder){
        // Code that binds information using the various
        // flavours of bind method.
    }
}
```

## Guice

Guice is a class which Clients directly depends upon to interact with other Objects.

```java
MyModule module = new MyModule();
Injector injector = Guice.createInjector(module);
```

## Providers

- Enables to **lazily** resolve dependencies, and **get multiple instances** of a certain type. Kind of factory.

## Scopes

- **Unscoped**: Create / Use / Drop.
- **@Singleton**: One per application
- **@RequestScoped**: One per web or RPC request
- **@SessionScoped**: One per HTTP session (usefull for caching, etc)

## Annotations

### @ImplementedBy

This Annotation points to a Class object that provides Implementation to the interface.

```java
@ImplementedBy(SimpleAdd.class)
interface Add{
    public int add(int a, int b);
}
```

### @Inject

For **injecting instances**, we can use this Inject Annotation.

```java
class Client{
    @Inject
    public Client(MyService service){
    }
}
```

### @ProvidedBy

Assuming that we want to customize the Object creation process for some interface type, then we would depend on Guice Provider mechanism. Let’s say, for Add interface we want AddProvider to create and return objects of type SimpleAdd.

```java
@ProvidedBy(AddProvider.class)
public interface Add{
}
```

### @Singleton

If you want the dependency to be resolved in a single instance for all the application, you need to mark your class with a @Singleton annotation.

```java
@Singleton
public class MyConnection{
    public void connect(){
    }

    public void disconnect(){
    }
}
```

## Examples


### Message services

```java
public interface MessageService { 
    boolean sendMessage(String msg, String receipient);
}
```

Sample implementation:

```java
import javax.inject.Singleton;
//import com.google.inject.Singleton; --> **Guice 3.0** added the support for JSR-330 and we can use annotations from **com.google.inject** or **javax.inject** package.
 
@Singleton
public class EmailService implements MessageService {
    public boolean sendMessage(String msg, String receipient) {
        //some fancy code to send email
    } 
}
```

Let’s say we have another service implementation to send facebook messages.

```java
@Singleton
public class FacebookService implements MessageService {
    public boolean sendMessage(String msg, String receipient) {
        //some complex code to send Facebook message
    }
}
```

Some application which requires the dependency:

```java
public class MyApplication { 
    private MessageService service;
     
//  constructor based injector
//  @Inject
//  public MyApplication(MessageService svc){
//      this.service=svc;
//  }
     
    //setter method injector
    @Inject
    public void setService(MessageService svc){
        this.service=svc;
    }
     
    public boolean sendMessage(String msg, String rec){
        //some business logic here
        return service.sendMessage(msg, rec);
    }
}
```

The bindings (map types to their implementations):

```java
public class AppInjector extends AbstractModule { 
    @Override
    protected void configure() {
        //bind the service to implementation class
        //bind(MessageService.class).to(EmailService.class);
         
        //bind MessageService to Facebook Message implementation
        bind(MessageService.class).to(FacebookService.class);
    }
}
```

Client application:

```java
public class ClientApplication {
    public static void main(String[] args) {
        Injector injector = Guice.createInjector(new AppInjector());                 
        MyApplication app = injector.getInstance(MyApplication.class);         
        app.sendMessage("Hi Pankaj", "pankaj@abc.com");
    }
}
```


## Injection: Constructor vs Method vs Field

**Constructor injection** combines **instantiation with injection**. Most constructors will then assign the parameters to final fields. Works nicely with **unit testing**.

```java
public class RealBillingService implements BillingService {
  private final CreditCardProcessor processorProvider;
  private final TransactionLog transactionLogProvider;

  @Inject
  public RealBillingService(CreditCardProcessor processorProvider, TransactionLog transactionLogProvider) {
    this.processorProvider = processorProvider;
    this.transactionLogProvider = transactionLogProvider;
  }
```

On **Method injection** dependencies take the form of parameters, which the injector resolves before invoking the method.

```java
public class PayPalCreditCardProcessor implements CreditCardProcessor {
  private static final String DEFAULT_API_KEY = "development-use-only";
  private String apiKey = DEFAULT_API_KEY;

  @Inject
  public void setApiKey(@Named("PayPal API key") String apiKey) {
    this.apiKey = apiKey;
  }
```

**Field injection**: This is the most concise injection, but the **least testable**.

```java
public class DatabaseTransactionLogProvider implements Provider<TransactionLog> {
  @Inject Connection connection;

  public TransactionLog get() {
    return new DatabaseTransactionLog(connection);
  }
}
```

## References

- https://github.com/google/guice/wiki/Injections
- http://www.javabeat.net/introduction-to-google-guice/
- http://www.journaldev.com/2403/google-guice-dependency-injection-example-tutorial