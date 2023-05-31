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
![ex-03](https://github.com/Kalpanareshma/EX-3/assets/122040453/2b0ade94-9cda-40d1-b1bf-869e2abd36ba)
## CLIENT OUTPUT :
![ex-03 client](https://github.com/Kalpanareshma/EX-3/assets/122040453/47e9939f-4b12-4703-b767-8c13776a3125)
## RESULT :
Thus, python program to perform stop and wait protocol And Sliding Window Protocol was successfully executed.
