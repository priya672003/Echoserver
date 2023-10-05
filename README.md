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

### Server Code
### echo server.py 

```python3

import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```


### Client Code 

### echo client .py
```python3

import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```
## OUTPUT:
### SERVER OUTPUT :

![image](https://github.com/priya672003/Echoserver/assets/81132849/a35140e9-ccd1-44f2-b282-210ab4c57a9b)

### CLIENT OUTPUT : 

![image](https://github.com/priya672003/Echoserver/assets/81132849/3259614c-8ff5-4224-8e64-3133ceb4297f)


## RESULT:
The program is executed successfully
