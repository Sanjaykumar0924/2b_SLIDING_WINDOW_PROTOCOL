# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

**CLIENT.PY**
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)
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
**SERVER.PY**
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT

![Screenshot 2024-03-06 201432](https://github.com/Roopsagar23001830/2b_SLIDING_WINDOW_PROTOCOL/assets/145972515/d9a92eee-e508-491a-912c-fdd1f87f182b)

![Screenshot 2024-03-06 200801](https://github.com/Roopsagar23001830/2b_SLIDING_WINDOW_PROTOCOL/assets/145972515/687d5a75-d8d2-4c90-88b6-5ac5386c8feb)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
