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