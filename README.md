# 2a_Stop_and_Wait_Protocol
## Name: THARUN D
## Reg.No: 212223240167
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
Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
## OUTPUT
![Screenshot 2025-04-12 133424](https://github.com/user-attachments/assets/6abb74b7-ed75-4f04-909f-d0b32a0b566d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
