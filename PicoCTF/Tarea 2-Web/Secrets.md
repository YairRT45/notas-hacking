We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:50393/).

Hints:
1. folders folders folders

## Solución 1:
Si revisamos los enlaces "href" vemos un archivo en la carpeta 'secret'
```
<link href="[secret/assets/index.css](view-source:http://saturn.picoctf.net:59768/secret/assets/index.css)" rel="stylesheet" />

Al acceder a esta, vemos la carpeta 'hidden'
<link rel="stylesheet" href="[hidden/file.css](view-source:http://saturn.picoctf.net:59768/secret/hidden/file.css)" />

Si entramos a esta carpeta, vemos la 'superhidden'
<link href="[superhidden/login.css](view-source:http://saturn.picoctf.net:59768/secret/hidden/superhidden/login.css)" rel="stylesheet" />

Y finalmente si ingresamos a esta, encontramos la flag:
<h1>Finally. You found me. But can you see me</h1>
<h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_790d2615}</h3>

picoCTF{succ3ss_@h3n1c@10n_790d2615}
```