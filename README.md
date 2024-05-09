# 2c.SIMULATING ARP /RARP PROTOCOLS
# NAME:PRASANNA I
REG NO:212223220079
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
### CLIENT:
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode()) 
```
## OUPUT - ARP
![image](https://github.com/prasanna2006I/2c.ARP_RARP_PROTOCOLS/assets/150161282/35984b8e-5e90-4733-9849-b7611a079534)

## PROGRAM - RARP
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![image](https://github.com/prasanna2006I/2c.ARP_RARP_PROTOCOLS/assets/150161282/87f0420d-06cd-4cad-8f41-382e8a9a8c80)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
