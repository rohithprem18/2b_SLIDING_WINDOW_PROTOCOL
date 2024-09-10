# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### NAME: ROHITH PREM S
### REG.NO:212223040172
## AIM
To write a python program for Implementation of sliding Window Protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Server
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
### Client
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### Client
![Screenshot 2024-09-10 083905](https://github.com/user-attachments/assets/d12610a1-7b7a-4808-8248-ca258cb62f38)

### Server
![Screenshot 2024-09-10 083915](https://github.com/user-attachments/assets/d68ad870-9ce1-4e5d-9bf7-c82b48241780)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
