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
7. 
## PROGRAM
 CLIENT
 ```
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
SERVER
```
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

## OUTPUT
CLIENT OUTPUT

![image](https://github.com/mdgj2005/2a_Stop_and_Wait_Protocol/assets/145533936/e90de383-1788-4f0a-a947-8fc563114f17)

SERVER OUTPUT

![image](https://github.com/mdgj2005/2a_Stop_and_Wait_Protocol/assets/145533936/28b13789-41b1-4dc1-9451-3303d916c98e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
