What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/161/challenge.zip)

Hints:
1. The `cat` command will let you read a file, but that won't help you here!
2. Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
3. When committing a file with git, a message can (and should) be included.


## Solución 1:
Revisando el registro(log) de Git 
```
┌──(yair㉿Yair)-[~/reto]
└─$ cd drop-in/

┌──(yair㉿Yair)-[~/reto/drop-in]
└─$ ls
message.txt

┌──(yair㉿Yair)-[~/reto/drop-in]
└─$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...
┌──(yair㉿Yair)-[~/reto/drop-in]
└─$ message.txt -h
message.txt: command not found

┌──(yair㉿Yair)-[~/reto/drop-in]
└─$ git log
commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}

```