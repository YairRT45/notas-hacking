Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:50736/).

Hints:
1. any redirections?

## Solución:
El reto mismo nos dice las credenciales para ingresar, pero si interceptamos las peticiones con BurpSuite, veremos que después del login nos redirige a dos paginas antes de ir a la pagina de busqueda, si revisamos estas redirecciones y vemos el id de cada uno, podemos apreciar que estan en base64:
```
1ra: GET /next-page/id=cGljb0NURntwcm94aWVzX2Fs HTTP/1.1
2da: GET /next-page/id=bF90aGVfd2F5X2RmNDRjOTRjfQ== HTTP/1.1

Unimos ambas y usando CyberChef decodificamos:
Input: cGljb0NURntwcm94aWVzX2FsbF90aGVfd2F5X2RmNDRjOTRjfQ==
Recipe: From Base64
Output: picoCTF{proxies_all_the_way_df44c94c}
```