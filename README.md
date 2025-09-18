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
```
Name : NAVEEN KUMAR P
Regno: 212224240102

```
```python
# echo-server.py

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
```python

# echo-client.py

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
<img width="1262" height="412" alt="server" src="https://github.com/user-attachments/assets/d2e25444-543c-4223-ad9a-6c1dad328d8e" />

<img width="1316" height="436" alt="client" src="https://github.com/user-attachments/assets/7f3336b8-6385-43fd-ab2b-6da43318dd42" />

## RESULT:
The program is executed successfully

