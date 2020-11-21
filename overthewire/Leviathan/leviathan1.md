# Leviathan 1 -> 2
Upon opening the box you can find the file `~/check`. This is an executable file that asks you for a password.

![](https://github.com/ELuculent/wargames-and-ctf/blob/master/overthewire/Leviathan/Resources/lev2-0.PNG?raw=true)

It asks for a password and you might be tempted to brute force it, but before jumping right into a `O(62^n)` solution, let's see if we can find something in the executable. After running `ltrace ./check`, we manage to find our answer staring us blankly in the face. Now we can go ahead and grab the password from the usual place.
