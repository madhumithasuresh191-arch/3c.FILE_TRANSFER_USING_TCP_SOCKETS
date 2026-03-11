# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## Name:S Madhumitha
## Reg no:212224050217
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
server
~~~
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    ClientMessage=c.recv(1024).decode()
    print("Client > ",ClientMessage)
    msg=input("Server > ")
    c.send(msg.encode())
~~~
client
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    print("Server > ",s.recv(1024).decode())
~~~
## OUPUT
server
![cn ex 3c client](https://github.com/user-attachments/assets/5e1cc6c7-c94b-45a1-a1de-547909cee120)

client
![cn ex 3c server](https://github.com/user-attachments/assets/18480100-19d7-4561-b72d-e87d94324339)

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
