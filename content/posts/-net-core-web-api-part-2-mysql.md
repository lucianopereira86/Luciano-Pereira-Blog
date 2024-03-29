---
title: .Net Core web API - Part 2 - MySQL
date: '2019-10-13T14:34:07-03:00'
categories:
  - Net Core
tags:
  - Net Core
  - MySQL
  - Dapper
keywords:
  - Net Core
  - MySQL
  - Dapper
autoThumbnailImage: true
thumbnailImagePosition: top
thumbnailImage: /images/uploads/netcore3_mysql_titulo.JPG
coverImage: /images/uploads/netcore3_mysql_titulo.JPG
---
![titulo](/images/uploads/netcore3_mysql_titulo.JPG)

Continuing the .Net Core series, in this chapter, we will connect our web API with a remote MySQL server. 
The full example can be downloaded in my GitHub repository: [NetCore3 MySQL](https://github.com/lucianopereira86/NetCore3-MySQL).

## Technologies

- [.Net Core 3](https://docs.microsoft.com/pt-br/dotnet/core/whats-new/dotnet-core-3-0)
- [MySQL](https://www.mysql.com/)
- [MySQL Workbench](https://www.mysql.com/products/workbench/)
- [Dapper](https://dapper-tutorial.net/)

## Topics

- [MySQL](#mysql)
- [.Net Core 3](#net-core-3)

### MySQL

Let's create a remote MySQL database and manipulate it with MySQL Workbench.

First, access this website:

```bash
https://remotemysql.com/
```

At the home page, click on "Login" and, in the next page, on the "Create Account" tab:

![mysql01](/images/uploads/netcore3_mysql_mysql01.JPG)

Create an account and you will receive an e-mail to confirm. Login in the website and create a database:

![mysql02](/images/uploads/netcore3_mysql_mysql02.JPG)

These are your connection data. Remember the password!

![mysql03](/images/uploads/netcore3_mysql_mysql03.JPG)

Now download the MySQL Workbench through this [link](https://dev.mysql.com/downloads/workbench/).  
After the installation process, open the program and click on "Manage Connections...":

![mysql04](/images/uploads/netcore3_mysql_mysql04.JPG)

Click on "New" and set the Hostname, Username, Password and Default Schema fields with the data from the remote database:

![mysql05](/images/uploads/netcore3_mysql_mysql05.JPG)

Test the connection:

![mysql06](/images/uploads/netcore3_mysql_mysql06.JPG)

Now, connect to the database:

![mysql07](/images/uploads/netcore3_mysql_mysql07.JPG)

![mysql08](/images/uploads/netcore3_mysql_mysql08.JPG)

![mysql09](/images/uploads/netcore3_mysql_mysql09.JPG)

We are ready to create our first table.  
Run the following script inside the "Query 1" tab:

```sql
CREATE TABLE user (
	id INT PRIMARY KEY AUTO_INCREMENT,
    name varchar(100)
);
```

Add some lines:

```sql
INSERT INTO user (name) VALUES ('Luciano');
INSERT INTO user (name) VALUES ('Sousa');
INSERT INTO user (name) VALUES ('Pereira');
```

The table structure will be visible:

![mysql10](/images/uploads/netcore3_mysql_mysql10.JPG)

### .Net Core 3

Download the [project sample](https://github.com/lucianopereira86/NetCore3-Swagger) from the [part 1](https://lucianopereira.netlify.com/posts/-net-core-web-api-part-1-swagger/).

Inside the _appsettings.json_, add a new object called _ConnectionStrings_ containing the MySQL connection string:

![netcore01](/images/uploads/netcore3_mysql_netcore01.JPG)

Create a folder named _Models_ in the root with two classes: _ConnectionStrings_ and _User_.

![netcore02](/images/uploads/netcore3_mysql_netcore02.JPG)

![netcore03](/images/uploads/netcore3_mysql_netcore03.JPG)

To be able to use the connection string anywhere in the code, it's necessary to create a singleton of its model inside the _Startup_ class.

![netcore04](/images/uploads/netcore3_mysql_netcore04.JPG)

Create another controller called _UserController_ with two methods: POST and GET.

![netcore05](/images/uploads/netcore3_mysql_netcore05.JPG)

Dapper is an ORM that allow an easy connection with any database. Install it through Nuget.

![netcore06](/images/uploads/netcore3_mysql_netcore06.JPG)

MySqlConnector is another package that you need to install.

![netcore07](/images/uploads/netcore3_mysql_netcore07.JPG)

Create a constructor inside the _UserController_ injecting the _ConnectionStrings_ singleton in a local variable.

![netcore08](/images/uploads/netcore3_mysql_netcore08.JPG)

Implement the Dapper inside the GET and POST methods:

![netcore09](/images/uploads/netcore3_mysql_netcore09.JPG)

![netcore10](/images/uploads/netcore3_mysql_netcore10.JPG)

Run the API and see the result in the URL:

```bash
http://localhost:53000/swagger/index.html
```

![netcore11](/images/uploads/netcore3_mysql_netcore11.JPG)

Test the GET method:

![netcore12](/images/uploads/netcore3_mysql_netcore12.JPG)

The result will be:

![netcore13](/images/uploads/netcore3_mysql_netcore13.JPG)

Test the POST method:

![netcore14](/images/uploads/netcore3_mysql_netcore14.JPG)

The result will be:

![netcore15](/images/uploads/netcore3_mysql_netcore15.JPG)

Run the GET method again and a new user will appear:

![netcore16](/images/uploads/netcore3_mysql_netcore16.JPG)

## Conclusion

In order to easily connect with a database we have used the Dapper and MySqlConnector packages.  
Model classes were created to reflect the table and the connection string.  
In the next chapter, we will deploy our web API to Heroku.
