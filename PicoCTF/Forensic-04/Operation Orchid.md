Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)

Hints:
1. None

## Solución:
```
┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ fls disk.flag.img -o 411648 472                    
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ icat disk.flag.img -o 411648 1782
Salted__�ށ��e��B�J▒�c�$QE&$��4jM�KGeE�1�^Ȥ7� ���؎$�'%                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ icat disk.flag.img -o 411648 1782 > posible_flag.txt

┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ icat disk.flag.img -o 411648 1875               

touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt

┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ openssl aes256 -salt -d -in posible_flag.txt -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40279DA9BD7F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ ls
disk.flag.img  flag.txt  posible_flag.txt
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/forensic/op_orchid]
└─$ cat flag.txt        
picoCTF{h4un71ng_p457_5113beab}  
```