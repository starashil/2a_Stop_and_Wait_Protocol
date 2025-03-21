# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## Client:

import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True:
    ip=c.recv(1024).decode() 
    try:
        c.send(address[ip].encode()) 
    except KeyError:
        c.send("Not Found".encode())  

## Server:

import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())


## OUTPUT

![Screenshot (105)](https://github.com/user-attachments/assets/c2fc48e7-b1f0-431a-9a79-4c1ec6fb08f7)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
