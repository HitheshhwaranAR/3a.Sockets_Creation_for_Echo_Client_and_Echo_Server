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
### Client
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Client waiting for connection...")

c, addr = s.accept()
print("Connected with:", addr)

while True:
    clientMessage = c.recv(1024).decode()
    if not clientMessage:
        break
    c.send(clientMessage.encode())

c.close()
s.close()
```

### Server
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("client> ")
    if not msg:
        break
    s.send(msg.encode())
    print("server>", s.recv(1024).decode())

s.close()
```
## OUPUT
### Client
<img width="1653" height="513" alt="image" src="https://github.com/user-attachments/assets/f9edb969-9e44-47b2-b18c-49847f126c93" />

### Server
<img width="1501" height="560" alt="image" src="https://github.com/user-attachments/assets/b9772595-c691-4f66-9ad7-f551eabda3ed" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
