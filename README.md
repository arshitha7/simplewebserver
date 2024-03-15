# EX01 Developing a Simple Webserver
## Date:24/02/2024

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
	<head>
		<title>EXP1</title>
	</head>
	<body>
	<table border="3" cellspacing="2" cellpadding="10" width="1000" height="60">
        <caption> TOP 10 SOFTWARE COMPANIES IN REVENUE </caption>
		<tr>
			<th>RANK</th>
			<th>COMPANY</th>
			<th>SALES</th>
            <th>NATIONALITY</th>
		</tr>
		<tr>
			<td>1</td>
			<td>Microsoft</td>
			<td>57.9</td>
            <td>USA</td>
        </tr>
		<tr>
			<td>2</td>
			<td>Oracle</td>
			<td>21.0</td>
            <td>USA</td>
		</tr>
		<tr>
            <td>3</td>
			<td>SAP</td>
			<td>16.1</td>
            <td>Germany</td>

		</tr>
        <tr>
            <td>4</td>
			<td>Computer Associates</td>
			<td>4.2</td>
            <td>USA</td>

		</tr>
        <tr>
            <td>5</td>
			<td>Adobe</td>
			<td>3.4</td>
            <td>USA</td>

		</tr>
        <tr>
            <td>6</td>
			<td>Electronic Arts</td>
			<td>3.2</td>
            <td>USA</td>

		</tr>
        <tr>
            <td>7</td>
			<td>Amdocs</td>
			<td>2.9</td>
            <td>USA</td>

		</tr>
            <tr>
            <td>8</td>
			<td>Intuit</td>
			<td>2.8</td>
            <td>USA</td>

		</tr>
        <tr>
            <td>9</td>
			<td>Activision</td>
			<td>2.6</td>
            <td>USA</td>

		</tr>
        <tr>
            <td>10</td>
			<td>Autodesk</td>
			<td>2.2</td>
            <td>USA</td>

		</tr>
	</table>
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
![output1](<Screenshot 2024-03-15 090908.png>)


![output2](<Screenshot (1).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
