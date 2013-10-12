---
layout: post
title: "Checking expiration date of SSL cert"
---

Here is you how you check whether an SSL cert is valid and hasn't yet expired

1. Retrieve the certificate.

    ```$ echo "" | openssl s_client -connect server:443 > certificate```

2. Check the expiration date of the certificate.

    ```$ openssl x509 -in certificate -noout -enddate```

Or you can use [ssl-cert-check][1] or [check-expire][2]

[1]: http://freshmeat.net/projects/ssl-cert-check/
[2]: http://sial.org/howto/openssl/check-expire/
