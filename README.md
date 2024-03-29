# pmmp_binary
pmmp binary for panel  
(ubuntu20)
## warning
Use official binaries as much as possible. 
php 8.0  
https://github.com/pmmp/PHP-Binaries/releases/tag/php-8.0-latest  
php 8.1  
https://github.com/pmmp/PHP-Binaries/releases/tag/php-8.1-latest  

## Q&A
### 
If the following error occurs, please configure the cacert.pem file manually.
```
DiscordPHP.ERROR: failed to connect to websocket,retry in 5 seconds
{"e":"Connection to gateway.discord.gg:443 failed during TLS handshake: Unable to complete TLS handshake: SSL operation failed with code 1. OpenSSL Error messages: error:1416F086:SSL routines:tls_process_server_certificate:certificate verify failed"} []
```
```
ErrorException: "file_get_contents(): SSL operation failed with code 1. OpenSSL Error messages: error:1416F086:SSL routines:tls_process_server_certificate:certificate verify failed" (EXCEPTION)
```

In many cases, as mentioned in the [link](https://github.com/pmmp/php-build-scripts/issues/70#issuecomment-1399601785), the following text can be added to `bin/php7/bin/php.ini` to solve the problem
```ini
openssl.cafile=/etc/ssl/cert.pem
openssl.capath=/etc/ssl/certs
```

If the above steps do not help, please follow these steps:

- Download the cacert.pem file from the following link: https://curl.se/ca/cacert.pem
- Upload the cacert.pem file to `bin/php7/bin/cacert.pem` on the server
- Add the following text to `bin/php7/bin/php.ini`
```ini
openssl.cafile="cacert.pem"
curl.cainfo="cacert.pem"
```
or 
```ini
openssl.cafile="/path/to/cacert.pem"
curl.cainfo="/path/to/cacert.pem"
```
