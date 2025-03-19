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
### echo-server.py
```
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

### echo-client.py
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello,World")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## OUTPUT:
### echo-server.py

<img src="https://github.com/user-attachments/assets/4a3b28db-eb3a-43a9-a409-43578fecb517" width=600>

### echo-client.py

<img src="https://github.com/user-attachments/assets/df272f7b-1693-404f-a2fe-c7176333bb03" width=600>



## RESULT:
The program is executed successfully
