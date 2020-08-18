# Collision

I will not be posting the flags I've found.

> Daddy told me about cool MD5 hash collision today.
> I wanna do something like that too!

# First Steps
List directory, find the source code. Normal stuff. Upon seeing the source, I noticed the hashcode to compare to. The passcode had to be 20 bytes. The `check_password` function appears to add the 20 byte password up.

Using the MD5 hash collision hint from the start, I could take the hexadecimal number from the hashcode and create a 20 byte password using hexadecimal. By dividing `0x21DD09EC` by 5, I was able to get a value of `0x6C5CEC8`, which I could multiply by 4 and get `0x1B173B20`, which was `0x6C5CECC` less than the target value. I converted these to small endians.
    I had issues with it being the wrong password even with the collision input via:
```bash
$ ./col $(python2 -c 'print "\xC8\xCE\xC5\x6C" * 4 + "\xCC\xCE\xC5\x6C"')
```
Zero points for guessing the problem :)

I remade the hexadecimal strings with different values, made sure they worked like they should and ended up with 
```bash
$ ./col $(python2 -c 'print "\x90\xCE\xC5\x06" * 4 + "\xAC\xCF\xC5\x06"')
```
which gave me the flag.