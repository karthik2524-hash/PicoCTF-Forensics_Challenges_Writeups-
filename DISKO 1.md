
#### Description

Can you find the flag in this disk image? Download the disk image [here](https://artifacts.picoctf.net/c/536/disko-1.dd.gz).

we need to decompress this file with using gunzip disko-1.dd.gz command 

![[Pasted image 20251124134802.png]]

then we can just search for strings for the flag 

![[Pasted image 20251124134924.png]]

we can see it is a lot of info , why late let us search for flag with grep command 

strings disko-1.dd | grep pico 

![[Pasted image 20251124135040.png]]

Final Flag : picoCTF{1t5_ju5t_4_5tr1n9_c63b02ef}

