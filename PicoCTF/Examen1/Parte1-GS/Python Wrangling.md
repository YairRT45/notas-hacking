Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/ende.py) using [this password](https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/pw.txt) to get [the flag](https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/flag.txt.en)?

Hints:
1. Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/ende.py`
2. $ man python

## Solución 1:
Ejecutamos el script, metiendo como parametro la flag encriptada, y posteriormente la contraseña
```
┌──(kali㉿kali)-[~/Documents/GS/wrangling]
└─$ python ende.py -h
Usage: ende.py (-e/-d) [file]
Examples:
  To decrypt a file named 'pole.txt', do: '$ python ende.py -d pole.txt'

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Documents/GS/wrangling]
└─$ cat pw.txt    
192ee2db192ee2db192ee2db192ee2db
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Documents/GS/wrangling]
└─$ python ende.py -d flag.txt.en 
Please enter the password:192ee2db192ee2db192ee2db192ee2db
picoCTF{4p0110_1n_7h3_h0us3_192ee2db}
```