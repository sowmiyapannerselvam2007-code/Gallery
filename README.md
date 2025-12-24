# Ex.07 Design of Interactive Image Gallery
# Date:
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
gallery.html
{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Ocean Image Gallery</title>

    <style>
        body{
            margin:0;
            min-height:100vh;
            background: linear-gradient(to bottom, #0f2027, #203a43, #2c5364);
            font-family: "Trebuchet MS", sans-serif;
            color: #e0f7fa;
        }

        h1{
            text-align:center;
            margin:35px 0;
            letter-spacing:4px;
            font-size:42px;
            color:#b2ebf2;
            text-shadow: 0 0 15px rgba(0,255,255,0.5);
        }

        /* GALLERY FLEX */
        .gallery{
            display:flex;
            flex-wrap:wrap;
            justify-content:center;
            gap:45px;
            padding:50px;
            max-width:1300px;
            margin:auto;
        }

        .gallery a{
            text-decoration:none;
        }

        .gallery img{
            width:320px;
            height:230px;
            object-fit:cover;
            border-radius:20px;
            border:3px solid rgba(178,235,242,0.5);
            box-shadow:
                0 10px 25px rgba(0,0,0,0.6),
                0 0 20px rgba(0,255,255,0.25);
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            cursor:pointer;
        }

        .gallery img:hover{
            transform: scale(1.15);
            box-shadow:
                0 20px 45px rgba(0,0,0,0.8),
                0 0 35px rgba(0,255,255,0.7);
            z-index:10;
        }

        /* POPUP OVERLAY */
        .Photo{
            position:fixed;
            top:0;
            left:0;
            width:100%;
            height:100%;
            background: radial-gradient(circle at top, rgba(0,80,120,0.9), rgba(0,0,0,0.95));
            display:none;
            justify-content:center;
            align-items:center;
            z-index:100;
        }

        .Photo img{
            max-width:90%;
            max-height:85%;
            border-radius:18px;
            border:4px solid rgba(178,235,242,0.8);
            box-shadow:
                0 0 40px rgba(0,255,255,0.8),
                0 0 80px rgba(0,120,180,0.8);
        }

        .Photo:target{
            display:flex;
        }

        .close{
            position:absolute;
            top:25px;
            right:35px;
            font-size:45px;
            color:#b2ebf2;
            text-decoration:none;
            font-weight:bold;
            transition: color 0.3s, transform 0.3s;
        }

        .close:hover{
            color:#ffffff;
            transform: scale(1.2);
        }
    </style>
</head>

<body>

<h1>OCEAN IMAGE GALLERY</h1>

<div class="gallery">
    <a href="#img1"><img src="{% static 'pic1.jpg' %}" alt="Ocean Image 1"></a>
    <a href="#img2"><img src="{% static 'pic2.jpg' %}" alt="Ocean Image 2"></a>
    <a href="#img3"><img src="{% static 'pic3.jpg' %}" alt="Ocean Image 3"></a>
    <a href="#img4"><img src="{% static 'pic4.jpg' %}" alt="Ocean Image 4"></a>
    <a href="#img5"><img src="{% static 'pic5.jpg' %}" alt="Ocean Image 5"></a>
    <a href="#img6"><img src="{% static 'pic6.jpg' %}" alt="Ocean Image 6"></a>
</div>

<!-- POPUP IMAGES -->
<div class="Photo" id="img1">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic1.jpg' %}">
</div>

<div class="Photo" id="img2">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic2.jpg' %}">
</div>

<div class="Photo" id="img3">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic3.jpg' %}">
</div>

<div class="Photo" id="img4">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic4.jpg' %}">
</div>

<div class="Photo" id="img5">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic5.jpg' %}">
</div>

<div class="Photo" id="img6">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic6.jpg' %}">
</div>

</body>
</html>
```
```
urls.py
from django.contrib import admin
from django.urls import path
from galleryapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.gallery, name='gallery'),
]

```
```
views.py
from django.shortcuts import render

def gallery(request):
    return render(request, 'gallery.html')
```
# OUTPUT:
![alt text](<Screenshot 2025-12-18 213817.png>)
![alt text](<Screenshot 2025-12-18 213831.png>)
# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
