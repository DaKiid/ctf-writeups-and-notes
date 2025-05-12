Nmap scan

sudo nmap -sC -sV -p- -T4 -Pn --min-rate=10000 -oN brook9.txt 10.10.86.157

When i performe the nmap scan i found three ports that are open. Ftp ssh and http for the web. 

![image](https://github.com/user-attachments/assets/90b745fa-2f27-4c8e-a495-cbfd213122d5)


Here i had access into the ftp server by using defaults credentials ftp:ftp. On the server i found this txt file note_to_jake and i downloaded it into my local machine.



download the file


Once i readed the file, i found this . I supposed there are two users on the systems maybe. Jake and Holt. 



More enumeration i found this webpage where we had an image ; On the source code the talked about steganography, so i assumed this something hidden inside the image.



reading the source code



Since the user Jake is present on the server i tried to brute the ssh credentials since they are weak.



I was able to log in successfully with the creds found



I downloaded the wallpaper for further inspection. And used my steg skills to get the information out of it.



When i try to open the image, it ask for a password.



With stegseek i’m able to brute force the password and have access into the secrets files.



Inside i retrieve the pasword for holt.



log as holt




got the user flag



For the privilege escalation we can see that the user holt may run the nano binary with sudo privileges.

I checked on gtfobins how to exploit this binary to get the root shell.




After pwning a shell using nano, we are log as root 




We have the root flag and the machine is pwn. !!!



