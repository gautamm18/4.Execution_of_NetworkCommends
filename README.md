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


##program
```
Server.py
import socket
from pythonping import ping
s = socket.socket()
# Bind to localhost and port
s.bind(('localhost', 8000))
# Listen for connections
s.listen(5)
print("Ping Server started... Waiting for connection")
# Accept connection
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    if not hostname:
        break
    try:
        result = ping(hostname, count=4, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Host Not Found".encode())
c.close()

Client.py
import socket
# Create socket
s = socket.socket()
# Connect to server
s.connect(('localhost', 8000))
while True:
    website = input("Enter the website you want to ping: ")
    if website.lower() == "exit":
        break
    s.send(website.encode())
    result = s.recv(1024).decode()
    print("\nPing Result:\n", result)
s.close()

Traceroute.py
import os
print("Running Traceroute...\n")
os.system("C:\\Windows\\System32\\tracert.exe google.com")
```

## Output
1.Ping
<img width="844" height="353" alt="image" src="https://github.com/user-attachments/assets/cc321c4f-3b86-470a-a48b-106974c5f6d4" />

2.Tracet
<img width="1046" height="561" alt="image" src="https://github.com/user-attachments/assets/dbaac5aa-049e-4075-8d6b-dda2b9f260e3" />

3.ipconfig
<img width="984" height="719" alt="image" src="https://github.com/user-attachments/assets/b737621d-b586-4cd2-9a1a-ba8f8699576f" />

4.netstat
<img width="886" height="909" alt="image" src="https://github.com/user-attachments/assets/050612ce-47c4-4e49-92cc-5250f4bdb228" />

5.nslookup
<img width="799" height="555" alt="image" src="https://github.com/user-attachments/assets/c77ff18d-a1b4-44e1-81fa-48e8e2ef52f7" />



## Result
Thus Execution of Network commands Performed 
