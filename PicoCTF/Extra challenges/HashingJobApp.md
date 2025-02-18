If you want to hash with the best, beat this test!
`nc saturn.picoctf.net 57704`

Hints:
1. You can use a commandline tool or web app to hash text
2. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución 1:
Con Nc y MD5 Hash Generator
```
┌──(yair㉿Yair)-[~]
└─$ nc saturn.picoctf.net 61986
Please md5 hash the text between quotes, excluding the quotes: 'having an operation'
Answer:
e8911c168f3f28c385ac7f3e4d0682cc
e8911c168f3f28c385ac7f3e4d0682cc
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'a morgue'
Answer:
1c5d1684ae8cd2f62a070044e5fc40c7
1c5d1684ae8cd2f62a070044e5fc40c7
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Keanu Reeves'
Answer:
4d2e1f8eabca061706aec58b21c2e199
4d2e1f8eabca061706aec58b21c2e199
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
```