# [MEDIUM] Counter write-up
Discription: Hacker tried to hide information inside this binary file.

He is not good in remembering passwords (usually his passwords consists of 4 characters)


We were given a 64-bit ELF binary, I opened it in IDA.
Starting from the main function.. I noticed there were multiple random values being pushed to the stack


![counter](https://user-images.githubusercontent.com/80649768/183888650-766447f3-a5c3-47bb-a792-f9fe79dcc13f.png)


I searched this https://filesignatures.net/index.php?page=all for 50 4B 03 04 and I found it, we got a zip file!
