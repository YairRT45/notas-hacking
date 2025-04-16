Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).

Hints:
1. Read the comments...darn it!
## Solución 1:
Al leer los comentarios nos dice algo sobre salirnos de las reglas y hacer las cosas de forma no segura, por lo que simplemente eliminamos los comentarios en unsafe{ y donde encontramos la llave que cierra 

```
// unsafe {
unsafe {

// }
}

┌──(kali㉿kali)-[~/…/GS/RustFM/fixme3/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `/home/kali/Documents/GS/RustFM/fixme3/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

```