## name: ponguru aasrith sairam
## reg. no: 212223240116
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
# client:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
  s.bind((HOST, PORT))
  s.listen()
  conn, addr = s.accept()
  with conn:
    print('Connected by', addr)
    while True:
      data = conn.recv(1024)
      if not data:
        break
      conn.sendall(data)
```
# server:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
   s.connect((HOST, PORT))
   while True:
      message = input("Enter message to send to server: ")
      s.sendall(message.encode())
      data = s.recv(1024)
      print('Received', repr(data.decode()))
```
## OUPUT
# client:
![image](https://github.com/AasrithSairam/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/139331438/120c605c-6dd7-4303-8715-c48d3797b290)
# server:
![image](https://github.com/AasrithSairam/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/139331438/ce82cb7e-a0f2-4ca8-83b9-f1d1a86a1e11)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
