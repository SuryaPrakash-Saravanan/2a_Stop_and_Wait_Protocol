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


server.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
print(s.recv(1024).decode()) 
s.send("Acknowledgement Recived".encode())
```

client.py
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
i=input("Enter a data: ") 
c.send(i.encode()) 
Type your text 
ack=c.recv(1024).decode() 
if ack: 
print(ack) 
continue 
else: 
c.close() 
break 
```
## OUTPUT

server

<img width="863" height="232" alt="2a server" src="https://github.com/user-attachments/assets/a2454d01-6ad9-4412-ad17-3c388a243f36" />


client

<img width="842" height="270" alt="2a client" src="https://github.com/user-attachments/assets/d608ab54-54c6-4a2e-8039-6b16b6e6a71f" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
