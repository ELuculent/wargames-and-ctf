# Pwnable.kr - fd (File Descriptor)

I will not be posting the flags I've found

> Mommy! what is a file descriptor in Linux?
>
> * try to play the wargame your self but if you are ABSOLUTE beginner, follow this tutorial link: https://youtu.be/971eZhMHQQw
> ssh fd@pwnable.kr -p2222 (pw:guest)

## First steps
After logging into the shell I did what I normally do in Linux. `ls -la` to show all files, their permissions, and their owners.

![Showing all files](https://github.com/ELuculent/wargames-and-ctf/blob/master/pwnable.kr/Resources/fd.1.png?raw=true)

I saw that there was a file called "fd" and tried executing. The first time it asked me for a number so I gave it one. It said to learn about Linux File I/O. 

![Trying to execute fd executable](https://github.com/ELuculent/wargames-and-ctf/blob/master/pwnable.kr/Resources/fd.2.png?raw=true)

## Getting to the flag
I used `nano` to view the "fd.c" file and found the functions for reading, error handling, and success conditions. I actually thought way too hard about this and tried to convert the success string "LETMEWIN\n" to an int and add 0x1234 to it, then convert back to a string. Obviously, that's not correct.

![C Code to figure out](https://github.com/ELuculent/wargames-and-ctf/blob/master/pwnable.kr/Resources/fd.3.png?raw=true)

I was able to figure out how to get a 0 file descriptor based on looking at the code and managed to input the right number to send "LETMEWIN\n" to the console, giving me the flag.

![Flag found (omitted from the screenshot)](https://github.com/ELuculent/wargames-and-ctf/blob/master/pwnable.kr/Resources/fd.4.png?raw=true)
