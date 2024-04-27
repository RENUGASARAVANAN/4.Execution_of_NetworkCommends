# 4.Execution_of_NetworkCommands
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

# Program:
## Client:
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
## Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
## TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```


# Output:

## CLIENT:

![318471243-94b257b7-bc90-4764-a87c-ab7fae09e288](https://github.com/820NaveenKumar208/4.Execution_of_NetworkCommends/assets/154746066/b76270b5-b61b-431b-b7a4-8ad0b11e9cb0)

## SERVER:
![318471321-699ce24a-a2c9-4f94-a7b5-9fd7ecb6f981](https://github.com/820NaveenKumar208/4.Execution_of_NetworkCommends/assets/154746066/eb2d0c72-4601-40fc-8609-6a3e2b0d022c)

## TRACEROUTE COMMAND:

![318471408-e6700ae2-fe8f-4c02-b36c-a6e01786ff2a](https://github.com/820NaveenKumar208/4.Execution_of_NetworkCommends/assets/154746066/6b086cc2-4e28-4013-acf9-5ca3d934267d)

## Result
Thus Execution of Network commands Performed 
