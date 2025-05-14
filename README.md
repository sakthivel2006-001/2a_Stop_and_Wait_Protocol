# EX:2a_Stop_and_Wait_Protocol
## AIM
## Name:SAKTHIVEL S
## REG NO: 212223220090
To write a python program to perform stop and wait protocol

## ALGORITHM

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM
```
CLIENT:
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
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT

CLIENT:

![Screenshot 2025-04-28 082001](https://github.com/user-attachments/assets/f8308302-0fa3-4e39-85bf-0241da7f654b)

SERVER:


![Screenshot 2025-04-28 082050](https://github.com/user-attachments/assets/c3a270a3-54c0-45e0-ba92-8088c3f6d898)

## RESULT

Thus, python program to perform stop and wait protocol was successfully executed.
