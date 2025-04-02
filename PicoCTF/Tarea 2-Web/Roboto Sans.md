The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:61888/) out.

Hints:
1. None

## Solución 1:
Sí ingresamos al archivo robots.txt podemos encontrar algunas líneas aparentemente decodificadas, si decodificamos la primera nos habla de un archivo file1.txt, el cual no existe, pero si decodificamos la segunda línea nos dice que revisemos la ruta js/myfile.txt en la cual se encuentra la flag
```
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```