The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf).

Hints:
1. This problem can be solved by just opening the file in different ways

## Solución 1:
Usamos foremost para encontrar otra imagen con la primera parte de la flag:
```
┌──(kali㉿kali)-[~/Documents/forensic/polyglot]
└─$ foremost flag2of2-final.pdf                 
Processing: flag2of2-final.pdf
|*|
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/forensic/polyglot]
└─$ ls
flag2of2-final.pdf  output
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/forensic/polyglot]
└─$ cd output  
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/forensic/polyglot/output]
└─$ ls
audit.txt  png
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/forensic/polyglot/output]
└─$ cd png     
                                                                                                                   
┌──(kali㉿kali)-[~/…/forensic/polyglot/output/png]
└─$ ls
00000000.png
                                                                                                                   
┌──(kali㉿kali)-[~/…/forensic/polyglot/output/png]
└─$ open 00000000.png  

picoCTF{f1u3n7_}


```
La segunda parte esta escrita en el pdf, solo es necesario abrirlo:
```
1n_pn9_&_pdf_53b741d6}

flag:picoCTF{f1u3n7_1n_pn9_&_pdf_53b741d6}
```