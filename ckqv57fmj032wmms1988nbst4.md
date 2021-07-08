## Setting up Python3 and Django for Linux / MacOS / Windows / Android

# Overview

Watsup Coders, and welcome to part of the django series. I'll walk you through setting up django project, using python3. Setting this up on android can be a little tricky and all, just feel free to leave a comment below if you have any problem at all.

Shall we?

# Contents


- Installing python3(Linux / MacOS, Windows, Android)
- Installing django
- Create a django project
- Run the django project

# Installing python3

- Linux / MacOS

MacOS are linux based Operating systems, they work exactly the same in terms on their terminal behavior, just very slight differences, the commands i'll be running will be available for both Linux / MacOS installation.

> First, let' open up the terminal. Search through app menu, you'll find it.


```
$ sudo apt-get install python3
[sudo] password for mohammed: 
Reading package lists... Done
Building dependency tree       
Reading state information... Done
python3 is already the newest version (3.8.2-0ubuntu2).
python3 set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 238 not upgraded.
``` 

I'm running Linux Ubuntu 20.04 LTS and in my case, it's installed already, if you don't have it installed, it'll do that for you.

- Windows

You need to visit the [official python website to download any python3 version](https://www.python.org/downloads/). Download it, then double click it like any other software, then follow the procedures. There's this option most people forget to tick, it'll ask if you want to add python to PATH, make sure you keep that box checked. Then you can proceed to finally install python3.

- Android

Termux at it again. You can use app store to install termux, it helps you easily emulate Linux terminal on android. Okay, now to install python3 using termux.

```
$ pkg install python
```
Check [here](https://techyeyes.com/install-python-3-in-termux/) for more.
And also, if we need to run any terminal commands, you can use termux if you are running on android. Hopefully that works.

Another thing you'll want to install is a text editor for android, Acode. Search for 'Acode' in app store and install it too.

> To verify your installation, you can invoke the interpreter

```
$ python3
Python 3.8.5 (default, May 27 2021, 13:30:53) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```
Works like magic.

> Next thing we need to install is pip

[pip](https://pypi.org/project/pip/) is a package manager for python. It'll help us install django, first, we need to install it.

Exit the python interpreter first

```

Python 3.8.5 (default, May 27 2021, 13:30:53) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()

```

Now install pip

```
$ sudo apt-get install python3-pip
Reading package lists... Done
Building dependency tree       
Reading state information... Done
python3-pip is already the newest version (20.0.2-5ubuntu1.5).
0 upgraded, 0 newly installed, 0 to remove and 238 not upgraded.
```

Again, i already have it installed, your output will be different, but it'll work the same.

> Verify your pip installation

```
$ pip --version
pip 21.1.2 from /home/mohammed/.local/lib/python3.8/site-packages/pip (python 3.8)
```

That works too, alright. We can install django now.

> Installing django

```
$ pip install django
Requirement already satisfied: django in ./.local/lib/python3.8/site-packages (3.1.7)
Requirement already satisfied: sqlparse>=0.2.2 in ./.local/lib/python3.8/site-packages (from django) (0.4.1)
Requirement already satisfied: pytz in /usr/lib/python3/dist-packages (from django) (2019.3)
Requirement already satisfied: asgiref<4,>=3.2.10 in ./.local/lib/python3.8/site-packages (from django) (3.3.1)
```

Yep, you guessed right, i also have django installed.
Currently, i'm running on django 3.1.7, anything around 3.1 or higher. The remaining stuffs there are dependencies that django needs to work. Okay.

> Verfiying your django installation

```
$ django-admin --version
3.1.7
```

That should give you the django version you installed, awesome.

# Creating a django project

This is easy, run the django-admin command like this;

```
$ django-admin startproject mydjangoapp
```

That should create a django project for you with this similar structure;

```
mydjangoapp/
├── manage.py
└── mydjangoapp
    ├── asgi.py
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py

1 directory, 6 files
```

Depending on the name of your project, you should have something similar to that.

# Run the django project

This is the final part we've all been waiting for, you'll have your first django application running in no time.

```
$ cd mydjangoapp
$ python3 manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
July 08, 2021 - 16:15:17
Django version 3.1.7, using settings 'mydjangoapp.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```

Now you have your django web server running, good job. You can visit the web address at http://127.0.0.1:8000/ using your browser. You should see your app running.

Congratulations on your first django project !!!.

Till next time.
Say ciao :v:
