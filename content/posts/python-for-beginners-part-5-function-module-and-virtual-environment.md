---
title: 'Python for Beginners - Part 5 - Function, Module and Virtual Environment'
date: '2019-10-15T20:26:27-03:00'
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

Fifth part of articles about the Microsoft's [Python for Beginners](https://www.youtube.com/watch?v=jFCNu1-Xdsw&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6) series.
You can read the part 4 [here](https://lucianopereira.netlify.com/posts/python-for-beginners-part-4-conditional-logic-collection-and-loop/).
All the examples from the playlist are available in this GitHub repository: [Python Examples](https://github.com/lucianopereira86/Python-Examples).

### Objective
You will learn how to create functions, importing modules and creating virtual environments.
A Python file was created to demonstrate each example.

## Topics
* [function.py](#function-py)
* [module.py](#module-py)
* [venv.py](#venv-py)

### function.py

Creating functions.

![code19](/images/uploads/python_code19.JPG)

Executing the command below:

```batch
python .\examples\function.py
```

The result is:

![code20](/images/uploads/python_code20.JPG)

### module.py

Importing the "math_module.py".

![code21](/images/uploads/python_code21.JPG)

Using its functions.

![code22](/images/uploads/python_code22.JPG)

Executing the command below:

```batch
python .\examples\module.py
```

The result is:

![code23](/images/uploads/python_code23.JPG)

### venv.py

Create a virtual environment, install a package and use it in a module.

Execute the command below to create a folder called 'venv':

```bash
python -m venv venv
```

Press the 'Yes' button inside the popup that shows up inside the VSCode.

![code24](/images/uploads/python_code24.JPG)

The virtual environment will be available in the project root folder.

![code25](/images/uploads/python_code25.JPG)

Run the command below to use it:

```bash
.\venv\Scripts\Activate.ps1
```

The word '(venv)' will be visible in the left side of the current path.

![code26](/images/uploads/python_code26.JPG)

And at the bottom of the VSCode, as well.

![code27](/images/uploads/python_code27.JPG)

Create a file named 'requirements.txt' at the project root folder and type _colorama_ inside of it.

![code28](/images/uploads/python_code28.JPG)

Install the _colorama_ package inside the venv with the following command:

```bash
pip install -r requirements.txt
```

The result will be:

![code29](/images/uploads/python_code29.JPG)

Import _colorama_ inside the _math_module.py_ to write colored messages.

![code30](/images/uploads/python_code30.JPG)

Finally, run the command below:

```bash
python .\examples\module.py
```

The result will be:

![code31](/images/uploads/python_code31.JPG)

## Next
You will learn how to make connect with web APIs, manipulate dictionaries, read environment variables and use decorators.

### Video References
* [Programming with Python | Python for Beginners [29 of 44]](https://www.youtube.com/watch?v=nrCAxXfRU28&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=29)
* [Programming with Python | Python for Beginners [30 of 44]](https://www.youtube.com/watch?v=C9ZEGqGHXms&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=30)
* [Programming with Python | Python for Beginners [31 of 44]](https://www.youtube.com/watch?v=sKW-zdYZNX4&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=31)
* [Programming with Python | Python for Beginners [32 of 44]](https://www.youtube.com/watch?v=LtKAXFRtxhQ&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=32)
* [Programming with Python | Python for Beginners [33 of 44]](https://www.youtube.com/watch?v=Uei2ILcxuPs&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=33)
* [Programming with Python | Python for Beginners [34 of 44]](https://www.youtube.com/watch?v=_eczHOiFMZA&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=34)
* [Programming with Python | Python for Beginners [35 of 44]](https://www.youtube.com/watch?v=mzpQgMNdR0g&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=35)
