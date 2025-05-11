# Wireshark-Incident-Response
Research malicious activity through cybersecurity tools. In today's lab, we will access a Cyber Defender project. Our task is to analyze the provided PCAP file to uncover how it appeared and determine the extent of any unauthorized activity.
<h2>Environments and Technologies Used</h2>

- Wireshark
- Whatismyipaddress.com

<h2>List of Prerequisites</h2>
<h2>- To begin the lab, we will go to Cyberdefenders.com, create an account, and look for the Webstrike lab underneath the lab tab. Click on the link and press the green open button to begin. Make sure to allow the lab to load up before beginning your incident response.<h2>

![image](https://github.com/user-attachments/assets/d3cc0dbe-1b6a-4dab-9573-1c5fc510a720)

![image](https://github.com/user-attachments/assets/13361b9a-ad7e-4419-93d0-f2993658045c)


# Webstrike Scenario
1. With the lab-generated, follow these steps to access malicious content: go to the desktop tab > start here file > artifacts file > Wireshark pcap file that has been segmented with the malicious activity. An example of said file will be in the picture below.

![image](https://github.com/user-attachments/assets/ef853647-12d9-406c-9e7c-4f2290e99138)


2. If this is your first time within Wireshark, it may be confusing, so we will break down the necessary steps to get to the malicious content. The first challenge cyberdefenders introduced is finding where the attack originated. The following steps will help guide you. If you are curious about understanding Wireshark better for this lab, a link will be provided for a beginner's lesson on Wireshark.
   https://www.youtube.com/watch?v=OU-A2EmVrKQ

- Look at the source and destination IP addresses in the PCAP file. Only one of them should correspond to an external entity. Have you identified which IP might be malicious?
- Filter for HTTP GET requests using the filter: http.request.method == GET.
- Use a geo-IP lookup service like WhatIsMyIPAddress to determine the geographical location of the identified source IP.

![image](https://github.com/user-attachments/assets/de594829-1db5-4595-913a-1dc8b6ce08f6)
![image](https://github.com/user-attachments/assets/fd5fbdb0-faba-45dc-a795-6e6a8919fe1b)

3. Next, we wanna learn more about who is attacking? What is the attacker's Full User-Agent? To find this info, I want you to right-click on the IP Address we just identified and scroll down to the following tab, where you will find TCP stream. You'll find critical info on the TCP connection that was established, including the host and user, using the code. An example of the TCP stream will be shown below.

- Analyze the HTTP packets in the PCAP. Check the details of requests that include User-Agent information.
- Filter for HTTP GET requests using http.request.method == GET. Expand the Hypertext Transfer Protocol section in a GET packet and find the User-Agent field to view the attacker's User-Agent string.
- Your answer should be (Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0)


![image](https://github.com/user-attachments/assets/403b82bc-dd83-46e1-a4ec-582d9e84ff8c)

![image](https://github.com/user-attachments/assets/d6579564-8dc7-4a27-8630-19b6542e5e17)

