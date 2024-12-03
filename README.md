# Ex.05 Design a Website for Server Side Processing
## Date:28/11/24

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

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
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Power</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color:  turquoise;
}
.edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;
}
.box {
    display: inline-block;
    border: thick double rgb(59, 8, 116);
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: azure;
}
.formelt {
    color: black;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
}
h1 {
    color: black;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>Power</h1>
        <form method="POST">
            {% csrf_token %}
            <div class="formelt">
                Intensity (I): <input type="text" name="Intensity" value="{{Intensity}}"> w/m2<br/>
            </div>
            <div class="formelt">
                Resistance (R): <input type="text" name="Resistance" value="{{Resistance}}"> Ω<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"><br/>
            </div>
            <div class="formelt">
                Power (P): <input type="text" name="Power" value="{{Power}}"> W<br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>

views.py

from django.shortcuts import render 
def Power(request): 
    context={} 
    context['Power'] = "0" 
    context['I'] = "0" 
    context['R'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        I = request.POST.get('Intensity','0')
        R = request.POST.get('Resistance','0')
        print('request=',request) 
        print('Intensity=',I) 
        print('Resistance=',R) 
        Power = (int(I) * int(I)) * int(R)
        context['Power'] = Power
        context['I'] = I
        context['R'] = R
        print('Power=',Power) 
    return render(request,'myapp/maths.html',context)

    urls.py

    from django.contrib import admin 
from django.urls import path 
from mathsapp import views 
urlpatterns = [ 
    path('admin/', admin.site.urls), 
    path('Power/',views.Power,name="Power"),
    path('',views.Power,name="Power")
]

```

## SERVER SIDE PROCESSING:
![Screenshot (61)](https://github.com/user-attachments/assets/2d2e01a5-7a77-46a9-b43d-5283139564e3)

## HOMEPAGE:
![Screenshot (60)](https://github.com/user-attachments/assets/194c9fe0-c0f6-4905-8fe4-99fd785cad15)

## RESULT:
The program for performing server side processing is completed successfully.
