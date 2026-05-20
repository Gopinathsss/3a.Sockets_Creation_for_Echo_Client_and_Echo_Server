# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
##client
```
import socket

client = socket.socket()

client.connect(('localhost', 8000))

print("Connected to server")

while True:

    msg = input("Client: ")

    client.send(msg.encode())

    if msg.lower() == "exit":
        print("Connection closed")
        break

    server_reply = client.recv(1024).decode()

    print("Server:", server_reply)

    if server_reply.lower() == "exit":
        print("Server closed the connection")
        break

client.close()
```
## sever
```
import socket

server = socket.socket()

server.bind(('localhost', 8000))

server.listen(1)

print("Server waiting for connection...")

conn, addr = server.accept()

print("Connected to:", addr)

while True:

    client_msg = conn.recv(1024).decode()

    print("Client:", client_msg)

    if client_msg.lower() == "exit":
        print("Client disconnected")
        break

    server_msg = input("Server: ")

    conn.send(server_msg.encode())

    if server_msg.lower() == "exit":
        print("Server disconnected")
        break

conn.close()
server.close()

```
## OUPUT
#client
<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/0af10cba-eb24-4032-b23e-f3f4e3c3114b" />
#server
<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/94a843d7-4c55-41de-bdd8-17b81c0c9f78" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
