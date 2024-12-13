# EX01 Developing a Simple Webserver

# Date:13/09/2024
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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Laptop Configuration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            text-align: center;
            padding: 20px;
        }
        section {
            padding: 20px;
        }
        .config-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        .config-table th, .config-table td {
            padding: 12px;
            text-align: left;
            border: 1px solid #ddd;
        }
        .config-table th {
            background-color: #4CAF50;
            color: white;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: #333;
            color: white;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
<header>
    <h1>My Laptop Configuration</h1>
</header>
<section>
    <h2>Overview</h2>
    <p>This page presents the configuration of my laptop.</p>
    
    <h2>Configuration Details</h2>
    <table class="config-table">
        <tr>
            <th>Component</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core i7 11th Gen</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16GB DDR4</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>512GB SSD</td>
        </tr>
        <tr>
            <td>Graphics</td>
            <td>NVIDIA GeForce GTX 1650</td>
        </tr>
        <tr>
            <td>Operating System</td>
            <td>Windows 10 Pro</td>
        </tr>
    </table>
</section>

<footer>
    <p>&copy; 2024 My Laptop Configuration</p>
</footer>

</body>
</html>

"""
class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        # Send HTTP response code
        self.send_response(200)
        # Send headers (Content-Type: text/html)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        # Write the HTML content to the response body
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My web server is running...")
httpd.serve_forever()
```
# OUTPUT:

![Screenshot (17)](https://github.com/user-attachments/assets/c822f461-0e93-4933-8c9e-5109b8bb3086)
![Screenshot (19)](https://github.com/user-attachments/assets/cffe005e-9c76-44c4-a317-2711b131123b)



# RESULT:
The program for implementing simple webserver is executed successfully.
