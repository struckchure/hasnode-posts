## Creating and Understanding a Django project

## Overview

Okay peeps, welcome back, it's been a while now, so let's get to it. I'll be talking to you about creating a django project and explaining the project structure and some files inside the project. For the purpose of this series, we'll be creating a music app, this was inspired by the first django series i watched on YouTube by Bucky Roberts (SentDex, TheNewBoston), let's call our app SoundBox.

**NB** : For now, we'll not be put too much attention to styling, that's the easiest part, we can do that last.

Yeah, let's roll.

## Content

- Create project using django-admin
- Explanation of project files;
    - settings.py
    - urls.py
    - wsgi.py
    - asgi.py

## Create project using django-admin

Throughout this tutorial till the end, you'll be needing your terminal. Pull up your terminal and type the command to create a new project.

```
$ django-admin startproject soundbox
```

You should now have a folder with a similar structure to this.

```
soundbox/
├── manage.py
└── soundbox
    ├── asgi.py
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py

1 directory, 6 files
```

Okay, that part is done, we can move one now.

## Explanation of project files

- manage.py

Check [here](https://github.com/Mohammed2702/soundbox/blob/main/manage.py) for manage.py file

The most important file, the way i see it is the manage.py file, which you never want to edit, i have built projects, and i have never had a reason to edit manage.py file for once for any reason. I suggest you don't mess with it if you can't handle it. So, what does it do?

It helps you manage your project as the name implies, it helps you create new app, run migrations, and a lot of other things you'll discover all along.

- soundbox folder (contains settings.py, urls.py, wsgi.py, asgi.py)

Check [here](https://github.com/Mohammed2702/soundbox/tree/main/soundbox) for soundbox folder

This folder houses the main configurations of the soundbox project, which i'll explain all the files in a bit. And there's the __init__.py file, it's an empty file, you'll find it in most python project folders, it basically tells python that the folder is contains python files.

- soundbox/settings.py

Check [here](https://github.com/Mohammed2702/soundbox/blob/main/soundbox/settings.py) for settings.py file

This file contains your project settings, main project settings, like the apps you have in your project, the kind of database you want to use, how you want to manage static files, media files, middlewares, authentications, validators and lots more, which you'll discover later on.

- soundbox/urls.py

Check [here](https://github.com/Mohammed2702/soundbox/blob/main/soundbox/urls.py) for urls.py file

Every django project needs a root urls configuration, just so you can keep things clean and modularized, you can keep adding urls from other apps with the project, you'll see how to do that in a bit.

- soundbox/wsgi.py

Check [here](https://github.com/Mohammed2702/soundbox/blob/main/soundbox/wsgi.py) for wsgi.py file

WSGI stands for Web Server Gateway Interface, this helps us to deploy (put our website online for other people to access it).

Check [here](https://wsgi.readthedocs.io/en/latest/) for more

- soundbox/asgi.py

Check [here](https://github.com/Mohammed2702/soundbox/blob/main/soundbox/asgi.py) for asgi.py file

ASGI stands for Asynchronous Server Gateway Interface, this helps us to deploy (put our website online for other people to access it).

Check [here](https://asgi.readthedocs.io/en/latest/) for more

Alright, i think that's all on setting up our SoundBox Application, see you in the next tutorial.

Peace.

