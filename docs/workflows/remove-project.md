# Workflows - Remove Project

Delete the project directory:

```sh
sudo rm -rf /var/www/<domain>
```

Delete the Nginx config/logs and reload:

```sh
sudo rm /etc/nginx/sites-available/<domain>.conf
sudo rm /etc/nginx/sites-enabled<domain>.conf
sudo rm /var/log/nginx/<domain>.*
sudo nginx -t && sudo systemctl reload nginx
```

Delete the SSL certificate:

```sh
sudo certbot revoke --cert-name <domain>
sudo certbot delete --cert-name <domain>
```

---

Depending on the type of project, a database needs to be removed and/or other things.
