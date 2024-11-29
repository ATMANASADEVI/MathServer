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
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Power</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color:burlywood;
            margin: 0;
            padding: 20px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            background: beige;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            color: #333;
        }
        label {
            display: block;
            margin-top: 10px;
            color: #555;
        }
        input {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 10px;
            margin-top: 20px;
            background-color:blue;
            color: azure;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: burlywood;
        }
        .result {
            margin-top: 20px;
            padding: 10px;
            background:blue;
            border: 1px ;
            border-radius: 5px;
            color: brown;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Power</h1>
        <form id="powerForm">
            <label for="intensity">Intensity (I) in Amps:</label>
            <input type="number" id="intensity" step="any" required>

            <label for="resistance">Resistance (R) in Ohms:</label>
            <input type="number" id="resistance" step="any" required>

            <button type="submit">Calculate Power</button>
        </form>
        <div id="result" class="result" style="display: none;"></div>
    </div>
</body
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


## HOMEPAGE:


## RESULT:
The program for performing server side processing is completed successfully.
