
#### Description

You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag. Download the jpg image [here](https://challenge-files.picoctf.net/c_amiable_citadel/0e679342e0fe04fa2efa860dda0923cba52108031ac4e1ab519df850c2764b5c/img.jpg).


Downloading the file and start solving the challenge 
since it is metadata again for this let us check with strings 

![[Pasted image 20251123232309.png]]

hence it is gibrish let us take one more move and check with exiftool 

![[Pasted image 20251123232355.png]]

we can see now the points are connecting just see the comment omg : it looks like base64 c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9

![[Pasted image 20251123232527.png]]

decoding it shows this steghide:cEF6endvcmQ=, damm again encoded so why to think let us decode again and yeah remember it says steghide 


![[Pasted image 20251123232646.png]]


we got something might be helpful later , let us recall we got something like steghide in prev decoding use that now

![[Pasted image 20251123232818.png]]


spooky good tool for this chall 

let us check with the --info 

![[Pasted image 20251123232913.png]]

it asks for passphrase , so let us use the decoded string we got pAzzword 

![[Pasted image 20251123233045.png]]

i gave the pAzzword and can see a embedded file "flag.txt" let us extract the file 
whith "steghide extract -sf img.jpg -p pAzzword" command and printing flag.txt 

![[Pasted image 20251123233248.png]]

Final Flag : picoCTF{h1dd3n_1n_1m4g3_54e31417}