A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/b6fbb3a5560749f838cdc6db4950985767c4691db3a7b34a220e5654ee39e700/myNetworkTraffic.pcap) and try to get the flag.

Hints:
1. Filter your packets to narrow down your search.
2. Attacks were done in timely manner.
3. Time is essential

## Solución:
Tomamos todos los paquetes con longitud 12 y el de longitud 4
```
tcp.len==12
tcp.len==4
```
Y los ordenamos por tiempo, obtenemos las cadenas y nos encontramos con un texto en base64:
```
cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfMw==NmY0YTY2Ng==fQ==
```

Decodificamos:
```
┌──(kali㉿kali)-[~]
└─$ echo cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfMw==NmY0YTY2Ng==fQ== | base64 -d
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_36f4a666}  
```