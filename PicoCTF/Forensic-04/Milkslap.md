🥛

Hints:
1. Look at the problem category

## Solución:
Descargamos la imagen buscando el nombre en la hoja de estilos de CSS y después ejecutamos lo siguientes comandos:
```
┌──(kali㉿kali)-[~/Documents/forensic/milkslap]
└─$ export RUBY_THREAD_VM_STACK_SIZE=500000000                                                                                        
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/forensic/milkslap]
└─$ zsteg -a milk.png                         
imagedata           .. text: "\n\n\n\n\n\n\t\t"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"

picoCTF{imag3_m4n1pul4t10n_sl4p5}
```