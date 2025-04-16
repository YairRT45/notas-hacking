The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.
`ssh -p 55790 ctf-player@mimas.picoctf.net`Use password: `6abf4a82`

Hints:
1. Where can you get some letters?

## Solución 1:
Usando WildCards, para encontrar la flag
```
SansAlpha$ *
bash: blargh: command not found

SansAlpha$ */*
bash: blargh/flag.txt: Permission denied

SansAlpha$ /*
bash: /bin: Is a directory

SansAlpha$ /*/??????
/bin/base32: extra operand '/bin/base64'
Try '/bin/base32 --help' for more information.

SansAlpha$ /*/????64 */*
/bin/base64: extra operand '/bin/x86_64'
Try '/bin/base64 --help' for more information.

SansAlpha$ /*/???[!_]64 */*
/bin/base64: extra operand 'blargh/flag.txt'
Try '/bin/base64 --help' for more information.

SansAlpha$ /*/???[!_]64 */????.*
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV84YjNkODNhZH0=


----------------------------------
CyberChef
Input: cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV84YjNkODNhZH0=
Recipe: From Base64
Output: return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_8b3d83ad}
```