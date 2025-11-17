
## Generate a 2048-bit RSA private key and Certificate Signing Request (CSR)

```
openssl req -newkey rsa:2048 -keyout PRIVATEKEY.key -out MYCSR.csr
```

## Save an encrypted private key unencrypted

```
openssl rsa -in <encrypted_private.key>  -out <decrypted_private.key>
```

## Convert x509 certificate to PEM

```
openssl x509 -in cert.crt -out cert.pem 
```
