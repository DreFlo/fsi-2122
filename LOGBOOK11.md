# Task 1
## What part of the certificate indicates this is a CA’s certificate?
![](task1.1.png)
## What part of the certificate indicates this is a self-signed certificate?
![](task1.2.png)
The Subject Key Identifier and the Authority Key Identifier being the same indicates this certificate is self-signed.
## In the RSA algorithm, we have a public exponent e, a private exponent d, a modulus n, and two secret numbers p and q, such that n = pq. Please identify the values for these elements in your certificate and key files.

### Public Exponent
65537

### Private Exponent
![](task1.3.private.png)

### Modulus
![](task1.3.modulus.png)

### Prime 1
![](task1.3.p.png)

### Prime 2
![](task1.3.q.png)

# Task 2

We ran the commands that were give to us, changing 'bank32' to 'flroes2022' (our created website), thus creating a certificate signing request.

```bash
openssl req -newkey rsa:2048 -sha256 -keyout server.key -out server.csr -subj "/CN=www.flores2022.com/O=Flores Inc./C=PT" -addext "subjectAltName = DNS:www.flores2022.com, DNS:www.flores2022A.com, DNS:www.flores2022B.com"-passout pass:pass
```

# Task 3

We ran the commands, changing the needed files so we could copy the configuration file, thus turning the previous certificate signing request into an x509 certificate.

```bash
openssl ca -config openssl.cnf -policy policy_anything -md sha256 -days 3650 -in server.csr -out server.crt -batch -cert ca.crt -keyfile ca.key
```

#Task 4

