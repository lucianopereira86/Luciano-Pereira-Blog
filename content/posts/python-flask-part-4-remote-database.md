---
title: Python + Flask - Part 4 - Remote Database
date: '2019-10-19T23:12:44-03:00'
categories:
  - Python
tags:
  - Python
  - Flask
keywords:
  - Python
  - Flask
autoThumbnailImage: true
thumbnailImagePosition: top
thumbnailImage: /images/uploads/python_flask_titulo.JPG
coverImage: /images/uploads/python_flask_titulo.JPG
---
![titulo](/images/uploads/python_flask_titulo.JPG)

This is the fourth and last part of a series about the Flask framework, a common tool used to create web applications with Python.  

## Objectives

The part 4 will focus on connecting the web API with a remote database.  
The full example is available here: [Python-Flask](https://github.com/lucianopereira86/Python-Flask).

## Topics

- [Remote Database](#remote-database)

### Remote Database

Let's connect with a remote MySQL database now.  
Follow the instructions in this [article](https://dev.to/lucianopereira86/net-core-web-api-part-2-mysql-3bje) or in this [repository](https://github.com/lucianopereira86/NetCore3-MySQL) to create a database and get the connection string.  
If you followed them correctly, you must have a _user_ table in your remote database. Change it by adding a column named _age_.  
Here is an easy script to do it:

```sql
ALTER TABLE user ADD age INT NOT NULL;
```

Now, return to VSCode, add _PyMySQL_ into the _requirements.txt_ and install it by running:

```sh
pip install -r requirements.txt
```

Inside the _db_api.py_, import the _PyMySQL_ package:

```python
import pymysql.cursors
```

Comment the _start_db_ function because it won't be needed anymore:

![flask33](/images/uploads/python_flask_flask33.JPG)

Modify the _execute_ function to receive the MySQL connection by adding the connection string:

![flask34](/images/uploads/python_flask_flask34.JPG)

Change the _post_users_ function to receive the inserted id:

![flask35](/images/uploads/python_flask_flask35.JPG)

Now, run the API again:

```sh
python .\api\db_api.py

```

Make a GET request to the _get_users_ function. The result will be something like this:

![flask38](/images/uploads/python_flask_flask38.JPG)

Make a POST request to create another user:

![flask39](/images/uploads/python_flask_flask39.JPG)

Another GET request and the result will be:

![flask40](/images/uploads/python_flask_flask40.JPG)

Modify the age from your new user with a PUT request:

![flask41](/images/uploads/python_flask_flask41.JPG)

Check it out:

![flask42](/images/uploads/python_flask_flask42.JPG)

Delete another user:

![flask43](/images/uploads/python_flask_flask43.JPG)

And... it is gone!

![flask44](/images/uploads/python_flask_flask44.JPG)

## Conclusion

In this series, you have seen how a web API behaves in a Python environment with Flask framework.  
During our tests, Runtime (_api.py_) and persistent (_db_api.py_) data were used.  
The local and remote database had similar functions, equal results and were easy to manipulate.
