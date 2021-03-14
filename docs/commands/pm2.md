# Commands - PM2

List the status of all application managed by PM2:

```bash
pm2 [list|ls|status]
```

Start an app:

```bash
pm2 start <file> --name <name>
```

Managing processes:

```bash
pm2 restart [name|id|all]
pm2 reload [name|id|all]
pm2 stop [name|id|all]
pm2 delete [name|id|all]
```

Setup startup script:

```bash
pm2 startup -u <username> --hp /home/<userhome>
pm2 save
```

Update:

```bash
npm install -g pm2@latest
pm2 update
```
