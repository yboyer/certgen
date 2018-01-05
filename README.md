# `certgen`
> Generate mutiple certificate for a root CA certificate


## Usage
```shell
hostnames=$IP1,$IP2
docker run -v $PWD/certs:/certs yboyer/certgen $hostnames
```
###### and `./certs` will contain:
```
certs
├── ca-key.pem
├── ca.pem
├── <hostnames>-key.pem
└── <hostnames>.pem
```


## Why
Træfik needs CAs for backends calls ([RootCAs](https://github.com/containous/traefik/blob/2cb4acd6cced7344b435f5dcf548f988bec9d597/docs/configuration/commons.md)).
This tool can generate mutiple certificates for one self-signed root CA certificate.
