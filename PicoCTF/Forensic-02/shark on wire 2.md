We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

Hints:
1. None

## Solución 1:
Al revisar los paquetes nos damos cuenta que la flag se encuentra en los UDP, el mensaje esta cifrado en el puerto de origen, por lo cual con un script de python la podemos obtener
```
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport -5000)

print(flag)



┌──(kali㉿kali)-[~/Documents/forensic/sharkOnWire/two]
└─$ python exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```