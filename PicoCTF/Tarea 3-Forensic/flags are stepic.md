A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message
Try it [here](http://standard-pizzas.picoctf.net:62440/)!

Hints:
1. In the country that doesn't exist, the flag persists

## Solución:
Observamos que entre todas las banderas, solo una no lo es, buscamos la ruta de la imagen y la descargamos:
```
┌──(kali㉿kali)-[~/Documents/forensic/flagsAreStepic]
└─$ wget http://standard-pizzas.picoctf.net:62440/flags/upz.png
--2025-05-13 00:30:13--  http://standard-pizzas.picoctf.net:62440/flags/upz.png
Resolving standard-pizzas.picoctf.net (standard-pizzas.picoctf.net)... 3.22.195.189
Connecting to standard-pizzas.picoctf.net (standard-pizzas.picoctf.net)|3.22.195.189|:62440... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1788400 (1.7M) [image/png]
Saving to: ‘upz.png’

upz.png                      100%[=============================================>]   1.71M  1.02MB/s    in 1.7s    

2025-05-13 00:30:16 (1.02 MB/s) - ‘upz.png’ saved [1788400/1788400]
```

Y después verificamos steganografía con:
```
┌──(kali㉿kali)-[~/Documents/forensic/flagsAreStepic]
└─$ stepic -d -i upz.png
/usr/lib/python3/dist-packages/PIL/Image.py:3402: DecompressionBombWarning: Image size (150658990 pixels) exceeds limit of 89478485 pixels, could be decompression bomb DOS attack.
  warnings.warn(
picoCTF{fl4g_h45_fl4g00518d32}   
```