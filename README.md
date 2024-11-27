## Middleware
https://dotnettutorials.net/lesson/asp-net-core-middleware-components/

## .net core
https://dotnettutorials.net/course/asp-net-core-tutorials/
https://learn.microsoft.com/en-us/aspnet/core/introduction-to-aspnet-core?view=aspnetcore-8.0
https://www.hackertrail.com/talent/backend/net-core-interview-questions-answers/
https://www.fullstack.cafe/blog/dot-net-core-interview-questions-and-answers
https://interviewprep.org/net-core-interview-questions/

## .NET Core Framework
- Open source
- cross palatform
- allows to create and run applications into different platforms - windows, linux etc
- provides various built in tools -> packages. libraries, API, DI, etc

## How it works
- develop code for required applications
- compile the code to IL
- CLR will convert IL code to machine code using JIT compiler
- execute the executable on any specific architecture.

## Features
- Cross platforms
- flexible
- open source
- support fir microservices
- support for mobile applications

## Core SDK VS Core runtime
- SDK is used to build applications, runtime is use to run the applications
- SDK is collection of tools, libraries used to develop applications like CLI, compiler, wheer as runtime is like virtual machine consisting of runtimes libraries and helps you run those applications.

## Advantages 
- Cross platform - develop and deploy applications on verious platforms using docker, kubernetes etc
- flexible
- open source - source code and documentation is available easily and free over github
- secure - easy to incorporate security measures for authentication and authorization
- High peformance - GC has been improved
- Flexible - we can use any db and infrastructure as per choice.

## Kestrel 
- open source, I/O based, event driven, cross platform and asynchronous server which hosts .NET applications.
- default server for .net core., so compatible with all platforms and versions
- it faces all the internet and http web requests from clients directly. 
- it is listening server with Command Line Interface.

## Advantages of Kestrel
- light weight
- cross platform
- supports https
- easy configuration

## Middleware
- layer, software, class
- through which all requests and responses have o go through
- is assembled of many delegates in an application pipeline
- each delegate in pipeline ecides
  - to pass the request to the next component
  - peform some processing on the request before or after pasing it.

## Razor pages
- new server-side framework which works on a page-based approach to render applications in .NET Core. 
- They are stored as a physical .cshtmlfile.
- They have the HTML and code in a single file, without the need to maintain separate controllers, view models, action methods, etc. 
- We can also have the code separate from the HTML in a different file which is attached to the Razor Page.

## Service lifetimes in .NET Core
- Transient Service: Instance is created each time it is requested.
- Scoped Service: User-specific instance is created once per user and shared across all the requests.
- Singleton Service: Single Instance is created once a lifetime of the application.

## .NET Core VS .Net Framework
- .NET core is cross platform open source, .NEt framework has few components as open source
- .NEt Core supports microservices.
- .net core : no support for desktop applications
- .net core: light weight for CLI
- .net core : easy intergration with Moder Ui framework - angular, react etc
- .net core: default server: Kestrel
- .net core: loosely coupled, easily testable
- .net core: support for various IDEs

## Docker in .NET Core
- open platform for developing, shipping, and running applications.
- allows you to quickly isolate your applications from the infrastructure to transmit software.
- You should leverage this feature for managing infrastructure and deploying codes fast. It would help reduce the time needed between writing and running codes in infrastructure.
- Take care following points while using Docker in .NET Core
  - You can use the Docker client's CLI for managing images and containers
  - You must adequately integrate Docker images, containers, and registries while designing and containerising applications or microservices
  - Use Dockerfile for rebuilding images and distribute them with others

## What is Hosting Environment Management?
- It is a new feature of .NET Core that permits you to work with multiple environments with no friction. 
- You can use this feature through the available interface, Hosting Environment. 
- The interface has been open since the first run of the application. 
- Its execution depends on the environment variable and switch between the configuration files during runtime.
- The interface reads a specific environment variable named "ASPNETCORE_ENVIRONMENT" and checks its value. Check its following values:
  - If value: Development – You are running the application in Dev mode
  - If value: Staging – You are running the application in staging mode
- This feature permits you to manage the different environments as well.

## Startup Class:
- The Startup is a critical class in the application. The following points make it imperative:
- It describes the pipeline of the web applications.
- You can use individual startups for each environment.
- It helps to perform the registration of all required middleware components.
- Reading and checking thousands of lines in different environments is tough, but you can use various startup classes to resolve it.

## State management
- Is a kind of state control object to control the states of the object during different processes. 
- Since stateless protocol, HTTP has been used, which is unable to retain user values; thus, different methods have been used to store and preserve the user data between requests.
  - Cookies -> HTTP Cookies, Server-side app code
  - Session state -> HTTP Cookies, Server-side app code
  - Temp Data -> HTTP Cookies, Session State
  - Query Strings -> HTTP Query Strings
  - Hidden Fields -> HTTP Form Fields
  - HTTPContext.Items -> Server-side app code
  - Cache -> Server-side app code

## What is the best way to manage errors in .NET Core?
- There are mainly four ways to manage errors in .NET Core for web APIs.
  - Developer Exception Page
  - Exception Handler Page
  - Exception Handle Lambda
  - UseStatusCodePages
- But, in all these four, the best way is "Developer Exception Page" as it provides detailed information (stacks, query string parameters, headers, cookies) about unhandled request exceptions. You can easily enable this page by running your applications in the development environment. This page runs early in the middleware pipeline, so you can easily catch the exception in middleware.

## Response caching in .NET Core
  - During response caching, cache-related headers are mentioned in the HTTP responses of .NET Core MVC actions. 
  - Using these headers, we can specify how the client/proxy machine will cache responses to requests. 
  - This, in turn, reduces the number of client/proxy requests to the web server because the responses are sent from the cache itself.
  - Example -  the first request has a complete cycle from client browser to proxy server and then subsequently to web server. Now, the proxy server has stored the response in the cache. For all the subsequent requests, the proxy server sends the response from the cache itself. Hence, the number of proxy/client requests to the web server is reduced.

## Generic host in .NET Core
- The generic host was previously present as ‘Web Host’, in .NET Core for web applications. 
- Later, the ‘Web Host’ was deprecated and a generic host was introduced to cater to the web, Windows, Linux, and console applications.
- Whenever a new application is started we are required to take care of the below points:
  - Dependency Injection
  - Configuration
  - Logging
  - Service lifetime management
- .NET generic host called ‘HostBuilder’ helps us to manage all the above tasks since it is built on the original abstraction of these tools.

## Routing in .NET Core
- It is a process through which the incoming requests are mapped to the corresponding controllers and actions.  
- The .NET Core MVC has a routing middleware to perform this task. This middleware matches the incoming HTTP requests to the executable request-handling code. We can define the routing in the middleware pipeline in the ‘Startup.Configure’ file.
- There are two methods or pair of middleware to define routing:
  - UseRouting: Adds route which matches the middleware pipeline.
  - UseEndpoints: Adds end execution point to the middleware pipeline and runs the delegate of the endpoint.

## Dependency Injection in .NET Core
- .NET Core has been designed to support Dependency Injection(DI), which means the application is loosely coupled. It is a technique to introduce Inversion Control(IoC) between the classes and their dependencies. 
- the object maintains only that dependency which is required during that particular task. 
- A dependency is an object on which another object depends, by dependency injection, the application becomes better testable, maintainable, and reusable.
- Dependency Injection has three steps:
  - An interface or base class is present to provide an abstraction for dependency implementation.
  - Dependency is registered in a service container, a built-in container IServiceProvider is present in .NET Core.
  - Service is injected into the constructor of the class where dependency is used.
- Advantages of Dependency Injection:
  - Code is flexible, implementation can be changed without much overhead.
  - Code becomes easy to test because of the use of interfaces.
  - Code is loosely coupled, clean, and easy to maintain.

## ASP.NET VS ASP.NET MVC
- ASP.NET is a web platform, whereas ASP.NET MVC is an application framework for building web applications.
- ASP.NET offers a layer that resides on the web server's top layer for creating web applications and services. Conversely, ASP.NET MVC framework stays on top of ASP.NET to design web applications with the help of ASP.NET's APIs.
- ASP.NET is based on a simple event-driven programming model, whereas ASP.NET MVC is based on the "Model-View-Controller" architectural model.

## View component
- new feature that has been considered a powerful version of partial views. 
- It is used for solving many problems. 
- The primary function of this feature is to split the complex views into reusable parts. 
- With the help of partial views, you can also access the parent page's view model.
- But, one drawback of this feature is that it can't access the page model and can operate on the passed arguments. Thus, the best application of this feature is to use it to render reusable pieces of pages that might consist of logic. Use this feature through dependency injection, which makes it robust and reusable.

## How to intercept exceptions using ASP.NET MVC?
- An intercepting exception is an essential part of application development and execution. The exception handling's job is to respond to exceptional conditions. ASP.NET MVC has various ways to intercept exceptions, including
  - HandleError attribute on controllers and action method – A simple method to handle errors and exception
  - Try-catch-finally – A simple three blocks to catch the exception
  - Overriding OnException Method – A void method that takes an argument as an object of ExceptionContext to manage exception
  - Setting a goal exception handling filter – You have to take care of HandleErrorAttribute and need to add it RegisterGlobalFilters
  - Extending HandleErrorAttribute – It permits you to create your Exception Handler to manage the errors

## Why use an area in ASP.NET MVC?
- Physical grouping of features in large complex applications
- Each area has its own MVC folder structure.

## ViewData VS ViewBag
- ViewData and ViewBag in ASP.NET MVC are used for transferring data from controller to view. Below are the differences between them:
- ViewData is a dictionary object of the ‘ViewDataDictionary’ class having key-value where as ViewBag is a wrapper around ViewData and is a dynamic property. 
- Viewdata :Faster than ViewBag. ViwBag : Slower than ViewData. 
- ViewData: Type conversion code is required. ViewBag : Dynamic hence type conversion code is not required. 

## .NET Standard?
- .NET Standard is a formal specification of .NET APIs that are intended to be available on all .NET implementations. 
- It’s a standard library that any .NET platform has to implement. 
- This unifies the .NET platforms and prevents future fragmentation.

## How does .NET Core support the microservices architecture?
- .NET Core provides a lightweight, cross-platform, and high-performance framework that’s ideal for microservices. 
- It allows running microservices in Docker containers and Kubernetes for orchestration, and also supports RESTful services via ASP.NET Core Web API.    

## Entity Framework Core
- Entity Framework Core (EF Core) is a lightweight, extensible, open-source, and cross-platform version of Entity Framework data access technology. 
- It’s an ORM (Object-Relational Mapper) enabling .NET developers to work with a database using .NET objects.

## What are some ways to improve performance in .NET Core applications?
- Use in-memory caching or distributed caching.
- Optimize data access: Use LINQ efficiently, and do not retrieve data that is not needed.
- Use the latest version of .NET Core: Each version comes with its performance improvements.

## What is the difference between ‘appsettings.json’ and ‘secrets.json’ files in ASP.NET Core?
-‘appsettings.json’ 
  - is used to store application settings, such as connection strings, logging configuration, etc. 
  - These are typically checked into source control. 
- ‘secrets.json’ 
  - is used to store sensitive data, like API keys and passwords, 
  - that should not be checked into source control.

## Can you explain how exception handling works in ASP.NET Core?
- Exception handling in ASP.NET Core can be done using middleware. 
- The ‘UseExceptionHandler’ middleware is built-in and can catch exceptions, log them, reset the request path, and re-execute the request. 
- The ‘Developer Exception Page’ middleware can also be used to display detailed exception information in a development environment.

## What is SignalR in the context of ASP.NET Core?
- ASP.NET Core SignalR is an open-source library that simplifies adding real-time web functionality to applications.
- Real-time web functionality is the ability to have server-side code push content to the connected clients instantly as it becomes available, instead of having the server wait for a client to request new data. 
- SignalR supports WebSockets protocol and falls back to other compatible techniques when it’s not available.

## What is Swagger and how is it used in .NET Core?
    - Swagger, also known as OpenAPI, is a tool used for understanding and documenting RESTful APIs. 
    - In .NET Core, you can integrate Swagger using the Swashbuckle NuGet package. It creates a JSON schema that stores API documentation and presents it via a beautiful UI for easy understanding.


## Can you discuss some of the security measures you would put in place when developing a .NET Core web application?
- Some of the security measures include:
  - Use of HTTPS and enforcing SSL.
  - Implementing Cross-Site Scripting (XSS) protection and Cross-Site Request Forgery (CSRF) protection.
  - Using the principle of least privilege in database connections.
  - Implementing authentication and authorization effectively using ASP.NET Core Identity.
  - Encrypting sensitive data in configuration files.

## Host in .NET Core?
- A host is an object that encapsulates an app’s resources, such as an ILogger, IConfiguration, and an IHostedService implementation. 
- When a host starts, it calls IHostedService.StartAsync on each implementation of IHostedService that’s found in the service container’s service collection.


## What are some use cases for using the ‘IOptions’ interface?
- The IOptions interface is used to retrieve the settings from the appsettings.json file or other configuration sources. 
- It’s especially useful when you need to access a certain configuration setting multiple times in the code, and the configuration might change, requiring the app to use the new settings.

## Can you explain what Blazor is in the context of .NET Core?
- Blazor is a .NET Core-based web framework for building Single Page Applications (SPAs) using C# instead of JavaScript. 
- It enables developers to build full-stack web applications using .NET and WebAssembly (WASM).

## What are Async Streams in C# and .NET Core?
- Asynchronous streams, introduced in C# 8.0, are a type of stream that can use async-await syntax to work with streams of data. 
- This feature is particularly useful for situations where you have a stream of data that arrives asynchronously (for example, data coming from a cloud platform).

## How can you create a Worker Service in .NET Core?
- A Worker Service in .NET Core is a console application that runs as a service, allowing you to perform tasks in the background, like processing CPU-intensive data or communicating with databases and APIs. You can create a Worker Service by using the Worker Service template in the .NET CLI with the following command:
  dotnet new worker -n MyWorkerService
- This command creates a new Worker Service project in a new directory named MyWorkerService.
- The Worker class, derived from the BackgroundService abstract class, is where the background task’s logic is defined. 
- It includes a ExecuteAsync method that is run when the service starts. 
- Here, you can define operations to be performed when the service is running. 
- The Stopping and Stopped methods can also be overridden to define behavior when the service is stopping or has stopped.


## What are the key differences between Entity Framework and Entity Framework Core? How might these differences impact development decisions?
- Entity Framework (EF) and Entity Framework Core (EF Core) are both Object-Relational Mapping (ORM) frameworks, but they have key differences that impact development decisions.
  1. Platforms: EF is limited to .NET Framework, while EF Core supports cross-platform development with .NET Core, .NET Standard, and .NET Framework.
  2. Performance: EF Core has improved performance due to its lightweight and modular architecture compared to EF.
  3. Features: EF Core lacks some features available in EF, such as lazy loading proxies, spatial data types, and hierarchy ID support. However, EF Core introduces new features like global query filters and shadow properties.
  4. Extensibility: EF Core offers better extensibility through custom conventions, metadata API, and pluggable components.
  5. LINQ Queries: EF Core translates more queries into SQL, reducing client-side evaluation, which improves performance.
  6. Database Providers: EF Core supports fewer database providers out-of-the-box but allows for easier third-party provider integratio
