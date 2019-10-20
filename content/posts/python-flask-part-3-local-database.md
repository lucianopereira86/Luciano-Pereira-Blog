---
title: Python + Flask - Part 3 - Local Database
date: '2019-10-19T23:08:47-03:00'
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

This is the third part of a series about the Flask framework, a common tool used to create web applications with Python.  

## Objectives

The part 3 will focus on connecting the web API with a local database.  
The full example is available here: [Python-Flask](https://github.com/lucianopereira86/Python-Flask).

## Topics

- [Local Database](#local-database)

### Local Database
 
Create another Python file inside the _api_ folder called _db_api_ and write this code:

![flask24_0](/images/uploads/python_flask_flask24_0.JPG)

The functions below must be created as well:

- Creates the database

![flask24](/images/uploads/python_flask_flask24.JPG)

- Creates tables

![flask25](/images/uploads/python_flask_flask25.JPG)

- Executes the operation

![flask27](/images/uploads/python_flask_flask27.JPG)

- Starts the database. This function must be called before _app.run()_.

![flask26](/images/uploads/python_flask_flask26.JPG)

Finally, run the following command:

```sh
python .\api\db_api.py

```

The _test.db_ will be created inside the _api_ folder and will contain the _user_ table:

![flask28](/images/uploads/python_flask_flask28.JPG)

Copy and modify the HTTP functions from _api.py_ to _db_api.py_.

- POST

![flask29](/images/uploads/python_flask_flask29.JPG)

- PUT

![flask30](/images/uploads/python_flask_flask30.JPG)

- GET

![flask31](/images/uploads/python_flask_flask31.JPG)

- DELETE

![flask32](/images/uploads/python_flask_flask32.JPG)

Test each one and see the result.

## Next

We will connect our web API with a remote database.
