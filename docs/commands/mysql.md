# Commands - MySQL

Create a new user:

```bash
sudo mysql -u root -p
CREATE USER <username>@'localhost' IDENTIFIED BY <user_password>;
EXIT;
```

Show all databases:

```bash
sudo mysql -u root -p
SHOW DATABASES;
```

Create a new database:

```bash
sudo mysql -u root -p
CREATE DATABASE <username>;
GRANT ALL ON <db_name>.* TO <username>@'localhost' IDENTIFIED BY <user_password> WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT;
```

Delete a database:

```bash
sudo mysql -u root -p
DROP DATABASE <db_name>;
```

Import a database:

```bash
mysql -u <username> -p <db_name> < <db_dump>
```
