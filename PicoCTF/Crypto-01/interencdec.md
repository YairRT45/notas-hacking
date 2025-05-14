Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/2/enc_flag).

Hints:
1. Engaging in various decoding processes is of utmost importance

## Solución 
Decodificamos 2 veces en base 64, vemos que queda otra cadena:
```
┌──(kali㉿kali)-[~/Documents/crypto/interenc]
└─$ cat enc_flag                                       
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg==
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/crypto/interenc]
└─$ cat enc_flag | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ=='
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/crypto/interenc]
└─$ echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ== | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_78250hmj} 
```
Esta cadena la desciframos con CyberChef, es un cifrado Cesar:
```
Input: wpjvJAM{jhlzhy_k3jy9wa3k_78250hmj}
Recipe: ROT13 [Amount: 19]
Output: picoCTF{caesar_d3cr9pt3d_78250afc} 
```