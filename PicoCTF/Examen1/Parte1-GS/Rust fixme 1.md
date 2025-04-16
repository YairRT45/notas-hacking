Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).

Hints:
1. Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
2. [println!](https://doc.rust-lang.org/std/macro.println.html)
3. Rust has some pretty great compiler error messages. Read them maybe?

## Solución 1:
Corregimos las 3 líneas con comentarios al respecto:
Agregamos un ;
Completamos el return
Y colocamos las llaves que indican donde ira el parámetro mandado en la impresión
```
let key = String::from("CSUCKS") // How do we end statements in Rust?
let key = String::from("CSUCKS");

ret; // How do we return in rust?
return;

println!(
        ":?", // How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
println!(
        "{}",
        String::from_utf8_lossy(&decrypted_buffer)
    );

┌──(kali㉿kali)-[~/…/GS/RustFM/fixme1/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `/home/kali/Documents/GS/RustFM/fixme1/target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```