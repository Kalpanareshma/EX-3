# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# DATE : 23.03.2023
# AIM :
To write a python program to perform sliding window protocol
# ALGORITHM :

### STEP 1: Start the program.
### STEP 2: Get the frame size from the user.
### STEP 3: To create the frame based on the user request.
### STEP 4: To send frames to server from the client side.
### STEP 5: If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
### STEP 6: Stop the program.

## CLIENT PROGRAM :
## Developed : Kalpana S
## Reg no : 212222040069
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
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
 ```
### SERVER OUTPUT :
![ex03 server output](https://github.com/Kalpanareshma/EX-3/assets/122040453/8f515237-b638-4965-8ef8-541bdfa1a418)
## CLIENT OUTPUT :
![ex03 client output](https://github.com/Kalpanareshma/EX-3/assets/122040453/6289f3d9-04c9-4cf5-9aed-54b7a781f120)

## RESULT :
Thus, python program to perform stop and wait protocol And Sliding Window Protocol was successfully executed.
