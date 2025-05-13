Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/260/flag.png).

Hints:
1. None

## Solución:
```
┌──(kali㉿kali)-[~/Documents/forensic/hideme]
└─$ foremost flag.png
Processing: flag.png
|foundat=secret/UT
foundat=secret/flag.pngUT
*|

┌──(kali㉿kali)-[~/Documents/forensic/hideme]
└─$ ls
flag.png  output
                                                                                                                                     
┌──(kali㉿kali)-[~/Documents/forensic/hideme]
└─$ cd output 
                                                                                                                                     
┌──(kali㉿kali)-[~/Documents/forensic/hideme/output]
└─$ ls
audit.txt  png  zip

┌──(kali㉿kali)-[~/Documents/forensic/hideme/output]
└─$ cd zip       
                                                                                                                                     
┌──(kali㉿kali)-[~/…/forensic/hideme/output/zip]
└─$ ls
00000077.zip
                                                                                                                                     
┌──(kali㉿kali)-[~/…/forensic/hideme/output/zip]
└─$ unzip 00000077.zip           
Archive:  00000077.zip
   creating: secret/
  inflating: secret/flag.png         
                                                                                                                                     
┌──(kali㉿kali)-[~/…/forensic/hideme/output/zip]
└─$ cd secret 
                                                                                                                                     
┌──(kali㉿kali)-[~/…/hideme/output/zip/secret]
└─$ ls
flag.png

┌──(kali㉿kali)-[~/…/hideme/output/zip/secret]
└─$ open flag.png 

La flag esta en la imagen resultante:
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_ad9f6587}
```