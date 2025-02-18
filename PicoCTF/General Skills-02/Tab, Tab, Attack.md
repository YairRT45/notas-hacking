Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)

Hints:
1. After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución 1:
Usando tab para autocompletar los directorios, strings para convertir el archivo binario a texto y grep para encontrar la flag
```
YagooRT-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep pico
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
```