**Write-up**
Room: https://tryhackme.com/room/intermediatenmap


-Self-Reflection:
 This was my first CTF challenge and it was fairly simple and and a good way to learn active reconnaissance. I would highly recommend this for cybersecurity beginners who want to get into Nmap and CTF challenges.
 
  First, I used the command **nmap -sV 10.67.188.82** to find open ports, services, and service version on the server. The command then exposed three open ports with the most noticeable being high port **31337**. Then, I used command **netstat 10.67.188.82 31337** to see the contents of that port. The contents revealed a username and password that I later used to SSH into the system. Once I was remotely connected I browsed the user directory and found sucessfully found the flag file.-
  
 


First, I started by doing a scan to find open ports, services, and service version with command: 
<img width="705" height="191" alt="Pasted image 20260621175310" src="https://github.com/user-attachments/assets/068d317f-c3b9-45cf-a054-f12d9de65d13" />



I found that port 22 and 31337, another high port/unknown port was open. 


Based on the room instructions I could already tell that this challenge would involve remoting into the server using SHH, but seeing port 22 open solidified that idea. 

From the instructions I could already tell that the next step involved using netstat with the high port and ran command:

<img width="271" height="87" alt="Pasted image 20260621180754" src="https://github.com/user-attachments/assets/9ead55e9-26b3-476b-953a-18f06ced87b9" />


Within the port the contents of the IP and port a username and password were revealed. 

Then, I used SHH to successfully remote into the server using those credentials: 

<img width="592" height="389" alt="Pasted image 20260621181951" src="https://github.com/user-attachments/assets/e3081044-2c3d-4ef9-96b4-b2d506bac1a8" />


Afterwards, all i needed to do was find the flag within the users files. I did this by running a couple of simple commands like pwd, cd, ls, and cat. 
<img width="724" height="366" alt="Pasted image 20260621182606" src="https://github.com/user-attachments/assets/20d7f908-7007-4c43-8c95-3433dc18c839" />



Overall, this challenge was easy but great practice for those getting used to Nmap and Linux. 
