# EX01 Developing a Simple Webserver
## Date:6/3/2024

## AIM:
To develop a simple webserver to serve html pages.

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

```from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<h1 align="center">SOFTWARE COMPANIES<h1>
<title>
TOP SOFTWARE COMPANIES WITH HIGH REVENUES
</title>
</head>
<body bgcolor="cyan">
<table border="3" align="center">
<caption>TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES</caption>
  <tr>
    <td>SNO</td>
    <td>Companies</td>
    <td>Revenue</td>
  </tr>
  <tr>
    <td>1.</td>
    <td>APPLE</td>
    <td>$385.70 B</td>
  </tr>
<tr>
    <td>2.</td>
    <td>Alphabet (Google)</td>
    <td>$307.39 B</td>
  </tr>
<tr>
    <td>3.</td>
    <td>Microsoft</td>
    <td>$227.58 B</td>
  </tr>
<tr>
    <td>4.</td>
    <td>IBM</td>
    <td>$61.85 B</td>
  </tr>
<tr>
    <td>5.</td>
    <td>Oracle</td>
    <td>$51.62 B </td>
  </tr>
</table>

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
![image](https://github.com/magesh534/simplewebserver/assets/135577936/f30fe500-ce3f-4566-8ec7-98ddccfe26a4)
![image](https://github.com/magesh534/simplewebserver/assets/135577936/fc023054-09ca-4a64-941d-adc8dc73cd8b)


## RESULT:
The program for implementing simple webserver is executed successfully.
