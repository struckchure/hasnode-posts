## Creating Music Application

# Overview

Hey there, been a while. Let's try picking up from where we stopped, now, shall we?

I would be adding some models to the project so we can upload songs into albums. You might be wondering what models are or so, yeah, it's no big deal. In my definition, I'd say models are abstract instances you create just so you can understand what is going on in your database. The abstraction I'm talking about here is the kind of data you're trying to store in the database, in this case, we want to store albums and songs only, we have to create those models, abstract as instances we can understand.
Alright.

# Content

- Create an app for albums and songs
- Create `Album` and `Song` model relationship
- Migrate the models
- Messing around with the models

# Create an app for albums and songs

This part is really easy, I explained what an app is, in a Django environment, think of it as a collection of similar functionalities, since an album contains songs, it only makes sense to put them in one place together, don't you agree?

I always get confused in this part, like what name do I give the app, it does not matter what name actually, but while naming things in this business, you want it to be related to what it actually does. I'll just call it box, as in music box.
To create the app, navigate to your project directory;

`struckchure@cws:~/cws/soundbox$ python3 manage.py startapp box`

Now i should have a folder named `box` in the project folder, with some files in it, the files we need to talk about here is just the `models.py`, `views`, and one other file we need to create `urls.py` file.

Let's start with the `models.py` file

# Create `Album` and `Song` model relationship

To create models in our app, we need to add a few codes to our `models.py` file in `box` app, let's get to it.

Album model

```py
# box/models.py

from django.db import models


class Album(models.Model):

    title = models.CharField(max_length=100)
    artist = models.CharField(max_length=100)
    cover_art = models.ImageField(upload_to="/cover-arts")
    year = models.PositiveIntegerField()

```

Line 1: This brings in the module necessary to create a model  
Line 4: We defined a model named `Album` which inherits from `models.Model`, this allows the model to be added to the database  
Line 6: A field to store album title, `CharField` is commonly used to store strings, with a required parameter, `max_length` which specifies the maximum length of the title  
Line 7: Same as Line 6  
Line 8: `cover_art` is an `ImageField` for storing images, obviously, with an optional parameter of where the file should be uploaded in the `MEDIA_ROOT`  
Line 9: An integer field to store the release year of the song, as `PositiveIntegerField`  

Piece of cake, ry?
Next is the song model

```py
from django.db import models


class Album(models.Model):

    title = models.CharField(max_length=100)
    artist = models.CharField(max_length=100)
    cover_art = models.ImageField(upload_to="/cover-arts")
    year = models.PositiveIntegerField()


class Song(models.Model):

    album = models.ForeignKey(Album, on_delete=models.CASCADE)
    title = models.CharField(max_length=200)
```

The only strange line here is;

```py
album = models.ForeignKey(Album, on_delete=models.CASCADE)
```

This is one of many relationships that exist in all databases, if not all.

`ForeignKey` is classified as ManyToOne relationship, for example, `Many` songs can belong `To` `One` album, sounds pun-ish, dohh.
So we said each song should belong to an album - `ForeignKey(Album)`
Then -> `ForeignKey(Album, on_delete=models.CASCADE)` says the song should be deleted once the album is also deleted.

# Migrate the models

# Messing around with the models

Hope you learned a few things and also enjoyed it. See you at the next one.

Struckchure, out.
