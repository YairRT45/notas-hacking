The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

Hints:
1. https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html

## Solución 1:
Corrigiendo el archivo, al recibir una variable pasada como parámetro, debe ser mutable, y la referencia igual
```
fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &String){ // How do we pass values to a function that we want to change?
fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){


let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?


┌──(kali㉿kali)-[~/…/GS/RustFM/fixme2/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `/home/kali/Documents/GS/RustFM/fixme2/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}

picoCTF{4r3_y0u_h4v1n5_fun_y31?}

```