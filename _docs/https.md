---
layout: docs
title: HTTPS
toc_rank: 10
redirect_from: "/https.html"
description: Using WireMock with HTTPS.
---

## Handling HTTPS requests

To enable HTTPS using WireMock's self-signed certificate just specify an
HTTPS port:

```java
@Rule
public WireMockRule wireMockRule = new WireMockRule(wireMockConfig().httpsPort(8443));
```

To use your own keystore you can specify its path and optionally its
password:

```java
@Rule
public WireMockRule wireMockRule = new WireMockRule(wireMockConfig()
    .httpsPort(8443)
    .keystorePath("/path/to/keystore.jks")
    .keystorePassword("verysecret")); // Defaults to "password" if omitted
```

## Requiring client certificates


To make WireMock require clients to authenticate via a certificate you
need to supply a trust store containing the certs to trust and enable
client auth:

```java
@Rule
public WireMockRule wireMockRule = new WireMockRule(wireMockConfig()
    .httpsPort(8443)
    .needClientAuth(true)
    .trustStorePath("/path/to/truststore.jks")
    .trustStorePassword("mostsecret")); // Defaults to "password" if omitted
```

See running-standalone for command line equivalents.
