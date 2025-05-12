Nmap scan

sudo nmap -sC -sV -p- -T4 -Pn --min-rate=10000 -oN brook9.txt 10.10.86.157

When i performe the nmap scan i found three ports that are open. Ftp ssh and http for the web. 

![image](https://github.com/user-attachments/assets/90b745fa-2f27-4c8e-a495-cbfd213122d5)


Here i had access into the ftp server by using defaults credentials ftp:ftp. On the server i found this txt file note_to_jake and i downloaded it into my local machine.

![image](https://github.com/user-attachments/assets/7555f5e1-dfca-40a0-ba95-019bbd894fc1)



download the file

![image](https://github.com/user-attachments/assets/ed192fba-92bd-4dda-972b-753364921012)



Once i readed the file, i found this . I supposed there are two users on the systems maybe. Jake and Holt. 

![image](https://github.com/user-attachments/assets/f960406b-38ce-4c1b-898e-04238f7e04cd)




More enumeration i found this webpage where we had an image ; On the source code the talked about steganography, so i assumed this something hidden inside the image.

![image](https://github.com/user-attachments/assets/e4c4753c-5ff5-441a-8a4f-e0ca9b40119f)




reading the source code

![image](https://github.com/user-attachments/assets/5c066b87-09f2-41cb-baa0-255dcd3243b4)



Since the user Jake is present on the server i tried to brute the ssh credentials since they are weak.


![image](https://github.com/user-attachments/assets/3d7d34b9-6eda-4471-b597-9fd960aab6ae)


I was able to log in successfully with the creds found


![image](https://github.com/user-attachments/assets/62fd2553-4b95-47c8-907e-58047d8a00de)


I downloaded the wallpaper for further inspection. And used my steg skills to get the information out of it.


![image](https://github.com/user-attachments/assets/c807d580-cad2-47bf-89d1-54c40567b335)


When i try to open the image, it ask for a password.


![image](https://github.com/user-attachments/assets/96987877-98b0-4fa7-a9c1-79ebeb9984bf)


With stegseek i’m able to brute force the password and have access into the secrets files.


![image](https://github.com/user-attachments/assets/59954701-ce40-4860-9b6f-12229145be4b)


Inside i retrieve the pasword for holt.


![image](https://github.com/user-attachments/assets/43482ee9-10b3-4680-8b7f-6bccd1603e14)


log as holt


![image](https://github.com/user-attachments/assets/75569c4c-a432-4d7a-b0c9-19fd62c84403)



got the user flag


![image](https://github.com/user-attachments/assets/174ebc2b-f102-44e6-83bf-85101bead1d0)


For the privilege escalation we can see that the user holt may run the nano binary with sudo privileges.

I checked on gtfobins how to exploit this binary to get the root shell.



![image](https://github.com/user-attachments/assets/00a67b3b-a382-4be5-9dc9-44aa4d6e91f0)


After pwning a shell using nano, we are log as root 


![image](https://github.com/user-attachments/assets/24b02af8-a17a-4152-b057-f08900d360ce)



We have the root flag and the machine is pwn. !!!



![image](https://github.com/user-attachments/assets/d6c97ca6-52c3-46ef-a35a-765ce82c75a8)

