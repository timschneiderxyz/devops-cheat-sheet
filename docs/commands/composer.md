# Commands - Composer

Update composer:

```sh
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin/ --filename=composer
```

Managing packages:

```sh
composer require <package> # Add a new package.
composer remove --update-with-dependencies <package> # Remove a package.
composer update # Update all packages.
```

Update the autoloader:

```sh
composer dump-autoload -a
```

Nuke:

```sh
rm -rf vendor composer.lock && composer clear-cache && composer update
```
