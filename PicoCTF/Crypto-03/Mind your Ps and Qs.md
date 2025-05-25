In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

Hints:
1. Bits are expensive, I used only a little bit over 100 to save money

## Solución:
```
┌──(kali㉿kali)-[~/Documents/crypto/psandqs]
└─$ cat values 
Decrypt my super sick RSA:
c: 421345306292040663864066688931456845278496274597031632020995583473619804626233684
n: 631371953793368771804570727896887140714495090919073481680274581226742748040342637
e: 65537                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Documents/crypto/psandqs]
└─$ python       
Python 3.13.2 (main, Mar 13 2025, 14:29:07) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> n = 631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> e = 65537
>>> p = 1461849912200000206276283741896701133693
>>> q = 431899300006243611356963607089521499045809
>>> p * q == n
True
>>> tn = (p - 1) * (q - 1)
>>> d = pow(e, -1, tn)
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639647889241102700065917
>>> bytes.fromhex(hex(m)[2:])
b'picoCTF{sma11_N_n0_g0od_55304594}'

```