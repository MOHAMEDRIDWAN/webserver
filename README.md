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

## HTML:
```
<!DOCTYPE html>
<html>
<head>
  <title>Using Python's SimpleHTTPServer Module</title>
  <style>
    #rectangle {
      height: 120px;
      width: 100px;
      background-color: #00f28f;
    }
  </style>
</head>
<body>
  <h2>Rectangle served by SimpleHTTPServer</h2>
  <div id="rectangle">
    <p>GOOGLE</p>
    <p>FACEBOOK</p>
    <p>AMAZON</p>
    <p>VDART</p>

  </div>
</body>
</html>
```
## PYTHON CODE:
```
import http.server
import socketserver

class MyHttpRequestHandler(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        if self.path == '/':
            self.path = 'mywebpage.html'
        return http.server.SimpleHTTPRequestHandler.do_GET(self)

# Create an object of the above class
handler_object = MyHttpRequestHandler

# Set the port number for the server
PORT = 8080

# Create the server and bind it to the specified port
my_server = socketserver.TCPServer(("", PORT), handler_object)

print(f"Serving on port {PORT}....")

# Start the server - run indefinately
my_server.serve_forever()
```
## PYTHON CODE 2:
```
import http.server
import socketserver

class MyHttpRequestHandler(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        if self.path == '/':
            self.path = 'mywebpage.html'
        return http.server.SimpleHTTPRequestHandler.do_GET(self)

# Create an object of the above class
handler_object = MyHttpRequestHandler

# Set the port number for the server
PORT = 8080

# Create the server and bind it to the specified port
my_server = socketserver.TCPServer(("", PORT), handler_object)

print(f"Serving on port {PORT}....")

# Start the server - run indefinately
my_server.serve_forever()
```

## OUTPUT:
<img width="922" alt="image" src="https://github.com/MOHAMEDRIDWAN/webserver/assets/146993368/a602a26a-bdc1-45bb-8942-3a1ea62c00dc">


## RESULT:
The program is executed succesfully
