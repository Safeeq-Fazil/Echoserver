# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
### Server.py
```
import socket
HOST = "127.0.0.1" 
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024).decode()
            if not data:
                break
            conn.sendall(data.encode())

```

### Client.py
```
   
import socket
HOST = "127.0.0.1" 
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
       s.sendall(input().encode()) 
       data = s.recv(1024).decode()
       print(f"Received {data!r}")

```
## OUTPUT:
### Server Side:
![image](https://github.com/Safeeq-Fazil/Echoserver/assets/118680361/164e3b64-d410-446f-870a-b4fd62ae685a)



### Client Side:
![image](https://github.com/Safeeq-Fazil/Echoserver/assets/118680361/79688d9d-ee59-49d5-a8ac-4a66d2ecd624)


## RESULT:
The program is executed successfully
