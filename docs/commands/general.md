# Commands - General

Update server:

```bash
sudo -- sh -c 'apt update && apt upgrade -y && apt autoremove -y && apt autoclean -y'
```

Reboot server:

```bash
sudo systemctl reboot
```

Shutdown server:

```bash
sudo systemctl poweroff
```

## User

```bash
cat /etc/passwd # List all users.
id <username> # Shows details about this user.
group <username> # Show in which groups the user is.
```

Managing users:

```bash
sudo adduser <username> # Create a new user.
sudo deluser --remove-home <username> # Delete a user and remove his home directory.
sudo usermod -aG <group> <username> # Add user to a group.
sudo deluser <username> <group> # Remove a user from a group.
```

## Packages

List all installed packages:

```bash
sudo apt list --installed
```

List all non-Debian packages:

```bash
aptitude search '?narrow(?installed, ?not(?origin(Debian)))'
```

Managing packages:

```bash
sudo apt update # Package lists are re-read and updated.
sudo apt upgrade # Update installed packages to a newer version if possible.
sudo apt autoremove # Uninstall unused dependencies.
sudo apt autoclean # Removes all stored archives in cache for packages that can't be downloaded anymore.
sudo apt install <package> # Install the package.
sudo apt remove <package> # Remove the package.
sudo apt purge <package> # Remove the package and its config files.
```

## Services

Show the status of a service:

```bash
sudo systemctl status <service>
```

Managing services:

```bash
sudo systemctl start <service>
sudo systemctl reload <service> # Keep the service running and reload the config files.
sudo systemctl restart <service> # Stop the service and restart it.
sudo systemctl stop <service>
sudo systemctl enable <service> # Enable the service to start up at boot.
sudo systemctl disable <service> # Disable the service to start up at boot.
```

## Directories/Files

Upload directories/files:

```bash
scp -P <ssh_port> -r [dir|file] <server_ip>:~/
```

Find directories/files:

```bash
sudo find / -name [dir|file]
```

Change user and group of directory/file:

```bash
sudo chown -R <username>:<group> [dir|file]
```

Change permissions of directory/file:

```bash
sudo chmod -R 775 [dir|file]
```

Create a Symlink:

```bash
sudo ln -s <absolut_path_source> <absolut_path_destination>
```

## Misc

Get server IP address:

```bash
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```

Create swap file:

```bash
sudo /bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024
sudo /sbin/mkswap /var/swap.1
sudo /sbin/swapon /var/swap.1
```

Set timezone:

```bash
sudo dpkg-reconfigure tzdata
```

If the command is not found:

```bash
export PATH=$PATH:/usr/sbin
```
