
#### Description

Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered. Find the PDF file here [Hidden Confidential Document](https://challenge-files.picoctf.net/c_amiable_citadel/a8aa03694837741eed59c479749fc7f5bfd14fa66f4295b83776f16b2003a67d/confidential.pdf) and uncover the flag within the metadata.

First thing for any chall is to  Download the file by the wget command , i bet u without this u cannot solve the chall HEHEHEHE 


wget https://challenge-files.picoctf.net/c_amiable_citadel/a8aa03694837741eed59c479749fc7f5bfd14fa66f4295b83776f16b2003a67d/confidential.pdf

while checking the strings for the file since the description says for checking metadata we can see a possible base64 encoded string hahaha 

![[Pasted image 20251123230146.png]]


![[Pasted image 20251123230203.png]]


we can see the Flag it is base64 encoded hehe that was soo simple 

Final Flag : picoCTF{puzzl3d_m3tadata_f0und!_c2073669}


