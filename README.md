# CyberTalents-[MEDIUM] Counter write-up

Category : Digital Forensics 

Description: 

Hacker tried to hide information inside this binary file.
He is not good in remembering passwords (usually his passwords consists of 4 characters)


We were given a 64-bit ELF binary, I opened it in IDA.
Starting from the main function.. I noticed there were multiple random values being pushed to the stack


![counter](https://user-images.githubusercontent.com/80649768/183888650-766447f3-a5c3-47bb-a792-f9fe79dcc13f.png)


I searched this https://filesignatures.net/index.php?page=all for 50 4B 03 04 and I found it, we got a zip file!

I dumped the values then used this site https://tomeko.net/online_tools/hex_to_file.php to convert them.

![Screenshot_2022-08-10_07-31-05](https://user-images.githubusercontent.com/80649768/183890769-4536d4d2-f167-42ae-b193-f192be7923ef.png)

I tried to extract it but it needed a password.
I tried to crack it using the famous rockyou.txt but it failed!!
I checked the description again, he said it's a 4-character password so I created my own wordlist.

The command used to create wordlists:

crunch 1 6 abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789 -o wordlist.txt
