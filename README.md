# P3rf3ct-r00t-2024
![N|Solid](https://pbs.twimg.com/media/Gca2AWAXQAAI5YV?format=jpg&name=large)
P3rf3ctr00t CTF was well organized and a fun way to learn while thinking outside the box. I enjoyed playing this CTF through my team **N3tS3c** achieving 600 points and at position 29.

This is a repository with my write-ups to the recently concluded CTF by P3rfect r00t in 2024.

**Disc:** There is always a first time for everyone, this is my first time doing a write-up, and I will improve with time.

# Misc Category
# 1. tGIF Challenge by 0st3

I found this challenge exciting, we are presented with information bits that might lead us to the flag with a format (r00t{...}).

We were presented with a file without an extension, I analyzed the file to establish the type with 
> - cmd: file tGIF. This does not identify the type of file.
> - cmd: binwalk tGIF. Still, I didn't get the file type.

Based on the names of the challenge (tGIF) and filename (tGIF), I decided to check if it is a Graphics Interchange Format (GIF) image, I renamed the file to tGIF1.gif and tried to open the file with Brave Browser. This did not result in anything tangible.

From the description of the challenge, **"TGIF, but I think I'm either rendering my file wrongly or the dimensions are just off."** I thought maybe something was OFF, so I tried to check the file signature. File signature is data used to verify file contents when the file is viewed as text. There are defined file signatures for every file extension as can be found on this website ( https://www.garykessler.net/library/file_sigs.html ). To check file signatures we can use tools such **xxd** in Linux to create a hex dump of the file e.g **cmd: xxd filename**, then after obtaining the hex values we can compare them with the known signatures.

So this is what I did:

> 1. Obtaining hex dump. cmd : hexedit tGIF1.gif | head
>    This displayed the top 10 lines of the hex values.

> 2. Comparing the obtained hex values with known file signatures. I did this manually, still learning how to automate.
>    Through comparison, I noted that the hex digits were different pushing me to find a way to correct them in my file.
>    GIF89a files have these signatures "47 49 46 38 39 61" while our file had "47 04 46 38  39 61"

> 3. Tools such as **hexedit** can be used to edit and save. e.g _**cmd: hexedit tGIF1.gif**_
>    After editing, I saved the file (CTRL+S) and exited the program (CTRL+X).

> 4. Trying again to open the file through, _**cmd: brave-browser tGIF1.gif**_ I was glad to see the flag.

Do you want the flag? Have it then,  **r00t{d38252762d3d4fd229faae637fd13f4e}**



# Stego Category

Steganography (Stego) is the art of concealing information inside some other information. The most common form is text hidden inside images. There are many ways of hiding this information including editing the Least Significant Bits (LSB) of a file.

# 2. Mayday Mayday by w1ll13

We are presented with a file (**007.wav**) and some text (**Incoming messsage from james bond**). Our task is to find the flag with this format (r00t{...}).

**Step 1: Analyze the file.**

> Use common tools:

> _**cmd: file 007.wav**_ This identifies the file as a wave audio

>_**cmd: binwalk 007.wav**_ This shows that no data is embedded in the file.
                    
>_**cmd: hexedit 007.wav | head**_ This shows the file signature, comparing them with known file signatures proves it is a WAV file.
                    
_**Step 2: Exploring the file.**_                
> Listening to the wave file: _**cmd vlc 007.wav**_ Out of nowhere, I thought that this was a Morse code, the next step would be to find a Morse code decoder. Thanks to  
 Google I got two sites, the first didn't work but the second gave the right flag (https://morsecodemagic.com/morse-code-audio-decoder).

_**Step 3: Getting the flag through decoding.**_
> Decoding using the above-mentioned site gave information that seemed interesting considering the description of the challenge.

So, here is your flag **r00t{J@M35_007_B0ND_2OO9}**

Congrats, I hope you are looking to explore stego further, resource (https://0xrick.github.io/lists/stego)



# 3




