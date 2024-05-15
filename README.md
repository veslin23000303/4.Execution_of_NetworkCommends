# 4.Execution_of_NetworkCommands
### NAME: VESLIN ANISH A
### REG.NO:212223240175

## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## PROGRAM

## Ping command
## Client
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
## Server
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
## Tranceroute command
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## OUTPUT
## Ping command
## Client
![Screenshot 2024-05-15 103812](https://github.com/veslin23000303/4.Execution_of_NetworkCommends/assets/151148539/9f832446-bca7-4702-94c8-38a5677d2111)


## Server
![Screenshot 2024-05-15 103820](https://github.com/veslin23000303/4.Execution_of_NetworkCommends/assets/151148539/359dcf70-8d71-4426-9965-0c0c3ad5855c)


## Tranceroute command
![Screenshot 2024-05-15 103830](https://github.com/veslin23000303/4.Execution_of_NetworkCommends/assets/151148539/2d5767dc-31ef-4c5f-bb47-66bb52cdb418)


## Result
Thus Execution of Network commands Performed 
