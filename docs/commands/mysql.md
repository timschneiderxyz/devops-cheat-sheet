# Commands - MySQL

Create a new user:

```sh
sudo mysql -u root -p
CREATE USER <username>@'localhost' IDENTIFIED BY <user_password>;
EXIT;
```

Show all databases:

```sh
sudo mysql -u root -p
SHOW DATABASES;
```

Create a new database:

```sh
sudo mysql -u root -p
CREATE DATABASE <db_name>;
GRANT ALL ON <db_name>.* TO <username>@'localhost' IDENTIFIED BY <user_password> WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT;
```

Delete a database:

```sh
sudo mysql -u root -p
DROP DATABASE <db_name>;
```

Import a database:

```sh
mysql -u <username> -p <db_name> < <db_dump>
```
