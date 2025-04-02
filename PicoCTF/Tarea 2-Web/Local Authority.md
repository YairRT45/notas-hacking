Can you get the flag?Go to this [website](http://saturn.picoctf.net:50421/) and see what you can discover.

Hints:
1. How is the password checked on this website?

## Solución 1:
Sí nos intentamos logear con cualquier usuario y contraseña, y revisamos el código fuente, podemos verificar el archivo JavaScript que verifica la contraseña:
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}


Nos logeamos y nos muestra la flag:
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
```