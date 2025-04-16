Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.

Hints:
1. Explore backend development with us
2. The head was dumped.

## Solución:
Para realizar esta flag, lo que tenemos que hacer es entrar en la pagina, en donde nos da una vista a las publicaciones de picoCTF, vamos a entrar en donde esta el hashtag de API Documentation. aqui nos encontraremos con varias "apis", entonces vamos hasta abajo a encontrar el que nos interesa que seria /headdump, con este lo ejecutamos y descargamos el archivo que nos deja, con este archivo solo queda usar la terminal para encontrar la flag
```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat heapdump-1744778778424.heapsnapshot | grep picoCTF{
picoCTF{Pat!3nt_15_Th3_K3y_bed6b6b8}
```
