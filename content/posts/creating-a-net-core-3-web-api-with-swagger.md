---
title: Creating a .Net Core 3 web API with Swagger
date: '2019-10-10T22:07:19-03:00'
categories:
  - coding
tags:
  - .Net Core
  - Swagger
  - Visual Studio 2019
keywords:
  - programming
  - coding
  - development
  - .Net Core
  - Swagger
  - Visual Studio 2019
autoThumbnailImage: true
thumbnailImagePosition: top
thumbnailImage: /images/uploads/titulo.jpg
coverImage: ''
---
![titulo](/images/uploads/titulo.jpg)

The full example can be downloaded in this GitHub repository: [NetCore3-Swagger](https://github.com/lucianopereira86/NetCore3-Swagger).

## Technologies

* [.Net Core 3](https://docs.microsoft.com/pt-br/dotnet/core/whats-new/dotnet-core-3-0)
* [Visual Studio 2019](https://visualstudio.microsoft.com/pt-br/vs/)
* [Swagger](https://docs.microsoft.com/pt-br/aspnet/core/tutorials/getting-started-with-swashbuckle?view=aspnetcore-3.0&tabs=visual-studio)

## Topics

* [.Net Core 3](#net-core-3)
* [Swagger](#swagger)

### .Net Core 3

Download the Visual Studio 2019 [here](https://visualstudio.microsoft.com/pt-br/vs/) and install it.

Create a new project:

![netcore01](/images/uploads/netcore01.jpg)

Choose ASP.Net Core Web Application:

![netcore02](/images/uploads/netcore02.jpg)

Name the project and configure the local path:

![netcore03](/images/uploads/netcore03.jpg)

Select an empty .Net Core project and uncheck the HTTPS and Docker support options:

![netcore04](/images/uploads/netcore04.jpg)

After the solution be compiled, create a folder named "Controllers" and add into it a class named "TestController" with an async method:

![netcore07](/images/uploads/netcore07.jpg)

Now, let's config the "Startup" class:

![netcore08](/images/uploads/netcore08.jpg)

Run the project in debug mode and access the URL below:

```bash
http://localhost:<API-PORT>/api/Test
```

If the "OK!" message be displayed in the browser, our web API is running!  

### Swagger

Inside the Visual Studio 2019, open the Package Manager Console and run the following commands to install the Swashbuckle version compatible with .Net Core 3:

```bash
Install-Package Swashbuckle.AspNetCore -Version 5.0.0-rc3
Install-Package Swashbuckle.AspNetCore.Filters -Version 5.0.0-rc3
Install-Package Swashbuckle.AspNetCore.Annotations -Version 5.0.0-rc3
```

Open the "Startup" class again and modify the "ConfigureServices" method:

![swagger01](/images/uploads/swagger01.jpg)

And the "Configure" method as well:

![swagger02](/images/uploads/swagger02.jpg)

Open the project's properties window, go to "Debug" and type "swagger" inside the input field above the environment variables list:

![swagger04](/images/uploads/swagger04.jpg)

Inside the "TestController", put a simple annotation above the "Get" method:

![swagger03](/images/uploads/swagger03.jpg)

Now, let's run the project again. The Swagger page will open in this URL:

```bash
http://localhost:<API-PORT>/swagger/index.html
```

This will be the result:

![swagger08](/images/uploads/swagger08.jpg)

Try the "Get" method and the "OK!" message will return from the API.

![swagger09](/images/uploads/swagger09.jpg)
