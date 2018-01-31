# Surge APP Shadowsocks Encrypt Support Module

## Usage
- Download The SSEncrypt Module form URL below
```url
https://raw.githubusercontent.com/Unbinilium/Surge/master/SSEncrypt.module
```

## Example Configurations
- Only the Proxy part and you are suppose to fill **SeverIP**、**ServerPort**、**EncryptMethod** and **Paddword** manually
```conf
[Proxy]
Shadowsocks = custom,ServerIP,ServerPort,EncryptMethod,Password,https://raw.githubusercontent.com/Unbinilium/Surge/master/SSEncrypt.module
```
- If you are using <a href="https://github.com/shadowsocks/simple-obfs" target="_blank">simple-obfs</a>, Please try this example after fill **ObfsMethod** and **ObfsHost** manually
```conf
custom,ServerIP,ServerPort,EncryptMethod,Password,https://raw.githubusercontent.com/Unbinilium/Surge/master/SSEncrypt.module,obfs=ObfsMethod,obfs-host=ObfsHost
```

## Notice
- Now only supported these Stream Ciphers for encrypt methods
```txt
rc4
rc4-md5
rc2-cfb
bf-cfb
des-cfb
idea-cfb
seed-cfb
cast5-cfb
camellia-128-cfb
camellia-192-cfb
camellia-256-cfb
aes-128-cfb
aes-192-cfb
aes-256-cfb
aes-128-ctr
aes-192-ctr
aes-256-ctr
salsa20
chacha20
chacha20-ietf
```
- These AEAD Ciphers are recommend to you instead of the Stream Ciphers
```txt
aes-128-gcm
aes-192-gcm
aes-256-gcm
chacha20-ietf-poly1305
```
- Now supported these obfs method
```txt
http
tls
```
- Also the default obfs-host is here if you leave there free. Recommend to use CDN domains which are not blocked. It related with your server side configurations
```txt
cloudfront.com
```

## Suggestions
- For better security, use these cipher as possible as you can <a href="https://en.wikipedia.org/wiki/Authenticated_encryption" target="_blank">AEAD</a> (Authenticated Encryption with Associated Data)
```txt
aes-128-gcm
aes-192-gcm
aes-256-gcm
chacha20-ietf-poly1305
```
- Add a TLS obfs and change the default obfs-host
- Try to use TCP Fast Open by add the perfix ```,tfo=true``` in the end of the line in the Proxy configurations

## Manual of Surge App
- View official Surge <a href="https://manual.nssurge.com/" target="_blank">Manual Guides</a>
