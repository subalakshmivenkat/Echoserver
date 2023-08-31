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
Server code


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
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
 

## OUTPUT:
# echo-server.py

![264606709-d17e161a-3eac-4267-82fc-a460727cb567](https://github.com/subalakshmivenkat/Echoserver/assets/119393477/59ce6815-2ae5-49c5-a016-09bac29dc0ed)

# echo-client.py

![264606750-4f7e5971-8a84-42cc-b1de-5f295f686962](https://github.com/subalakshmivenkat/Echoserver/assets/119393477/edc8ded5-347f-4a3f-9250-e759e68079c0)


## RESULT:
The program is executed successfully
