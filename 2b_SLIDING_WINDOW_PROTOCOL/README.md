# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
To implement the Sliding Window Protocol using socket programming in Python to simulate reliable frame transmission between a client and a server.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
# Client
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
# Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())

```
## OUTPUT
## CLIENT

![image](https://github.com/user-attachments/assets/06ebb921-aeb5-4406-be63-ab6b4250b8e3)


## SERVER

![image](https://github.com/user-attachments/assets/71f81b0c-ad58-4a73-a30b-52be382a011c)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
