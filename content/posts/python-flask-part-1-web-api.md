---
title: Python + Flask - Part 1 - Web API
date: '2019-10-19T22:15:13-03:00'
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

This is the first part of a series about the Flask framework, a common tool used to create web applications with Python.  

## Objectives

In this series you will learn how to create a web API in Python, make requests and connect it with local and remote databases. 
The part 1 will focus on the virtual environment to install Flask and how to run a web API. The full example is available here: [Python-Flask](https://github.com/lucianopereira86/Python-Flask).

## Before Start

If you are new to Python, read these articles to get started: [Python for Beginners](https://dev.to/lucianopereira86/python-for-beginners-part-1-hello-world-19ed).

## Topics

- [venv](#venv)
- [API](#api)

### venv

Create a folder for your project, open VSCode and execute the command below to create a virtual environment (venv):

```sh
python -m venv venv
```

Confirm any popup that shows up and run the command below to use the _venv_:

```sh
.\venv\Scripts\Activate.ps1
```

Create a file named 'requirements.txt' containing the word _flask_.

![venv01](/images/uploads/python_flask_venv01.JPG)

Install the _flask_ package inside the _venv_ with the following command:

```sh
pip install -r requirements.txt
```

The result will be:

![venv02](/images/uploads/python_flask_venv02.JPG)

### API

Create a folder called _api_ with a file called _api.py_. Inside the file, write this code:

![flask01](/images/uploads/python_flask_flask01.JPG)

Run the following command:

```sh
python .\api\api.py
```

The result will be:
![flask02](/images/uploads/python_flask_flask02.JPG)

If you follow the URL displayed you will see the web page running:

```
http://127.0.0.1:5000/
```

![flask03](/images/uploads/python_flask_flask03.JPG)


## Next

We will create the HTTP methods to turn our web application into a web API.

## References

- [Creating Web APIs with Python and Flask](https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask)
