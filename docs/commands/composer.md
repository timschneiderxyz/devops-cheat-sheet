# Commands - Composer

Update composer:

```bash
  curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin/ --filename=composer
```

Managing packages:

```bash
  composer require <package> # Add a new package.
  composer remove --update-with-dependencies <package> # Remove a package.
  composer update # Update all packages.
```

Update the autoloader:

```bash
  composer dump-autoload -a
```

Nuke:

```bash
  sudo rm -rf vendor/ && sudo rm composer.lock && composer clear-cache && composer update
```
