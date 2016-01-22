# SSL Certificates related

## Oneliner to get SHA1 fingerprint of SSL certificate of a site

You need to have `openssl` installed, then:

`echo | openssl s_client -connect google.com:443 |& openssl x509 -fingerprint -noout`

