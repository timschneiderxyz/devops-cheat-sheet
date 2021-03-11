# Commands - PostgreSQL

Enter CLI:

```bash
  sudo -u postgres psql
```

List all user:

```bash
  \du+
```

Managing user:

```bash
  sudo -u postgres createuser -P -s -e <username> # Create a new user.
  sudo -u postgres dropuser -e <username> # Delete a user.
```

List all databases:

```bash
  \l
```

Managing databases:

```bash
  sudo -u postgres createdb -O <username> -e <db_name> # Create a new database with owner.
  sudo -u postgres dropdb -e <db_name> # Delete a database.
  sudo -u postgres psql <db_name> < <db_dump> # Import a database.
```
