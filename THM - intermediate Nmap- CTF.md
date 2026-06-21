**Write-up**
Room: https://tryhackme.com/room/intermediatenmap
Self-Reflection:
 This was my first CTF challenge and it was fairly simple and and a good way to learn active reconnaissance. I would highly recommend this for cybersecurity beginners who want to get into Nmap and CTF challenges.
 
  First, I used the command **nmap -sV 10.67.188.82** to find open ports, services, and service version on the server. The command then exposed three open ports with the most noticeable being high port **31337**. Then, I used command **netstat 10.67.188.82 31337** to see the contents of that port. The contents revealed a username and password that I later used to SSH into the system. Once I was remotely connected I browser the user directory and found the flag file. 
  
  
  It taught me to look for high ports and how to utilize netcat (nc) see the contents of services. 



First, I started by doing a scan to find open ports, services, and service version with command: 
![[Pasted image 20260621175310.png]]  


I found that port 22 and 31337, another high port/unknown port was open. 

Based on the room instructions I could already tell that this challenge would involve remoting into the server using SHH, but seeing port 22 open solidified that idea. 

From the instructions I could already tell that the next step involved using netstat with the high port and ran command:

![[Pasted image 20260621180754.png]]

Within the contents of the IP and port a username and password were revealed. 

Then I used SHH to successfully remote into the server using those credentials: 

![[Pasted image 20260621181951.png]]

Afterwards, all i needed to do was find the flag within the users files. I did this by running a couple of simple commands like pwd, cd, ls, and cat. 
![[Pasted image 20260621182606.png]]


Overall, this challenge was easy but great practice for those getting used to Nmap and Linux. 