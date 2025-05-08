We found this [file](https://mercury.picoctf.net/static/09a86202e72dbdb5bf4d1b5d2c6a5b86/tunn3l_v1s10n). Recover the flag.

Hints:
1. Weird that it won't display right...

## Solución 1:
Modificando los magic bytes para arreglar la imagen bmp
```
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333                                0'#3
                                                          
```
Vemos que al ser creado en windows su encabezado es de 40 bits por lo cual modificamos los bits marcados como bad0 y los reemplazamos por 2800
```
00000000: 424d 8e26 2c00 0000 0000 2800 0000 2800  BM.&,.....(...(.
00000010: 0000 6e04 0000 4003 0000 0100 1800 0000  ..n...@.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333  
```
La imagen ya se ve pero no hay rastro de la flag, ahora hay que modificar la altura en el offset 0x16:
Le colocamos 40 para que sea una altura optima y encontramos la flag:
```
picoCTF{qu1t3_a_v13w_2020}
```