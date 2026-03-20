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

## Server.py
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived from the server".encode())
```

## Client.py
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
## OUTPUT

## Server

<img width="1113" height="250" alt="image" src="https://github.com/user-attachments/assets/00c348d5-0f4c-4c4f-8116-a408e143f4ad" />

## Client

<img width="1116" height="260" alt="image" src="https://github.com/user-attachments/assets/6f0b64aa-39cb-4a1c-a0d4-02b379f34908" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
