
#### Description

The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: [Logs Data](https://challenge-files.picoctf.net/c_amiable_citadel/34c1721086e2555cb8df9a09fcad35cfc09a2844bbc990dd022efca838b4e6ea/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .

SO yes let us begin

viewing the downloaded logs Data is not useful

![[Pasted image 20251123235824.png]]

it seems like something encoded file let us give it to base64 decoder , yes the entire file 

![[Pasted image 20251123235927.png]]

we got the below image with some string 
![[Pasted image 20251124000011.png]]

copying the string using google lens and checking for hex decoder we got the flag 

![[Pasted image 20251124000201.png]]


Final Flag : picoCTF{forensics_analysis_is_amazing_ac1e3584}
