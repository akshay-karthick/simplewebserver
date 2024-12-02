# EX01 Developing a Simple Webserver
## Date:
19/10/2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
##  
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <body bgcolour="violet">
        <h1 align="center">LAPTOP SPECIFICATIONS (Akshay Karthick ASR,24002815) </h1>
        <ol>
        <li>Device name - DESKTOP-MOHHBTU</li>
        <li>Processor - 13th Gen Intel(R) Core(TM) i5-1335U 1.30 GHz</li>
        <li>RAM - 16gb</li>
        <li>Device ID - 15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
        <li>System Type - 64 bit </li></ol>
    </body>
</html>    
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot (28).png>)
![alt text](<Screenshot (29).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
