# Ex03 Time Table
# Date:20.10.2024
# AIM
To write a html webpage page to display your slot timetable.

# ALGORITHM
## STEP 1
Create a Django-admin Interface.

## STEP 2
Create a static folder and inert HTML code.

## STEP 3
Create a simple table using `<table>` tag in html.

## STEP 4
Add header row using `<th>` tag.

## STEP 5
Add your timetable using `<td>` tag.

## STEP 6
Execute the program using runserver command.

# PROGRAM
```


views.py

from http.server import BaseHTTPRequestHandler, HTTPServer
from importlib.resources import contents
from django.http import HttpResponse
from django.shortcuts import render

content='''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SLOT TIME TABLE</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        img {
            width: 800px;
            margin-bottom: 20px;
        }
        h1 {
            text-align: center;
            margin-bottom: 20px;
        }
        table {
            border: 1px;
            width: 100%;
            max-width: 1000px; /* Adjust this value as needed */
            margin-bottom: 20px;
        }
        th, td {
            border: 1px;
            text-align: center;
            padding: 10px;
        }
        th {
            background-color: rgb(224, 244, 10);
            color: white;
        }
        td {
            background-color: rgb(8, 210, 190);
        }
    </style>
</head>
<body>
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTfVHM7lQHBY3fMmzXE1m0bYnMg3dsccFDu2g&s" width="1200px">
    <h1>SLOT TIME TABLE-SANTHOSH.V(24901020)</h1>
    <table>
        <tr>
        <th>Day/time</th>
        <th>Monday</th>
        <th>Tuesday</th>
        <th>Wednesday</th>
        <th>Thursday</th>
        <th>Friday</th>
        <th>Saturday</th>
        </tr>
        <tr>
        <th>8-10</th>
        <td>FREE SLOT</td>
        <td>BEEM</td>
        <td>CRYPTO</td>
        <td>FREE SLOT</td>
        <td>PHYSICS</td>
        <td>FREE SLOT</td>
        </tr>
        <tr>
           <th>10-12</th>
           <td>CRYPTO</td>
           <td>PHYSICS</td>
           <td>BEEM</td>
           <td>CARRIER DEVOLPMENT</td>
           <td colspan="2">WEB DEVOLPMENT</td>
        </tr>
        <tr>
            <th>12-1</th>
            <td colspan="6">LUNCH</td>
        </tr>
        <tr>
            <th>1-3</th>
            <td>WEB DEVOLPMENT</td>
            <td>C PROGRAMMING</td>
            <td>MENTOR MEET</td>
            <td colspan="2">Statistics</td>
            <td>C PROGRAMMING</td>
        </tr>
        <tr>
            <th>3-5</th>
            <td colspan="6">FREE SLOT</td>
        </tr>
    </table>
    <br>
    
    <table>
        <tr>
            <th>S.No</th>
            <th>Subject Code</th>
            <th>Subject Name</th>
        </tr>
        <tr>
            <td>1.</td>
            <td>19AI414</td>
            <td>Fundamentals of Web Application Department</td>
    
        </tr>
        <tr>
            <td>2.</td>
            <td>19AI304</td>
            <td>Fundamentals of C Programming</td>
        </tr>
        <tr>
            <td>3.</td>
            <td>19MA211</td>
            <td>Statistics and Numerical Methods</td>
        </tr>
        <tr>
            <td>4.</td>
            <td>SH3214</td>
            <td>Physics for Quantum Computing</td>
        </tr>
        <tr>
            <td>5.</td>
            <td>19EE305</td>
            <td>Basic Electrical,Electionics and Measurement Engineering</td>
        </tr>
        <tr>
            <td>6.</td>
            <td>19CS547</td>
            <td>Fundamentals of Cryptocurrency</td>
        </tr>
        <tr>
            <td>7.</td>
            <td>19EY708</td>
            <td>Career Development Skills</td>
        </tr>
        <tr>
            <td>8.</td>
            <td>ECA-M-SCOFT</td>
            <td>Mentor Meet</td>
        </tr>
    </table>
</body>
</html>'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

urls.py

from tempfile import template
from django.contrib import admin
from django.urls import path
from app1.views import MyServer

urlpatterns = [
    path('admin/', admin.site.urls),
    # path('new/',views.trial),
    # path('page/',views.slot),
    # path('home/',template.slot),
    path('server/',MyServer.as_view())
]



```

# OUTPUT
![Screenshot 2024-12-07 112406](https://github.com/user-attachments/assets/77e69afe-ec94-4619-a4ea-f57e662d26ef)
![Screenshot 2024-12-07 112104](https://github.com/user-attachments/assets/8d7ab08f-2412-40cb-9311-48452e84dc5f)



# RESULT
The program for creating slot timetable using basic HTML tags is executed successfully.
