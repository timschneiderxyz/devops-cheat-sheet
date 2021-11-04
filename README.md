# DevOps Cheat Sheet

Fed up with having to remember all the different commands you need every now and then to manage your server? Finally being able to say: "Look, mum, I can do DevOps too"?

Because I felt the same way, I try to summarise the most important commands and configurations in this repository and expand them over time.

Since I mainly use Debian as the operating system for my servers, the system-dependent commands, such as those concerning systemd or the package manager, are related to it. Most other commands, however, should be identical or at least very similar on all other Linux distributions.

## Docs

### Setup

Instructions for setting up a Debian server.

- [01. General](./docs/setup/01-general.md)
- [02. Nginx](./docs/setup/02-nginx.md)
- [03. Databases](./docs/setup/03-database.md)
- [04. PHP](./docs/setup/04-php.md)
- [05. NodeJS](./docs/setup/05-nodejs.md)

### Workflows

Instructions for different workflows.

- [New Project](./docs/workflows/new-project.md)
- [Remove Project](./docs/workflows/remove-project.md)

### Commands

Collection of frequently used commands for various programmes.

#### Server

- [General](./docs/commands/general.md)
- [UFW](./docs/commands/ufw.md)

#### Hosting

- [Nginx](./docs/commands/nginx.md)
- [Certbot](./docs/commands/certbot.md)

#### Databases

- [PostgreSQL](./docs/commands/postgresql.md)
- [MySQL](./docs/commands/mysql.md)
- [Redis](./docs/commands/redis.md)

#### PHP

- [PHP](./docs/commands/php.md)
- [Composer](./docs/commands/composer.md)

#### NodeJS

- [nvm](./docs/commands/nvm.md)
- [npm](./docs/commands/npm.md)
- [PM2](./docs/commands/pm2.md)

## Examples

Example configuration files for:

- Nginx
