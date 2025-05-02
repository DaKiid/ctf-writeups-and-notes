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
![image.png](attachment:4bf0e53b-321c-4b56-ac5b-7cd8fa07d567:image.png)
This was an audio forensics challenge involving DTMF (Dual-Tone Multi-Frequency) tones. Here's the detailed solution:

![image](https://github.com/user-attachments/assets/e4d2d04b-19bb-4857-8a34-14c0cc93fd02)
1. Initial Analysis:
    - Challenge hint mentioned "telephone digits being entered"
    - Identified the sounds as DTMF tones (the sounds made when pressing phone keypad buttons)
    - I extracted the DMTF Tones of the audio file using this ressources

![image](https://github.com/user-attachments/assets/690fd443-a460-415b-9ec1-7e39a7141c78)

Identified the encryption as ASCII text

![image](https://github.com/user-attachments/assets/3d262148-af24-4686-88ec-481ef3af2c38)

Converted ASCII to binary

![image](https://github.com/user-attachments/assets/e04e39f5-5a3a-4f61-a904-003d6e32334f)

Used CyberChef to convert binary to text

![image](https://github.com/user-attachments/assets/45721504-341b-4a02-b9bd-663bf26ef6ee)

- Retrieved the flag from the final text output

Tools Used:

- Stegseek for steganography
- Binwalk for file analysis
- Strings command for text extraction
- Online DTMF decoder
- CyberChef for binary conversion

This CTF challenge series demonstrated various techniques in steganography, audio forensics, and encoding/decoding methods commonly used in cybersecurity.



