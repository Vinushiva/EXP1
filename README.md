# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>List of Protocols in TCP/IP Protocol Suite</title>
  <style>
    :root{
      --frame-bg: #3a3a3a;
      --inner-shadow: rgba(0,0,0,0.7);
      --cell-bg: #bfeef2;
      --header-bg: #bfeef2;
      --title-color: #333;
    }

    body{
      background: #fff;
      font-family: "Times New Roman", Times, serif;
      display:flex;
      justify-content:center;
      padding:32px;
    }

    .frame {
      border: 8px solid var(--frame-bg);
      padding: 8px;
      box-shadow: 8px 8px 0 var(--inner-shadow);
      max-width: 1000px;
      width: 100%;
    }

    h1.title{
      text-align:center;
      font-size:28px;
      margin:8px 0 14px;
      font-weight: 700;
      color: var(--title-color);
      text-transform: none;
    }

    table.protocols {
      width: 100%;
      border-collapse: collapse;
      table-layout: fixed;
      background: transparent;
    }

    .protocols th,
    .protocols td {
      border: 2px solid #7a7a7a;
      padding: 26px 18px;
      vertical-align: middle;
      word-wrap: break-word;
    }

    .protocols thead th {
      background: var(--header-bg);
      font-size:18px;
      font-weight:700;
    }

    .protocols tbody td {
      background: var(--cell-bg);
      font-size:20px;
      font-weight:600;
      color:#123; 
    }

    .col-sno { width: 12%; }
    .col-layer { width: 44%; }
    .col-proto { width: 44%; }

    .protocols tbody td:first-child {
      text-align:center;
      font-weight:700;
    }

    @media (max-width:700px){
      .protocols thead th, .protocols tbody td { padding:16px 8px; font-size:16px; }
    }
  </style>
</head>
<body>
  <div class="frame">
    <h1 class="title">List of Protocols in TCP/IP <br>Practical Suite:-</h1>

    <table class="protocols" aria-label="TCP/IP Protocol Suite">
      <thead>
        <tr>
          <th class="col-sno">S.No.</th>
          <th class="col-layer">Name of the layer</th>
          <th class="col-proto">Name of the Protocol</th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <td>1</td>
          <td>Application Layer</td>
          <td>HTTP, FTP, DNS, Telnet &amp; SSH</td>
        </tr>

        <tr>
          <td>2</td>
          <td>Transport Layer</td>
          <td>TCP / UDP</td>
        </tr>

        <tr>
          <td>3</td>
          <td>Network Layer</td>
          <td>IPv4 / IPv6</td>
        </tr>

        <tr>
          <td>4</td>
          <td>Link Layer</td>
          <td>Ethernet</td>
        </tr>
      </tbody>
    </table>
  </div>
</body>
</html>

"""

class myhandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address, myhandler)
print("my webserv webserver is running...")
httpd.serve_forever()

```


## OUTPUT:
![alt text](<Screenshot 2025-11-02 130051.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
