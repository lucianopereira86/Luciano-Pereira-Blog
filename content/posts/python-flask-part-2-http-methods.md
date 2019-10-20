---
title: Python + Flask - Part 2 - HTTP Methods
date: '2019-10-19T22:46:48-03:00'
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

This is the seconde part of a series about the Flask framework, a common tool used to create web applications with Python.  

## Objectives

The part 2 will focus on creating HTTP methods to our web API.  
The full example is available here: [Python-Flask](https://github.com/lucianopereira86/Python-Flask).

## Topics

- [GET](#get)
- [POST](#post)
- [PUT](#put)
- [DELETE](#delete)

### GET

Create a dictionary called _users_dict_ to be returned after a GET request:

![flask04](/images/uploads/python_flask_flask04.JPG)

Access the URL below and see the result:

```
http://127.0.0.1:5000/users
```

![flask05](/images/uploads/python_flask_flask05.JPG)

Create another method to return a user by id:

![flask06](/images/uploads/python_flask_flask06.JPG)

Access the URL below and see the result:

```
http://127.0.0.1:5000/user?id=1
```

![flask07](/images/uploads/python_flask_flask07.JPG)

Return a user by id passing the parameter in the path:

![flask08](/images/uploads/python_flask_flask08.JPG)

Access the URL below and see the result:

```
http://127.0.0.1:5000/user/1
```

![flask09](/images/uploads/python_flask_flask09.JPG)

### POST

To simulate a POST request, remove all dictionaries from _users_dict_:

![flask10](/images/uploads/python_flask_flask10.JPG)

Create a POST method with the following code:

![flask11](/images/uploads/python_flask_flask11.JPG)

Execute a POST request sending a new user. You can use the [Postman](https://www.getpostman.com/) to make the request:

![flask12](/images/uploads/python_flask_flask12.JPG)

The result will be:

![flask13](/images/uploads/python_flask_flask13.JPG)

A new user was added to the _users_dict_. Make some changes at the _get_users_ function to search for the user by using multiple properties dynamically, even by considering their types.

| Don't forget to run the POST request every time you save the project because the _users_dict_ will be resetted! |
| --------------------------------------------------------------------------------------------------------------- |

![flask14](/images/uploads/python_flask_flask14.JPG)

This way there will be many possible queries with the same method:

![flask15](/images/uploads/python_flask_flask15.JPG)

![flask16](/images/uploads/python_flask_flask16.JPG)

![flask17](/images/uploads/python_flask_flask17.JPG)

### PUT

To update a user, create this method:

![flask18](/images/uploads/python_flask_flask18.JPG)

Execute a PUT request:

![flask19](/images/uploads/python_flask_flask19.JPG)

The result will be:

![flask20](/images/uploads/python_flask_flask20.JPG)

### DELETE

To delete a user by id, write this code:

![flask21](/images/uploads/python_flask_flask21.JPG)

Execute a DELETE request:

![flask22](/images/uploads/python_flask_flask22.JPG)

The result will be:

![flask23](/images/uploads/python_flask_flask23.JPG)

## Next

We will connect our web API with a local database.
