# Server Setup - Nginx

Add the Nginx mainline repository:

```bash
echo "deb https://nginx.org/packages/mainline/debian `lsb_release -cs` nginx" \ | sudo tee /etc/apt/sources.list.d/nginx.list
```

Import the signing key:

```bash
curl -sS https://nginx.org/keys/nginx_signing.key | sudo apt-key add -
```

Install Nginx:

```bash
sudo apt update
sudo apt install nginx
```

Allow the necessary ports in the firewall:

```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

Create the necessary directories:

```bash
sudo mkdir /etc/nginx/sites-available
sudo mkdir /etc/nginx/sites-enabled
sudo mkdir /var/www
```

Disable the default config, edit the main config (check out the Nginx example config in this repository):

```bash
sudo mv /etc/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf.disabled
sudo nano /etc/nginx/nginx.conf
```

Check the config for errors and start Nginx:

```bash
sudo nginx -t && sudo systemctl start nginx
```

## Certbot

Install Certbot and create a common ACME-challenge directory:

```bash
sudo apt install certbot
sudo mkdir /var/www/_letsencrypt
sudo chown www-data:www-data /var/www/_letsencrypt
```


---


[Next - Databases](03-database.md)
