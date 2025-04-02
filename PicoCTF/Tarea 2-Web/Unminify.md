I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!Browse [here](http://titan.picoctf.net:62217/), and find the flag!

Hints:
1. Try CTRL+U / ⌘+U in your browser to view the page source. You can also add 'view-source:' before the URL, or try `curl <URL>` in your shell.
2. Minification reduces the size of code, but does not change its functionality.
3. What tools do developers use when working on a website? Many text editors and browsers include formatting.
## Solución 1:

```
Sí revisamos el código vemos que esta todo en una sola línea, y no es posible filtrar por 'picoCTF{' al haber más clases con nombres similares, pero si inspeccionamos la pagína y vemos el código desde ahí, vemos que lo organiza, y así es mas facil observar la flag presente en un parrafo

<p class="picoCTF{pr3tty_c0d3_d9c45a0b}"></p>

picoCTF{pr3tty_c0d3_d9c45a0b}
```