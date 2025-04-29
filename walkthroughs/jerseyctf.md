The challenge provided an image file that contained hidden data. Here's a detailed breakdown of the solution:
![image.png](attachment:2e527d8b-9d16-4b1a-88b6-2af69683eded:image.png)

Tool Used: Stegseek - A powerful steganography tool designed to crack steghide encrypted files
2. Process:
    - No password was required for extraction
    - Command used: `stegseek noir.jpg`
    - Output file: noir.jpg.out
    Flag was directly readable in the extracted file
    ![image](https://github.com/user-attachments/assets/6e243b66-a7a0-4d0d-8151-b26b06df326c)
   
     **Sound Secure Write-up**

This challenge involved analyzing an MP3 file. Here's the systematic approach taken:

1. Initial Analysis:
    - Listened to the audio file - no obvious clues
    - Attempted binwalk to check for embedded files - no results
2. Solution Method:
    - Used the `strings ` command to examine readable text within the file
    - Command used: `strings sounds_secure.mp3 | less`
    - Flag was found in the output
    - 
![image](https://github.com/user-attachments/assets/a1014393-4e9d-4207-9bb3-c7ef644deb8d)

Frequency-Deception Write-up
