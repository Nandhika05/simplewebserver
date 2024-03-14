# EX01 Developing a Simple Webserver
## Date:14/02/2024

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
   <title> Top Software companies with Revenue Table</title>
</head>
<body bgcolor="lavender">
  <table border="4" cellspacing="6" cellpadding="8" height="40" width="80">
<caption>Top Five Revenue software companies</caption>
<tr>
  <th>Company Name</th>
  <th>Rank</th>
  <th>Revenue</th>
  <th>Headquarters</th>
</tr>
<tr>
  <td>Microsoft</td>
  <td>1</td>
  <td>586.8</td>
  <td>Washington,USA</td>
</tr>
<tr>
  <td>Oracle</td>
  <td>2</td>
  <td>537.1</td>
  <td>Redwood city,CA,USA</td>
</tr>
<tr>
  <td>SAP</td>
  <td>3</td>
  <td>520.9</td>
  <td>Waldort,Germany</td>
</tr>
<tr>
  <td>Wincor Nixdorf</td>
  <td>4</td>
  <td>53.1</td>
  <td>Texces,USA</td>
</tr>
<tr>
  <td>Alphabet</td>
  <td>5</td>
  <td>45.3</td>
  <td>Washington,USA</td>
</tr>
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

## OUTPUT:

![Screenshot 2024-03-12 113122](https://github.com/Nandhika05/simplewebserver/assets/154419402/7bce1d3c-2857-4b89-9e42-56c055d2e8e9)

![Screenshot 2024-03-12 113751](https://github.com/Nandhika05/simplewebserver/assets/154419402/ffc05a3b-6671-451c-9616-799e545f7618)


## RESULT:
The program for implementing simple webserver is executed successfully.
