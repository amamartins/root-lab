## Can I exploit all open ports? ##

Here are all identified open ports: 

<img width="1914" height="763" alt="identifying configs" src="https://github.com/user-attachments/assets/333989bc-a33d-466e-ac6c-557c9ea10e00" />

Level 1: FTP

<img width="911" height="211" alt="FOUND FTP VULN" src="https://github.com/user-attachments/assets/79e2c67a-208b-4a0b-9d02-c9ae954d59c3" />

Here is the vulnerability with FTP. It is running an older version, creating vulnerabilties for me to exploit.

Metasploit created a backdoor and with a few commands, I was able to find all files.

<img width="935" height="833" alt="entered the server, now in the files" src="https://github.com/user-attachments/assets/9dbd31d3-75b7-4f25-a73e-99cb98fe4dae" />

Level 2: SSH

The next open port was SSH. This appears to be hard to crack as SSH is encrypted. Luckily, Metasploit Framework shows us how to crack it through brute force. 

<img width="1075" height="848" alt="how to brute force" src="https://github.com/user-attachments/assets/95c02ccf-586b-4d0f-9a47-bc7b7384569f" />

Setting all the parameters for the brute force
<img width="712" height="270" alt="revving engines for brute force" src="https://github.com/user-attachments/assets/33825971-4936-4410-8f79-ec25b03cb005" />

Level 3: Telnet

Attempting to login into Telnet

<img width="887" height="444" alt="TELNET LOGIN COMPLETE" src="https://github.com/user-attachments/assets/6443d381-2da3-499e-af45-bb394b35b453" />

Success! Now, let's telnet into metasploitable:

<img width="855" height="581" alt="Screenshot 2026-09-16 151635" src="https://github.com/user-attachments/assets/91247043-c18b-4abc-b0b6-50f07e4a57c4" />

Now, using Wireshark, we can analyze the traffic going through and follow TCP stream to find any unencrypted traffic. I found the username and password. 

<img width="1778" height="797" alt="Screenshot 2026-09-16 152231" src="https://github.com/user-attachments/assets/4612c3c1-5d49-4ba7-bdcf-758a94be5e39" />

Level 4: SMTP

After setting RHOSTS and clicking run, we found the users

<img width="942" height="205" alt="users found" src="https://github.com/user-attachments/assets/8af9bdf1-1423-465c-b18e-93d0acf51837" />

Level 5: HTTP

Switching over to the auxiliary for HTTP

<img width="942" height="525" alt="Screenshot 2026-09-16 154914" src="https://github.com/user-attachments/assets/e1a6458e-a4ea-4387-a3a4-ddad790a5b24" />

Finding vulnerabilities with HTTP

<img width="943" height="204" alt="Screenshot 2026-09-16 160705" src="https://github.com/user-attachments/assets/8d4201e9-88c9-435f-b76f-08f428988d62" />


Trying to find the best exploit to use

<img width="948" height="291" alt="which exploit to use http" src="https://github.com/user-attachments/assets/5496d7c2-2114-4a07-8f2e-e90d169aa1b3" />

Didn't work

<img width="943" height="774" alt="Screenshot 2026-09-16 162324" src="https://github.com/user-attachments/assets/d23f6cf5-0b3e-4c9b-91b9-473c6085683f" />

Found a new one

<img width="942" height="378" alt="Screenshot 2026-09-16 162635" src="https://github.com/user-attachments/assets/ee7beee1-88c9-41a8-a1c3-d35deb8130d5" />

<img width="942" height="378" alt="Screenshot 2026-09-16 162635" src="https://github.com/user-attachments/assets/3d0c2f97-a13f-4518-b59a-93a5b2870ac6" />

Success!





