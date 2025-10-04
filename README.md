# Ex.05 Design a Website for Server Side Processing
## Date:04.10.2025

## AIM:
 To design a website to calculate the Body Mass Index (BMI) in the server side.


## FORMULA:
BMI = W/H<sup>2</sup>
<br> BMI --> Body Mass Index
<br> W --> Weight
<br> H --> Height

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
<html>
<head>
    <title>BMI Calculator</title>
    <style>
        
h1{
    border: 2px solid ;
    padding: 15px;
    margin: 40px;
    border-radius: 10px;
    position: center;
    top: 200px;
    right: 1100px;
    font-size: xx-large;
    font-weight: bolder;
    font-variant: small-caps;
    font-family: Georgia;
}
form{
    border: 5px  solid rgb(13, 13, 13);
    background-color: rgb(45, 123, 158) ;
    padding: 30px;
    margin: 10px;
    border-radius: 20px;
    width: 425px;
    position:center;
    top: 300px;
    left: 527px;
    
}

    </style>
</head>
<body bgcolor="pink">
    <center>
        <h1>BMI CALCULATOR</h1>
        <form method="POST">
            {% csrf_token %}
            <label>HEIGHT (in meter):</label><br>
            <input type="text" name="height"><br>
            <label>WEIGHT (in kg):</label><br>
            <input type="text" name="weight"><br>
            <button type="submit">CALCULATE</button>
        </form>

        

        {% if BMI %}
            <h2>YOUR BMI IS: {{ BMI }}</h2>
        {% endif %}
    </center>
</body>
</html>

urls.py

from django.contrib import admin
from django.urls import path
from myapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.calculate_bmi, name='calculate_bmi'),
]
views.py
from django.shortcuts import render

def calculate_bmi(request):
    bmi = None  
    if request.method == "POST":
        height = float(request.POST.get("height"))
        weight = float(request.POST.get("weight"))
        bmi = weight / (height * 2)
        print("Height:", height)
        print("Weight:", weight)
        print("BMI calculated:", bmi)

    return render(request, "myapp/math.html", {"BMI": bmi})

```


## SERVER SIDE PROCESSING:
![alt text](<Screenshot (34)-1.png>)

## HOMEPAGE:
![alt text](<Screenshot (35)-1.png>)

## RESULT:
The program for performing server side processing is completed successfully.
