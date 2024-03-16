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
![image](https://github.com/Safeeq-Fazil/Echoserver/assets/118680361/59fa91d8-23bd-43a6-8229-98bdc9dcec58)


### Client Side:
![image](https://github.com/Safeeq-Fazil/Echoserver/assets/118680361/9b9e9339-88aa-4f35-8f5f-12a0974c93d4)


## RESULT:
The program is executed successfully
