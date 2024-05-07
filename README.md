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
## Client
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
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## Client:
![image](https://github.com/Pavithrasaravanakumar/2a_Stop_and_Wait_Protocol/assets/150664013/14689e07-2b25-4e02-9012-bf7edc766294)
## Server:
![image](https://github.com/Pavithrasaravanakumar/2a_Stop_and_Wait_Protocol/assets/150664013/23e26fb7-3a5e-4304-8504-70451ffb2444)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
