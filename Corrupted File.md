
#### Description

This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life? Download the file [here](https://challenge-files.picoctf.net/c_amiable_citadel/c5e80ada9fe1374e6a70dc17a4d53a2da7216b6daf618429ccf73c1fa9417a5d/file).

![[Pasted image 20251124103849.png]]

the file shows \x��JFIF��C  JFIF which is actually a JPEG hence the challenge itself says the file is corrupted so it is a JPEG/JFIF corrupted file 

let us check with the hex format of JPEG/JFIF 

![[Pasted image 20251124104136.png]]

Here we can see the file hexadecimal starts with FF D8 FF so let us check with the hex 

![[Pasted image 20251124104245.png]]

Yup here it is it starts with something different than what we expected 
Two ways to solve this chall we have to correct the file by Terminal and GUI hex editor 

Terminal Based 
       we can correct the file with this command 
       (printf '\xff\xd8' && tail -c +3 file) > repair.jpg
1. `**printf '\xff\xd8'**`: Prints the JPEG start bytes `FF D8` to the screen
2. `**&&**`: Executes the second command if the first command is successful
3. `**tail -c +3 file**`: Skips the first 2 bytes of the original file and displays all content starting from the 3rd byte
4. `**> repair.jpg**`: Combines the outputs of both commands and saves them to the `repair.jpg` file 

![[Pasted image 20251124105308.png]]

GUI based Online hex editor 

![[Pasted image 20251124105829.png]]

![[Pasted image 20251124105845.png]]


Final Flag : picoCTF{r3st0r1ng_th3_by73s_684e09bc}




