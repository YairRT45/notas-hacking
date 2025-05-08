I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/2e739f9e0dc9f4c1556ea6b033c3ec8e/Forensics%20is%20fun.pptm)

Hints: 
1. None

## Solución:
Un archivo .pptm se puede comportar como un .zip, entonces lo descomprimimos:
```
┌──(kali㉿kali)-[~/Documents/forensic/MacroHard]
└─$ unzip 'Forensics is fun.pptm'
Archive:  Forensics is fun.pptm
  inflating: [Content_Types].xml     
  inflating: _rels/.rels             
  inflating: ppt/presentation.xml    
  inflating: ppt/slides/_rels/slide46.xml.rels  
  inflating: ppt/slides/slide1.xml   
  inflating: ppt/slides/slide2.xml   
  inflating: ppt/slides/slide3.xml   
  inflating: ppt/slides/slide4.xml   
  inflating: ppt/slides/slide5.xml   
  inflating: ppt/slides/slide6.xml   
  inflating: ppt/slides/slide7.xml   
  inflating: ppt/slides/slide8.xml   
.
.
.
```
Y buscamos entre todos los archivos algo inusual, aquí encontré un archivo llamado hidden, con una aparente codificación en base64:
```
┌──(kali㉿kali)-[~/Documents/forensic/MacroHard]
└─$ cat ppt/slideMasters/hidden 
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q  
```

Al eliminar los espacios y decodificar la cadena, encontramos la flag:
```
┌──(kali㉿kali)-[~/Documents/forensic/MacroHard]
└─$ cat ppt/slideMasters/hidden | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}  
```