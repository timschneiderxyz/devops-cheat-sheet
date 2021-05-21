# Commands - PM2

List the status of all application managed by PM2:

```sh
pm2 [list|ls|status]
```

Start an app:

```sh
pm2 start <file> --name <name>
```

Managing processes:

```sh
pm2 restart [name|id|all]
pm2 reload [name|id|all]
pm2 stop [name|id|all]
pm2 delete [name|id|all]
```

Setup startup script:

```sh
pm2 startup -u <username> --hp /home/<userhome>
pm2 save
```

Update:

```sh
npm install -g pm2@latest
pm2 update
```
