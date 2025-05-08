Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg)

Hints:
1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución 1:
```
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka]
└─$ ls
dolls.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka]
└─$ unzip dolls.jpg         
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka]
└─$ ls
base_images  dolls.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka]
└─$ cd base_images 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka/base_images]
└─$ ls
2_c.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka/base_images]
└─$ unzip 2_c.jpg  
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka/base_images]
└─$ ls
2_c.jpg  base_images
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/Matryoshka/base_images]
└─$ cd base_images 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/forensic/Matryoshka/base_images/base_images]
└─$ ls
3_c.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/forensic/Matryoshka/base_images/base_images]
└─$ unzip 3_c.jpg 
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/forensic/Matryoshka/base_images/base_images]
└─$ ls
3_c.jpg  base_images
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/forensic/Matryoshka/base_images/base_images]
└─$ cd base_images 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ ls
4_c.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ unzip 4_c.jpg 
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ ls
4_c.jpg  flag.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ cat flag.txt            
picoCTF{96fac089316e094d41ea046900197662}   
```