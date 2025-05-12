Nmap scan
sudo nmap -sC -sV -p- -T4 -Pn --min-rate=10000 -oN brook9.txt 10.10.86.157
When i performe the nmap scan i found three ports that are open. Ftp ssh and http for the web. 
![image.png](attachment:63ddb2de-7c5d-40b6-96fa-7cdf6fa30b6f:image.png)

Here i had access into the ftp server by using defaults credentials ftp:ftp. On the server i found this txt file note_to_jake and i downloaded it into my local machine.

![image.png](attachment:8e397387-85df-4a35-8f41-db6a34db786a:image.png)

download the file
![image.png](attachment:14c635fc-191e-4465-95b9-9da8b06076b9:image.png)

Once i readed the file, i found this . I supposed there are two users on the systems maybe. Jake and Holt. 

![image.png](attachment:6c3ade35-0aec-47b2-b3de-95637c53328a:image.png)

More enumeration i found this webpage where we had an image ; On the source code the talked about steganography, so i assumed this something hidden inside the image.

![image.png](attachment:8ce23a1b-819a-4d34-b255-04d91cf7fbde:image.png)

reading the source code
![image.png](attachment:2f9bdc41-e3f0-4870-a136-3eedfcaed697:image.png)

Since the user Jake is present on the server i tried to brute the ssh credentials since they are weak.

![image.png](attachment:7a71a5e2-9a2a-40af-8ce5-9e8ddcfe65b6:image.png)

I was able to log in successfully with the creds found

![image.png](attachment:8a0b931e-543a-4ee6-900a-bb55b6d8f230:image.png)

I downloaded the wallpaper for further inspection. And used my steg skills to get the information out of it.

![image.png](attachment:9f2174e8-1d52-4e2d-8143-7c1cd383a748:image.png)

When i try to open the image, it ask for a password.

![image.png](attachment:62bdc8b4-8289-4de0-8c1f-aae157d880cb:image.png)

With stegseek i’m able to brute force the password and have access into the secrets files.

![image.png](attachment:9545b13e-4dae-421b-8f00-df9ce612fe68:image.png)

Inside i retrieve the pasword for holt.

![image.png](attachment:eb5c8435-8b58-4c67-8926-2c2cdf1cea74:image.png)

log as holt


![image.png](attachment:18cdfa3d-54a4-4278-b3a9-901667792c41:image.png)

got the user flag
![image.png](attachment:0269ea84-1dd0-4eaa-9d50-694aa3c837f7:image.png)

For the privilege escalation we can see that the user holt may run the nano binary with sudo privileges.

I checked on gtfobins how to exploit this binary to get the root shell.

![image.png](attachment:00f84aa2-0645-4d46-9032-e3bb5c0a77d2:image.png)

After pwning a shell using nano, we are log as root 

![image.png](attachment:7c89c1bc-9f86-4f88-a5eb-3585b87ec641:image.png)

We have the root flag and the machine is pwn. !!!

![image.png](attachment:9446adf8-88fb-42de-b4a2-dcbe93ff1b7f:image.png)

