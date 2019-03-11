## View PEM encoded certificate
```shell
openssl x509 -in cert.pem -text -noout
openssl x509 -in cert.cer -text -noout
openssl x509 -in cert.crt -text -noout
```

## View DER encoded Certificate

```shell
openssl x509 -in certificate.der -inform der -text -noout
```

## Transform

### PEM to DER
```
openssl x509 -in cert.crt -outform der -out cert.der
```

### DER to PEM
```
openssl x509 -in cert.crt -inform der -outform pem -out cert.pem
```

## Fetch certificate from host
### With SNI
```shell
openssl s_client -showcerts -servername www.example.com -connect www.example.com:443 </dev/null
```
### Without SNI
```shell
openssl s_client -showcerts -connect www.example.com:443 </dev/null
```

### Gen certificate one line with SAN (OpenSSL ≥ 1.1.1)
```shell
openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes -keyout example.key -out example.crt -extensions san -config <(echo "[req]"; echo distinguished_name=req; echo "[san]"; echo subjectAltName=DNS:example.com,DNS:example.net,IP:10.0.0.1) -subj /CN=example.com
```
