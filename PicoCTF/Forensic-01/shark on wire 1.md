We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

Hints:
1. Try using a tool like Wireshark
2. What are streams?

## Solución 1:
Revisamos la captura de paquetes con wireshark, revisamos los flujos de paquetes UDP y encontramos la flag en el stream 6
```
picoCTF{StaT31355_636f6e6e}
```