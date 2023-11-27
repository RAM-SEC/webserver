# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
 <!doctype html>
 <html>
 <head>
 <title> My Web Server</title>
 </head>
 <body>
 <h1>Top Five Web Application Development Frameworks</h1>
 <h2>1.Django</h2>
 <h2>2. MEAN Stack</h2>
 <h2>3. React </h2>
 <h2>4. String </h2>
 <h2>5. MERN Stack</h2>
 </body>
 </html>
 '''

class MyServer(BaseHTTPRequestHandler):
     def do_GET(self):
         print("Get request received...")
         self.send_response(200) 
         self.send_header("content-type", "text/html")       
         self.end_headers()
         self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
## OUTPUT:
![serveroutput](https://github.com/RAM-SEC/webserver/assets/147473522/2e376f38-2c6c-461d-8286-6bce6fcb800d)
![clientoutput](https://github.com/RAM-SEC/webserver/assets/147473522/87159729-9bef-4355-9451-fe9b31cd7a8f)

## RESULT:
The program is executed succesfully
