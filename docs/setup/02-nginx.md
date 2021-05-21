# Server Setup - Nginx

Add the Nginx mainline repository:

```sh
echo "deb http://nginx.org/packages/mainline/debian `lsb_release -cs` nginx" \ | sudo tee /etc/apt/sources.list.d/nginx.list
```

Import the signing key:

```sh
curl -sS https://nginx.org/keys/nginx_signing.key | sudo apt-key add -
```

Install Nginx:

```sh
sudo apt update
sudo apt install nginx
```

Allow the necessary ports in the firewall:

```sh
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

Create the necessary directories:

```sh
sudo mkdir /etc/nginx/sites-available
sudo mkdir /etc/nginx/sites-enabled
sudo mkdir /var/www
```

Generate a Diffie-Hellman key:

```sh
sudo openssl dhparam -out /etc/nginx/dhparam.pem 2048
```

Remove the default-site config, edit the Nginx main config and add the necessary config for your site/app:

> Create the config for your project in sites-available and activate it with a symlink in sites-enabled.
> See [workflows/new-project](../workflows/new-project.md) for more information on this.
> You can also check out [examples/nginx](../../examples/nginx/) for some Nginx example configs.

```sh
sudo rm /etc/nginx/conf.d/default.conf
sudo nano /etc/nginx/nginx.conf
sudo nano /etc/nginx/sites-available/<domain>.conf
sudo ln -s /etc/nginx/sites-available/<domain>.conf /etc/nginx/sites-enabled
```

Check the config for errors and start Nginx:

```sh
sudo nginx -t && sudo systemctl start nginx
```

## Certbot

Install Certbot and create a common ACME-challenge directory:

```sh
sudo apt install certbot
```


---


[Next - Databases](03-database.md)
