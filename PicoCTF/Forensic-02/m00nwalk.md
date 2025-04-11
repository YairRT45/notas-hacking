 Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.

Hints:
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option

## Solución 1:
Con la herramienta SSTV para decodificar la imagen oculta dentro del audio
```
┌──(kali㉿kali)-[~/Documents/forensic/moonwalk]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                                                                                        [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!


Nos aparece una imagen con la flag, la transcribimos y el resultado es:
picoCTF{beep_boop_im_in_space}
```