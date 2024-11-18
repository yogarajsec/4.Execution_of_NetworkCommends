# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer
All commands related to Network configuration which includes how to switch to privilege mode
and normal mode and how to configure router interface and how to save this configuration to
flash memory or permanent memory.
This commands includes
• Configuring the Router commands
• General Commands to configure network
• Privileged Mode commands of a router
• Router Processes & Statistics
• IP Commands
• Other IP Commands e.g. show ip route etc.
## PROGRAM:
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
## Client![328395645-a71fd251-4981-4a47-895e-397385132009](https://github.com/user-attachments/assets/3d9c88e1-6378-462f-b236-4fce69962046)

## Server![328395773-798a1a24-2784-46a9-916a-ec8552ecd907](https://github.com/user-attachments/assets/2dadc626-aef4-41d9-a8cd-d4a2af2e82b0)

## Tranceroute command![328395891-ce4aa790-9cc7-427a-8860-e4a5f40b1076](https://github.com/user-attachments/assets/314efb1f-7ee6-48d2-a37e-b5fba411cfb5)


## Result
Thus Execution of Network commands Performed 
