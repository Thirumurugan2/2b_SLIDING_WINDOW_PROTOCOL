# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
# client output:
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
# server output:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUTPUT:
# Client output:

![310176120-04e31cd7-16ce-4d98-9f46-31de101427c4](https://github.com/Thirumurugan2/2b_SLIDING_WINDOW_PROTOCOL/assets/162677168/0078b274-e743-46b4-bc8c-280eed210ff6)

#server output
![310176279-72cd4465-2f77-4c46-a3ff-565df01321f1](https://github.com/Thirumurugan2/2b_SLIDING_WINDOW_PROTOCOL/assets/162677168/8f9f6ea7-ce4a-4193-b997-b2914a7eef93)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
