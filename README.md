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

This output represents the instances of the services created during the API request. The GUIDs (e.g., `9a4420ce-4152-4200-8157-ff1886e17654`) are unique identifiers for each service instance.

## License

This project is licensed under the MIT License. See the `LICENSE.md` file for details.
