---
title: Generate .pfx from cert and private key
date: 2023-09-03 010:00.00 +0000
categories: [Certificates,OpenSSL]
tags: [certificates,openssl,pfx,encryption]
---

# How to generate .pfx from cert and private key
Sometimes you may have a public key and private key, but you might specifically need .pfx file. Pfx file is a password protected file certificate. To generate it with the help of OpenSSL, follow below steps.


## Install OpenSSL
OpenSSL is probably already installed in your system. If not, just follow the installation guides for you OS.

## Generate .pfx from cert and private key
To generate pfx, run below command in directory where resides openssl.exe. Replace the values in <>

```bash
openssl pkcs12 -export -out <domain.name.pfx> -inkey <domain.name.key> -in <domain.name.crt>
```

**domain.name.pfx** is the name of file that will be generated  
**domain.name.key** is the file with private key  
**domain.name.crt** is the file with public key

When prompted, enter password that will be used when importing the certificate.