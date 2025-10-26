# x)
## Karvinen 2025: Wireshark - Getting Started
- 
- 
- 
## Karvinen 2025: Network Interface Names on Linux
- 
- 
- 
# a)
Debian was already installed and works without issue

# b)
You can use 'ip route' to check your active interface.

I used the code 'sudo ip link set enp0s3 down' to disable my network interface.

Then i used 'sudo ip link set enp0s3 up' to re-enable it.
 
<img width="806" height="461" alt="Stopped_networking" src="https://github.com/user-attachments/assets/600cd5e0-fd12-4d12-b53d-0a2414d56c7d" />

# c)
I downloaded wireshark with 'sudo apt-get install wireshark' after which i used 'whoami' and 'sudo adduser *YOURNAME* wireshark' to add myself as a user.

Then i launched wireshark with 'wireshark' and started capturing my wifi packages and here is a small example of them.

<img width="1052" height="629" alt="Captured_traffic" src="https://github.com/user-attachments/assets/815c88fd-bdb7-45eb-a398-a00fcc424900" />

# d)
1. DNS is the Application layer
   - Application layer contains the communications protocol and interface methods used by computer networks.
2. UDP is the Transport layer
   - Protocols of this layer provide end-to-end communication services for applications.
3. Internet protocol is the Internet layer
   - This layer is used to transport network packets from the host across network boundaries.
4. Ethernet 2 or local are network or LAN is the Link layer
   - This is the group of methods and communication protocols confined to the link that that a host is physically connected to.

<img width="922" height="554" alt="d)_updated" src="https://github.com/user-attachments/assets/30189746-1688-4371-a44e-9af66a0737ad" />

# e)

- By going to Statistics -> endpoints tab in wireshark you can see Ethernet has 2 listed and IPv4 has 7 so this would mean there was 2 physical connections and 7 IP addresses.
- The most used protocols in this capture are DNS, QUIC, TCP and TLSv1.3
- You can see 283 packages captured this would tell you that the capture was very short maybe like 2 or 3 searches.

# g) 
# h)
# i)

