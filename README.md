# 2a_Stop_and_Wait_Protocol
### NAME:GOKUL S
### REF.NO:212223040051
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
### CLIENT:
~~~PYTHON
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
~~~
### SERVER:
~~~PYTHON
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
~~~ 
## OUTPUT
## CLIENT
![image](https://github.com/SGokul2005/2a_Stop_and_Wait_Protocol/assets/147121825/12a99eb6-b34e-4e95-b6f0-e3cbc12c42bb)
## SERVER:
![image](https://github.com/SGokul2005/2a_Stop_and_Wait_Protocol/assets/147121825/92ee0d98-6130-47a5-9f1e-86d7d72820c0)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
