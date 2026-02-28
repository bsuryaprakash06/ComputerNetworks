# 2a_Stop_and_Wait_Protocol
```
Name:B.Surya Prakash
Reg.no:212224230281
```
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
To write a python program to perform stop and wait protocol
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT
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
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
## CLIENT

![image](https://github.com/user-attachments/assets/8656848d-21da-41a1-9630-5af8ebf5b6e0)



## SERVER

![image](https://github.com/user-attachments/assets/5e7284b3-9bbd-4375-a738-13181b450253)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
