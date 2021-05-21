# Server Setup - General

Set up a Debian Server.

## First Steps

Change the root password:

```sh
passwd root
```

Create a new user and add him to the sudo group:

```sh
adduser <username>
usermod -aG sudo <username>
```

Copy the SSH key of the root user to the new user and set the permissions:

```sh
cp -r ~/.ssh /home/<username>
chown -R <username>:<username> /home/<username>/.ssh
chmod 700 /home/<username>/.ssh
```

Login as the new user:

```sh
su - <username>
```

Update packages:

```sh
sudo -- sh -c 'apt update && apt upgrade -y && apt autoremove -y && apt autoclean -y'
```

## Security

### SSH

Disable root and password login and change the default SSH port:

```sh
sudo nano /etc/ssh/sshd_config
```

The following changes must be made here (replace XX for the new port):

```plaintext
Port XX
PermitRootLogin no
PasswordAuthentication no
PermitEmptyPasswords no
ChallengeResponseAuthentication no
UsePAM no
PrintMotd yes
```

Save the file and reload the SSH config:

```sh
sudo systemctl reload sshd
```

### Firewall

Set up a basic firewall (XX is the port we just set for SSH):

```sh
sudo apt install ufw
sudo ufw allow XX/tcp
sudo ufw enable
```

### Fail2ban

Set up Fail2ban:

```sh
sudo apt install fail2ban
```

Copy jail.conf to jail.local to prevent changes from being overwritten when updating:

```sh
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
```

Edit the new file:

```sh
sudo nano /etc/fail2ban/jail.local
```

```plaintext
bantime = 30m
findtime = 15m
maxretry = 5

banaction = ufw
banaction_allports = ufw

[sshd]
enabled = true
```

Reload fail2ban:

```sh
sudo fail2ban-client reload
```

## Additional Packages

```sh
sudo apt install curl unzip git
```


---


[Next - Nginx](02-nginx.md)
