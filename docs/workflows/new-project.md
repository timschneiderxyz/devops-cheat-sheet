# Workflows - New Project

Create the project directory and set the permissions:

```bash
sudo mkdir /var/www/<domain>
sudo chown -R <username>:www-data /var/www/<domain>
sudo chmod -R 775 /var/www/<domain>
```

Add the Ngnix config for the project:

```bash
sudo nano /etc/nginx/sites-available/<domain>.conf
```

Activate the config by linking it to the sites-enabled directory:

```bash
sudo ln -s /etc/nginx/sites-available/<domain>.conf /etc/nginx/sites-enabled
```

Check the config for errors and reload Nginx:

```bash
sudo nginx -t && sudo systemctl reload nginx
```

Obtain the SSL certificate (after obtaining the certificate, adjust the Nginx config and reload Nginx):

```bash
sudo certbot certonly --webroot -w /var/www/_letsencrypt -d <domain> -d www.<domain> --email <email> -n --agree-tos
```

---

Depending on the type of project, a database needs to be created and/or other things.
