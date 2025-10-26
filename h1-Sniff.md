# x)
## Karvinen 2025: Wireshark - Getting Started
- This is an article that has a tutorial on how to install wireshark on Debian linux and how to get started using it.
- It also includes some troubleshooting tips if no packets are being captured.
   - the tip given is to search the web and if that fails maybe you're not in group to which you can see the instructions on how to do that earlier in the guide
- It also has some instuctions on viewing captures

source: https://terokarvinen.com/wireshark-getting-started/
## Karvinen 2025: Network Interface Names on Linux
- This article explains Network Interdace Names (like wlps4s and enp1s0) mean.
- it also tells you how to check your own interfaces with 'ip a' and 'ip route'
  
source: https://terokarvinen.com/network-interface-linux/
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
 
Source: wikipedia: https://en.wikipedia.org/wiki/Internet_protocol_suite

<img width="922" height="554" alt="d)_updated" src="https://github.com/user-attachments/assets/30189746-1688-4371-a44e-9af66a0737ad" />

# e)

- By going to Statistics -> endpoints tab in wireshark you can see Ethernet has 2 listed and IPv4 has 7 so this would mean there was 2 physical connections and 7 IP addresses.
- The most used protocols in this capture are DNS, QUIC, TCP and TLSv1.3
- You can see in captured file properties found in the Statistics tab that the capture lasted for slightly over 7 seconds with 283 packets captured.

# g) 
# h)
<img width="1277" height="754" alt="weppipalvelin" src="https://github.com/user-attachments/assets/f9c2fee6-48b8-4e7d-989f-3600bc46e989" />
# i)
<img width="1272" height="773" alt="analysis" src="https://github.com/user-attachments/assets/58be95e1-7e72-461c-8853-38f978ce95ae" />

- This is a normal search to terokarvinen.com
- frame 1 oct 26, 2025
- frame 16 oct 26, 2025
- 331 packets captured
- Network card: PCSSystemstec
- 22sec
# Sources 

Karvinen 2025: Wireshark - getting started: https://terokarvinen.com/wireshark-getting-started/

Karvinen 2025: Network Interface Names on Linux: https://terokarvinen.com/network-interface-linux/

Wikipedia: https://en.wikipedia.org/wiki/Internet_protocol_suite

<img width="933" height="510" alt="Capture" src="https://github.com/user-attachments/assets/46daa52e-4ac3-450f-9e04-ae1660903598" />
<img width="1278" height="775" alt="Ethernet2" src="https://github.com/user-attachments/assets/cec4f91e-ae4d-4d1e-9ada-84f6ac79a666" />

<img width="842" height="736" alt="Capture_file" src="https://github.com/user-attachments/assets/c9026ad3-125a-4444-a535-7a8d611d8df8" />
