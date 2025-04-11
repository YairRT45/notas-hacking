We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Hints:
1. Try fixing the file header

## Solución 1:
Revisamos el archivo mediante el comando file, el cual nos dice que es data nada mas, corregimos los magiy bytes y ahora si es considerado un PNG
```
00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 49 48 44 52  .PNG........IHDR
```
El archivo aun no se puede abrir, revisamos con le herramienta pngcheck para verificar, cambiamos la resolución y ahora la imagen es cuadrada
```
00000040: 00 09 70 48 59 73 00 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
```
Volvemos a revisar y nos dice que un chunk es invalido, lo modificamos y después abrimos la imagen:
```
00000050: 52 24 f0 00 00 ff a5 49 44 41 54 78 5e ec bd 3f  R$.....IDATx^..?
```
Transcribimos la flag y listo:
`picoCTF{c0rrupt10n_1847995}`