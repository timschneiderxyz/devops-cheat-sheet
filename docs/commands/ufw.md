# Commands - UFW

```sh
sudo ufw status # Show the current status of UFW and the allowed ports/services.
sudo ufw enable # Start and enabled on system startup.
sudo ufw disable # Stop and disable on system startup.
```

Managing ports:

```sh
sudo ufw allow <port>/tcp
sudo ufw deny <port>/tcp
```
