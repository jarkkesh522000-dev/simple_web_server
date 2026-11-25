# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """<!DOCTYPE html>
<html>
<head>
    <title>MY LAPTOP INFO</title>
</head>
<body>
    <h1 align="center">MY LAPTOP INFO</h1>
    <table border="1" cellpadding="10" cellspacing="0" align="center">
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Model Name</td>
            <td>TL15-53M-G2</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <td>Graphics card</td>
            <td>Intel(R) Graphics (128 MB)</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>135 GB of 477 GB used</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>293A0BE5-947B-4751-8D5C-E68EBE3F1C22</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00342-42954-11725-AAOEM</td>
        </tr>
        <tr>
            <td>System type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>"""

class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get Request Recived...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ("", 8000)
httpd = HTTPServer(server_address, Myserver)
httpd.serve_forever()
# OUTPUT:
<img width="813" height="701" alt="Screenshot 2026-11-25 213945" src="https://github.com/user-attachments/assets/0ab7c57a-df2d-4d76-b256-e92780584011" />

# RESULT:
The program for implementing simple webserver is executed successfully.
