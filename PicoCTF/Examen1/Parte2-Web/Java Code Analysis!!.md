BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/480/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:64581/).

Hints:
1. Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
2. The 'role' and 'userId' fields in the JWT can be of interest to you!
3. The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
4. Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

## Solución:
Encontramos el token JWT al ingresar con las credenciales dadas por el reto, lo encontramos inspeccionando la pagina, en el local storage, lo encontramos con lo siguiente: 
```
{
  "role": "Free",
  "iss": "bookshelf",
  "exp": 1745386954,
  "iat": 1744782154,
  "userId": 1,
  "email": "user"
}
```
Lo convertimos con lo siguiente y la clave '1234':
```
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1745386954,
  "iat": 1744782154,
  "userId": 2,
  "email": "admin"
}
Ingresamos el nuevo token y encontramos la flag en el pdf:
Great job! Here’s your flag:picoCTF{w34k_jwt_n0t_g00d_7745dc02}
```