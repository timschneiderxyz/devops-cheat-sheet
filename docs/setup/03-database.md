# Server Setup - Database

## PostgreSQL

Add the PostgreSQL repository:

```bash
  echo "deb https://apt.postgresql.org/pub/repos/apt `lsb_release -cs`-pgdg main" \ | sudo tee /etc/apt/sources.list.d/postgresql.list
```

Import the signing key:

```bash
  curl -sS https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```

Install PostgreSQL:

```bash
  sudo apt update
  sudo apt install postgresql
```

Create a new user:

```bash
  sudo -u postgres createuser -P -s -e <username>
```

## MySQL

Install MySQL:

```bash
  sudo apt install default-mysql-server
```

Secure the installation:

```bash
  sudo mysql_secure_installation
```

```plaintext
  Enter current password for root (enter for none): Just press enter
  Set root password? [Y/n]: Y
  New password: Enter password
  Re-enter new password: Repeat password
  Remove anonymous users? [Y/n]: Y
  Disallow root login remotely? [Y/n]: Y
  Remove test database and access to it? [Y/n]: Y
  Reload privilege tables now? [Y/n]: Y
```

Create a new user:

```bash
  sudo mysql -u root -p
  CREATE USER <username>@'localhost' IDENTIFIED BY <user_password>;
  EXIT;
```

## Redis

Install Redis:

```bash
  sudo apt install redis-server
```

Edit the config file:

```bash
  sudo nano /etc/redis/redis.conf
```

```plaintext
  supervised systemd
  bind 127.0.0.1 ::1
```

Restart Redis:

```bash
  sudo systemctl restart redis
```


---


[Next - PHP](04-php.md)
