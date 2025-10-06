# Ex.05 Design a Website for Server Side Processing
## Date:06.10.2025

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
math.html
<html>
    <head>
        <title>BMI Calculator</title>
    <style> 
           h1{
    border: 2px solid ;
    padding: 15px;
    margin: 40px;
    text-align: center;
    border-radius: 10px;
    position: center;
    top: 200px;
    right: 1100px;
    font-size: xx-large;
    font-weight: bolder;
}
form{
    border: 5px  solid rgb(13, 13, 13);
    background-color: rgb(45, 123, 158) ;
    padding: 30px;
    margin: 100px;
    border-radius: 30px;
    width: 425px;
    position:center;
}


.footer {
    border-top: 1px solid #070707;
    padding-top: 20px;
    
}

    </style>
    </head>
    <body bgcolor="pink">
        <h1>BMI CALCULATOR</h1>
        <form method="POST">
            {%csrf_token%}
            <label>HEIGHT</label>
            <input type="text" name="height" value="{{h}}" ></input>(in cm)<br/>
            <label>WEIGHT</label>
            <input type="text" name="weight" value="{{w}}"></input>(in kg)<br/>
            <button type="submit">Calculate BMI</button>
              <h2>Your BMI:{{BMI}}</h2>

        </form>
        
<footer class="footer">
                <p>&copy; 2025 Dharshini (25008655)</p>
            </footer>
    </body>

</html>

urls.py

from django.contrib import admin 
from django.urls import path 
from myapp import views 
urlpatterns = [ 
    path('admin/', admin.site.urls), 
    path('Bmi_Calculator/',views.Bmi_Calculator,name="Bmi_Calculator"),
    path('',views.Bmi_Calculator,name="Bmi_Calculator")
]

views.py

from django.shortcuts import render 
def Bmi_Calculator(request): 
    context={} 
    context['BMI'] = "0" 
    context['h'] = "0" 
    context['w'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        h = request.POST.get('height','0')
        w = request.POST.get('weight','0')
        print('request=',request) 
        print('Height=',h)
        print('Weight=',w) 
        BMI = int(w) /int(h)*2
        context['BMI'] = BMI
        context['h'] = h
        context['w'] = w 
        print('BMI=',BMI) 
    return render(request,'myapp/math.html',context)


```


## SERVER SIDE PROCESSING:
![WhatsApp Image 2025-10-06 at 20 30 35_5f0000f8](https://github.com/user-attachments/assets/70bdf41b-cb59-4716-9e5a-2ff954360da6)

## HOMEPAGE:

![WhatsApp Image 2025-10-06 at 20 30 18_ae559764](https://github.com/user-attachments/assets/2c7be12d-29cb-4b24-93a7-0c71f2fdd8f2)



## RESULT:
The program for performing server side processing is completed successfully.
