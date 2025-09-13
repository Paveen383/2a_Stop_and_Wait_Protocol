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
## PROGRAM:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
<img width="1036" height="446" alt="Screenshot 2025-09-13 141646" src="https://github.com/user-attachments/assets/2d0633b6-92db-4d76-bca0-6f449b9f7993" />
<img width="1034" height="377" alt="Screenshot 2025-09-13 141659" src="https://github.com/user-attachments/assets/c2e39e51-be60-477f-b708-e28be4578d86" />
## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
