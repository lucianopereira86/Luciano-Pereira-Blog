---
title: .Net Core web API - Part 3 - Heroku
date: '2019-10-16T21:25:04-03:00'
categories:
  - .Net Core 3
tags:
  - .Net Core 3
  - Heroku
  - Docker
keywords:
  - .Net Core 3
  - Heroku
  - Docker
autoThumbnailImage: true
thumbnailImagePosition: top
thumbnailImage: /images/uploads/netcore3_heroku_titulo.JPG
coverImage: /images/uploads/netcore3_heroku_titulo.JPG
---
![titulo](/images/uploads/netcore3_heroku_titulo.JPG)

# NetCore3-Heroku

Deploying a .Net Core 3 web API to Heroku by using Docker.

## Technologies

- [.Net Core 3](https://images/uploads.microsoft.com/pt-br/dotnet/core/whats-new/dotnet-core-3-0)
- [Docker](https://www.docker.com/get-started)
- [Heroku](https://www.heroku.com/)

## Before start

This guide is directed for those who have a mininum experience with Docker and a proper environment to run it.

## Topics

- [Heroku](#heroku)
- [.Net Core 3](#net-core-3)
- [Docker](#docker)

### Heroku

Heroku is a cloud platform that allows applications be hosted at will. It's mostly used for web APIs.
Go to [Heroku website](https://signup.heroku.com/login) and sign up or sign in.

In the Dashboard, click on "Create new app".

![heroku01](/images/uploads/netcore3_heroku_heroku01.JPG)

Name the app and click on "Create app".

![heroku02](/images/uploads/netcore3_heroku_heroku02.JPG)

In your machine, install the latest version of Heroku CLI [here](https://devcenter.heroku.com/articles/heroku-cli).

### .Net Core 3

Download the web API from this GitHub repository: [NetCore3-MySQL](https://github.com/lucianopereira86/NetCore3-MySQL).  
Follow the instructions to make the required database connection.

In the _api_ folder, create manually a file called "Dockerfile" without extension and edit it with this lines:

```batch
FROM mcr.microsoft.com/dotnet/core/sdk:3.0-buster AS build
WORKDIR /app
COPY ./ ./

RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-buster-slim
WORKDIR /app
COPY --from=build /app/out .
CMD ASPNETCORE_URLS=http://*:$PORT dotnet NetCore3WebAPI.dll
```

### Docker

Run the following commands in the _api_ folder replacing [MYAPP] by the app's name created on Heroku.

```batch
docker build -t [MYAPP] .
```

To authenticate with Heroku, run this command. It will be required to press any key to open a web browser window containing a login button.

```batch
heroku login
```

Then, return to the terminal and run:

```batch
heroku container:login
```

Tag the image:

```batch
docker tag [MYAPP] registry.heroku.com/[MYAPP]/web
```

Build the image locally and push it to Heroku's Container Registry:

```batch
heroku container:push web -a [MYAPP]
```

Release the image on Heroku to be deployed:

```batch
heroku container:release web -a [MYAPP]
```

Access the URL of your app with Swagger:

```batch
https://[MYAPP].herokuapp.com/swagger/index.html
```

![heroku03](/images/uploads/netcore3_heroku_heroku03.JPG)

## Conclusion

It was very simple to publish on Heroku. Docker was used only to build the image. 
Now you have a remote database and a deployed web API. 

## Next
We will integrate the web API with Entity Framework to manipulate the database only by C# objects and Lambda Expression.
