Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 48247`.

Hints:
1. What kind of encoding uses dashes and dots?
2. The flag is in the format PICOCTF{}

## Solución:
Usando CyberChef:
```
Input: .--. .. -.-. --- -.-. - ..-.  -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .---- ..--- -.... .---- ....- ...-- ---.. .---- ---.. .---- 
Recipe: From Morse Code
Output: PICOCTFM0RS3C0D31SFUN1261438181

Flag: PICOCTF{M0RS3C0D31SFUN1261438181}
```