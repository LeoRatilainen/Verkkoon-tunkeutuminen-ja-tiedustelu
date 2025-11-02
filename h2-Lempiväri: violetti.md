# X)
## Pyramid of pain
 - The idea of the pyramid of pain is to illustrate how much pain it will cause to an attacker when you are able to deny certain indicators to them.
In the picture given the toughest one is TTPs meaning it would cause a lot of pain if you are able to deny access to those.
### source: https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html
## Diamond model
 - The purpose of the diamond model is to identify attackers and understand the tactics, threats and procedures they used. The diamond has four points adversary, infrastructure, capability and victim and various lines to indicate how they connect to each other in an attack scenario
### source: https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf
### source: https://www.eccouncil.org/cybersecurity-exchange/ethical-hacking/diamond-model-intrusion-analysis/
# a) Apache log.
- I downloaded apache2 with 'sudo apt-get install apache2' then started it with 'sudo systemctl start apache2'.
- After this i opened my web browser and went to 'http://localhost' and this web page opened.

<img width="1277" height="772" alt="Apache2_works" src="https://github.com/user-attachments/assets/19934469-f395-4090-9ffc-4a2d2fb6c18c" />

#### breaking down this line from the log 
 - 127.0.0.1 - Client ip address in this case it's localhost.
 - [02/Nov/2025:16:43:57 +0200] - time of the request and timezone.
 - "GET /favicon.ico HTTP/1.1" - HTTP method, request resource and protocol version.
 - 404 - not found server didn't find /favicon.ico
 - 487 - size of the reponse in bytes
 - "Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0" - User agent or the client software in this case the request came from a firefox or a firefox-like browser on a linux machine
<img width="1560" height="62" alt="Screenshot 2025-11-02 183750" src="https://github.com/user-attachments/assets/f303a3b2-4f82-4eee-84d3-bf57682e22e6" />

# b) Nmapped.
Analyzing this return we can summerize that
 - port 80/tcp is open.
 - tcp is the protocol used.
 - service running on the port is http meaning a web server
 - and we can confirm that the web server is Apache/2.4.65 running on debian
<img width="686" height="52" alt="Port80" src="https://github.com/user-attachments/assets/bbd1d663-113a-4916-b641-c9f5e0a01d8b" />

# c) Skriptit.

- From here we can summerize that OS and service detections were performed.

<img width="1074" height="175" alt="A-script" src="https://github.com/user-attachments/assets/7560d7a5-af40-482e-b8e2-d1632e8765ab" />

# d) Jäljet logissa. 

 - This is an apache2 log after a 'sudo nmap -A localhost' scan we can see a nmap here in the context of a url this seems to be pointing to the Nmap sctripting engine page.

<img width="1260" height="374" alt="jäljet-logissa" src="https://github.com/user-attachments/assets/e58b4408-c55e-4b10-95b5-7fbdfa896832" />

# e) Wire sharking.

- This is a wireshark capture done during a normal 'sudo nmap -A localhost' scan and as we can see using the 'frame contains "nmap"' filter there's quite a lot of lines that contain nmap they are mostly in the hypertext transfer protocol section.
- Seem to be pointing to the same nmap scripting engine URl page.
 
<img width="1275" height="681" alt="nmap_kohdat" src="https://github.com/user-attachments/assets/156c985e-d07e-4394-90fd-31bd5aff1505" />

# f) Net grep
- Here i downloaded ngrep with 'sudo apt-get install ngrep -y'
- Then started to watch all the traffic that had nmap in it with 'sudo ngrep -d lo -i nmap'
- I then opened another terminal and did a normal 'sudo nmap -A localhost' command and here is a snipet of the ngrep capture i got as it was quite large 
<img width="1259" height="720" alt="ngrep-scan" src="https://github.com/user-attachments/assets/adf05b28-99cd-46b7-a95c-cb1afe67d9c2" />

# g) Agentti
So after a lot of hours trying to figure out what this means and how to do it i was unable to get it done and such couldn't do the rest of the assignements but i wanted to mention a few commands to get it work 
  - 'sudo nmap -p 80 --script http-title --script-args'
  - 'sudo nmap -A -script-args'
  - 'sudo nmap -p 80 --script http-methods,http-server-header --script-args'
  - I also went to https://ifconfig.me/ua tried the command on the nmap section of this blog post: https://mrtalagoz.medium.com/change-your-user-agent-in-web-pentests-bug-bounties-dont-be-a-plain-jane-98b442a0c601

Maybe at somepoint i did it correctly and didn't realize it, but i would love to learn how this is done since from my research this sounds like a very good tool to know.
# Sources 
Karvinen 2025. https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/

Bianco 2013: Pyramid of pain: https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html

Caltagirone et al 2013: Diamond Model: https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf

EC-Council 2023: Diamond Model of Intrusion Analysis: What, Why, and How to Learn: https://www.eccouncil.org/cybersecurity-exchange/ethical-hacking/diamond-model-intrusion-analysis/

Medium 2023: Change your User Agent in web pentests and bug bounties: Don’t Be a Plain Tester!: https://mrtalagoz.medium.com/change-your-user-agent-in-web-pentests-bug-bounties-dont-be-a-plain-jane-98b442a0c601
