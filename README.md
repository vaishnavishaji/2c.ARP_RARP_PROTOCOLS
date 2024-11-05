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
P
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
![366398577-abb108c8-b1aa-4cb3-a17f-066e916d4e29](https://github.com/user-attachments/assets/e57b7351-b7ce-4e76-8af8-6b797bce41b1)

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
![366399046-2bcfde1b-9896-4a01-9c5a-384e6134ddce](https://github.com/user-attachments/assets/3a6390d6-3e20-4e86-a304-89f605c3447e)


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
