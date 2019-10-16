---
title: >-
  Python for Beginners - Part 6 - Web API connection, Dictionary, Environment
  Variable and Decorator
date: '2019-10-15T20:48:42-03:00'
categories:
  - Python
tags:
  - Python
  - Microsoft
keywords:
  - Python
  - Microsoft
autoThumbnailImage: true
thumbnailImagePosition: top
thumbnailImage: /images/uploads/python_titulo.jpg
coverImage: /images/uploads/python_titulo.jpg
---
![python_titulo](/images/uploads/python_titulo.jpg)

Last part of articles about the Microsoft's [Python for Beginners](https://www.youtube.com/watch?v=jFCNu1-Xdsw&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6) series.
You can read the part 5 [here](https://lucianopereira.netlify.com/posts/python-for-beginners-part-5-function-module-and-virtual-environment/).
All the examples from the playlist are available in this GitHub repository: [Python Examples](https://github.com/lucianopereira86/Python-Examples).

### Objective
You will learn how to make connect with web APIs, manipulate dictionaries, read environment variables and use decorators.
A Python file was created to demonstrate each example.

## Topics
* [api/post.py](#apipostpy)
* [dictionary.py](#dictionary-py)
* [keys.py](#keys-py)
* [decorators.py](#decorators-py)

### api/post.py

Making a POST request to a web API.  
The example file was created inside of a folder named _api_.

![code32](/images/uploads/python_code32.JPG)

First, install the _requests_ library:

```bash
pip install requests
```

The result will be:

![code33](/images/uploads/python_code33.JPG)

Then, run this command:

```bash
python .\examples\api\post.py
```

The result will be:

![code34](/images/uploads/python_code34.JPG)

### dictionary.py

Creating and manipulating dictionaries.

![code35](/images/uploads/python_code35.JPG)

Executing the command below:

```batch
python .\examples\dictionary.py
```

The result is:

![code36](/images/uploads/python_code36.JPG)

### keys.py

Reading environment variables.

![code37](/images/uploads/python_code37.JPG)

Create a _.env_ file containing a secret key.

![code38](/images/uploads/python_code38.JPG)

Update the _requirements.txt_ file by adding _python-dotenv_.

![code39](/images/uploads/python_code39.JPG)

Let's use a virtual environment again by executing the commands below:

```bash
python -m venv venv

.\venv\Scripts\Activate.ps1
```

Install the _python_dotenv_ package inside the venv:

```bash
pip install -r requirements.txt
```

The result will be:

![code40](/images/uploads/python_code40.JPG)

Finally, run this command:

```bash
python .\examples\keys.py
```

The result will be:

![code41](/images/uploads/python_code41.JPG)

### decorators.py

How to use decorators in functions.

![code42](/images/uploads/python_code42.JPG)

Run the command:

```bash
python .\examples\decorators.py
```

The result will be:

![code43](/images/uploads/python_code43.JPG)

## Conclusion
We have finally ended this series! 
Now you have the basics to start working with Python.
