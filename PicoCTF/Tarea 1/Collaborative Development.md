My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)

Hints:
1. `git branch -a` will let you see available branches
2. How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
3. Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

## Solución 1:
Verificamos las ramas y vamos de una en una para armar la flag uniendo las ramas y corrigiendo el archivo
```
┌──(yair㉿Yair)-[~/drop-in]
└─$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main

┌──(yair㉿Yair)-[~/drop-in]
└─$ git merge feature/part-1
Already up to date.

┌──(yair㉿Yair)-[~/drop-in]
└─$ git merge feature/part-2
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.

┌──(yair㉿Yair)-[~/drop-in]
└─$ nano flag.py

┌──(yair㉿Yair)-[~/drop-in]
└─$ git add .

┌──(yair㉿Yair)-[~/drop-in]
└─$ git commit -m "first merge"
[main 2b30ef4] first merge

┌──(yair㉿Yair)-[~/drop-in]
└─$ git merge feature/part-3
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.

┌──(yair㉿Yair)-[~/drop-in]
└─$ nano flag.py

┌──(yair㉿Yair)-[~/drop-in]
└─$ git add .

┌──(yair㉿Yair)-[~/drop-in]
└─$ git commit -m "second merge"
[main 5111c60] second merge

┌──(yair㉿Yair)-[~/drop-in]
└─$ python3 flag.py
Printing the flag...
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
```