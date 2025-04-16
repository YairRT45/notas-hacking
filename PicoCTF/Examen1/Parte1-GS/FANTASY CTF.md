Play this short game to get familiar with terminal applications and some of the most important rules in scope for picoCTF.Connect to the program with netcat:`$ nc verbal-sleep.picoctf.net 57327`

Hints:
1. When a choice is presented like [a/b/c], choose one, for example: `c` and then press Enter.

## Solución 1:
Si iniciamos la conexión por medio de netcat con:
```
$ nc verbal-sleep.picoctf.net 57327
---------------------------------
Después de responder:
Nyx brings up the registration page.

Options:
A) *Register multiple accounts*
B) *Share an account with a friend*
C) *Register a single, private account*
[a/b/c] > c

Nyx nods, "Good choice, Ei. Let's proceed with a single, private account. It
can be tempting to try and do something 'clever', but registering multiple
accounts or sharing an account with a friend can lead to disqualification."
--------------------------------------------
Y:
Options:
A) *Play the game*
B) *Search the Ether for the flag*
[a/b] > a

"Good choice, Ei," Nyx says, "You never want to share flags or artifact
downloads."
-----------------------------------------------
Después de un par de iteraciones después obtenemos la flag:
"Thanks, Nyx! Here's the flag I found: picoCTF{m1113n1um_3d1710n_5e40d7b5}"


picoCTF{m1113n1um_3d1710n_5e40d7b5}
```