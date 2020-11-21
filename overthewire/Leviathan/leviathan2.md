# Leviathan 2 -> 3
In this level it you are given a file called `printfile`. First thought would be to grab the file from the regular place. That's not going to work. Way too easy. 

We can create a file and see if we can use it as an argument.

![Normal File]()

It prints as expected but let's test with a spaced file name.

![Spaced File]()

It doesn't print as expected. It attempts to print both files straight to the console, not the spaced file. We can create a symbolic link and cat out the password; and that's the end of this game.
