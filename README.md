# 2c.SIMULATING ARP /RARP PROTOCOLS
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
## PROGRAM - ARP
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
![311234045-e10774b9-ceb0-4dd4-a4a4-dff2626aa0cc](https://github.com/codedbykishore/2c.ARP_RARP_PROTOCOLS/assets/147139122/8a11a159-da35-430a-8648-1c72c23197aa)


## PROGRAM - RARP
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
![311234096-8eb0efa1-301c-4494-86c0-b26edf7d8493](https://github.com/codedbykishore/2c.ARP_RARP_PROTOCOLS/assets/147139122/b95c17b8-461c-454c-94ee-d520c594e08d)


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
