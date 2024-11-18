# P3rf3ct-r00t-2024
![N|Solid](https://pbs.twimg.com/media/Gca2AWAXQAAI5YV?format=jpg&name=large)
P3rf3ctr00t CTF was well organized and a fun way to learn while thinking outside the box. I enjoyed playing this CTF through my team **N3tS3c** achieving 600 points and at position 29.

This is a repository with my write-ups to the recently concluded CTF by P3rfect r00t in 2024.

**Disc:** There is always a first time for everyone, this is my first time doing a write-up, and I will improve with time.

# Misc Category
# 1. tGIF Challenge Write-up

I found this challenge exciting, we are presented with information bits that might lead us to the flag with a format (r00t{...}).

We were presented with a file without an extension, I analyzed the file to establish the type with 
> - cmd: file tGIF. This does not identify the type of file.
> - cmd: binwalk tGIF. Still, I didn't get the file type.

Based on the names of the challenge (tGIF) and filename (tGIF), I decided to check if it is a Graphics Interchange Format (GIF) image, I renamed the file to tGIF1.gif and tried to open the file with Brave Browser. This did not result in anything tangible.

From the description of the challenge, **"TGIF, but I think I'm either rendering my file wrongly or the dimensions are just off."** I thought maybe something was OFF, so I tried to check the file signature. File signature is data used to verify file contents when the file is viewed as text. There are defined file signatures for every file extension as can be found on this website ( https://www.garykessler.net/library/file_sigs.html ). To check file signatures we can use tools such **xxd** in Linux to create a hex dump of the file e.g **cmd: xxd filename**, then after obtaining the hex values we can compare them with the known signatures.

So this is what I did:

> 1. Obtaining hex dump. cmd : hexedit tGIF1.gif | head
>    This displayed the top 10 lines of the hex values.

> 3. Comparing the obtained hex values with known file signatures. I did this manually, still learning how to automate.
>    Through comparison, I noted that the hex digits were different pushing me to find a way to correct them in my file.
>    GIF89a files have these signatures "47 49 46 38 39 61" while our file had "47 04 46 38  39 61"

> 5. Tools such as **hexedit** can be used to edit and save. e.g _**cmd: hexedit tGIF1.gif**_
>    After editing, I saved the file (CTRL+S) and exited the program (CTRL+X).

> 7. Trying again to open the file through, _**cmd: brave-browser tGIF1.gif**_ I was glad to see the flag.

You want the flag? Have it then,  **r00t{d38252762d3d4fd229faae637fd13f4e}**

# 2. 


