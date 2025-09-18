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
# echo-client.py

import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the serve
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")

## OUTPUT:
<img width="1316" height="436" alt="image" src="https://github.com/user-attachments/assets/4568310a-7dbe-4b15-a32e-655484358375" />
<img width="1263" height="413" alt="image" src="https://github.com/user-attachments/assets/f644c9cb-7459-44e9-bad1-06401028df80" />

## RESULT:
The program is executed successfully
