# Commands - Certbot

List all of the installed certificates:

```sh
sudo certbot certificates
```

Obtain the SSL certificate (after obtaining the certificate, adjust the Nginx config and reload Nginx):

```sh
sudo certbot certonly --webroot -w /var/www/<domain> -d <domain> -d www.<domain> --email <email> -n --agree-tos
```

Managing certificates:

```sh
sudo certbot renew --cert-name <domain> --force-renewal # Renew the certificate now, regardless of whether it expires soon.
sudo certbot renew --force-renewal # Renew all certificates now, regardless of whether they expire soon.
sudo certbot renew --dry-run # Test the renewal of all certificates.
sudo certbot revoke --cert-name <domain> # Revokes the certificate.
sudo certbot delete --cert-name <domain> # Deletes all relevant files of a certificate.
```
