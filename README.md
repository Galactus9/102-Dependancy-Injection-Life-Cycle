# Dependancy-Injection-Life-Cycle

This project demonstrates the concept of Dependency Injection (DI) and its life cycle in a C# Web API. The goal of this project is to help developers understand how DI works and how it impacts the life cycle of services in a C# Web API application.

## Introduction

Dependency Injection is a software design pattern that promotes loose coupling between components by allowing the injection of dependencies from external sources. In this project, we use DI to manage the life cycle of services in a C# Web API application.

## Dependency Injection

Dependency Injection is achieved through the use of a DI container, which is responsible for creating and managing instances of services and their dependencies. In this project, we use the built-in DI container provided by ASP.NET Core.

## Service Life Cycle

In a C# Web API application, services can have different life cycles based on their registration type with the DI container. The three main life cycle types are:
1. Transient: A new instance of the service is created every time it is requested.
2. Scoped: A new instance of the service is created per HTTP request.
3. Singleton: Only one instance of the service is created throughout the lifetime of the application.


## Output Explanation

When you hit the API controller, you will see an output like the following:

```
"_transientService1 Trans Test1 9a4420ce-4152-4200-8157-ff1886e17654",
"_transientService2 Trans Test2 ecb982d8-ff3c-4eb4-9666-99fb1fe12440",
"_scopedService1 Scoped Test2 b1f477fc-b592-4378-bfab-39e0d370c00d",
"_scopedService2 Scoped Test2 b1f477fc-b592-4378-bfab-39e0d370c00d",
"_singletonService1 16a723c0-a7a9-4d58-b12d-29ba1047b8de",
"_singletonService2 16a723c0-a7a9-4d58-b12d-29ba1047b8de"
```

1 Transient Services:

- Transient services are created anew every time they are requested, which is evident from the different unique identifiers (GUIDs) for each service instance.
- This behavior ensures that each service instance operates independently and does not retain any state across different parts of the application.

2 Scoped Services:

- Scoped services are created once per HTTP request and are reused within the same request context.
- In this output, both _scopedService1 and _scopedService2 share the same GUID, indicating that they are the same instance, created once for the current HTTP request.
- This behavior helps reduce unnecessary object creation - and promotes better performance within a single request.

3 Singleton Services:

- Singleton services are created only once throughout the lifetime of the application and are reused across all requests.
- Both _singletonService1 and _singletonService2 share the same GUID, demonstrating that they represent the same instance created at the application startup.
- Singleton services are useful when you need to share stateful objects across multiple parts of the application, such as configuration settings or data that should remain consistent.


Analyzing the output, you can observe how the DI container adheres to the defined life cycle for each service type. Understanding these life cycle behaviors is crucial for designing and optimizing applications that effectively manage resources and performance.


