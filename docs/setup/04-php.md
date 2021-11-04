# Server Setup - PHP

Add the PHP repository:

```sh
echo "deb https://packages.sury.org/php `lsb_release -cs` main" \ | sudo tee /etc/apt/sources.list.d/php.list
```

Import the signing key:

```sh
curl -sS https://packages.sury.org/php/apt.gpg | sudo apt-key add -
```

Install PHP and all necessary packages:

```sh
sudo apt update
sudo apt install php8.0-fpm php8.0-pgsql php8.0-mysql php8.0-zip php8.0-curl php8.0-mbstring php8.0-xml php8.0-intl php8.0-gd php8.0-imagick
```

Edit the config files (adjust the file path according to the installed version):

```sh
sudo nano /etc/php/8.0/fpm/pool.d/www.conf
```

```plaintext
user = www-data
group = www-data
listen.owner = www-data
listen.group = www-data
```

```sh
sudo nano /etc/php/8.0/fpm/php.ini
```

```plaintext
cgi.fix_pathinfo=0
memory_limit = 256M
max_execution_time = 300
upload_max_filesize = 100M
post_size_limit = 100M
```

```sh
sudo nano /etc/php/8.0/cli/php.ini
```

```plaintext
memory_limit = -1
max_execution_time = 0
```

Restart PHP:

```sh
sudo systemctl restart php8.0-fpm.service
```

## Composer

```sh
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin/ --filename=composer
```

---

[Next - NodeJS](05-nodejs.md)
