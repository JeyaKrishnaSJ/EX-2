# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# DATE: 16/03/23

# AIM : 
To write a python program to perform stop and wait protocol

# ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program
```
# PROGRAM :
# CLIENT PROGRAM:
```
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
# SERVER PROGRAM:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
 ```
# OUTPUT :
# CLIENT OUTPUT :
![client2](https://github.com/JeyaKrishnaSJ/EX-2/assets/118707091/01198342-44dd-48e7-bfed-9bdf54c9a1e9)

# SERVER OUTPUT :
![server2](https://github.com/JeyaKrishnaSJ/EX-2/assets/118707091/8f498873-f50a-4bd9-b366-767427d67fd2)


# RESULT : 

Thus, python program to perform stop and wait protocol was successfully executed.



