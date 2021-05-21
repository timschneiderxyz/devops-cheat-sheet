# Commands - PostgreSQL

Enter CLI:

```sh
sudo -u postgres psql
```

List all user:

```sh
\du+
```

Managing user:

```sh
sudo -u postgres createuser -P -s -e <username> # Create a new user.
sudo -u postgres dropuser -e <username> # Delete a user.
```

List all databases:

```sh
\l
```

Managing databases:

```sh
sudo -u postgres createdb -O <username> -e <db_name> # Create a new database with owner.
sudo -u postgres dropdb -e <db_name> # Delete a database.
sudo -u postgres psql <db_name> < <db_dump> # Import a database.
```
