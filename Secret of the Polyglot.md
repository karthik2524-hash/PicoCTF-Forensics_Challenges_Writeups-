#### Description

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).

Yoo solved this chall , u want to know  how  below are the steps 


![[Pasted image 20251126004525.png]]

![[Pasted image 20251126004750.png]]

i can see some text int the pdf  1n_pn9_&_pdf_2a6a1ea8} definitely it is a part of flag now let us look after the other half 

Do u know what's the basic thing we need to do mainly for forensics chall ? 
it is checking with exiftool for the metadata of that particular file so let us do it 

![[Pasted image 20251126005221.png]]

damm it is quit useful now all  dots seems to be connected , it is a fucking png file , let us try displaying it

![[Pasted image 20251126005439.png]]

yoo here is the first half let us combine both 

Final Flag : picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8} 