# Workflows - New Project

Create the project directory and set the permissions:

```sh
sudo mkdir /var/www/<domain>
sudo chown -R <username>:www-data /var/www/<domain>
sudo chmod -R 775 /var/www/<domain>
```

Add the Ngnix config for the project:

```sh
sudo nano /etc/nginx/sites-available/<domain>.conf
```

Activate the config by linking it to the sites-enabled directory:

```sh
sudo ln -s /etc/nginx/sites-available/<domain>.conf /etc/nginx/sites-enabled
```

Check the config for errors and reload Nginx:

```sh
sudo nginx -t && sudo systemctl reload nginx
```

Obtain the SSL certificate:

```sh
sudo certbot certonly --webroot -w /var/www/<domain> -d <domain> -d www.<domain> --email <email> -n --agree-tos
```

After obtaining the certificate, adjust the Nginx config for SSL and reload Nginx.

---

Depending on the type of project, a database needs to be created and/or other things.
