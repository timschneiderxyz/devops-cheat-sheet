# Commands - npm

Managing packages:

```sh
npm install --save-prod # Install package in dependencies.
npm install --save-dev # Install package in devDependencies.
npm outdated # List outdated packages.
npm update # Update all packages.
```

Nuke:

```sh
rm -rf node_modules package-lock.json && npm install
```
