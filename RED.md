
#### Description

RED, RED, RED, RED Download the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

Trying with the strings is no use let us see what actually it is Hiding 
![[Pasted image 20251124140208.png]]

 Let us use a tool which is for stegnography using zsteg tool 

![[Pasted image 20251124140808.png]]

let us try with zsteg -a red.png 


![[Pasted image 20251124141208.png]]

we got this string cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==

let us decode the string maybe it is a base64 encoded 

![[Pasted image 20251124141101.png]]

Final Flag : picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}










