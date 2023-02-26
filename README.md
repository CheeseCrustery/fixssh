# sshoot
Setting up SSH with RSA authentication seems like a straightforward process, but the configuration process has many pitfalls. If you're not careful, these will cost you some time at best and lock you out of your server at worst. sshoot is a simple command line tool that will automatically check for many of these common mistakes and give you hints on how to fix them.

## Installation
For Ubuntu:
```
sudo apt install wget fish # install wget to download, and fish to execute the tool
sudo wget --output-document=/usr/local/bin/sshoot --quiet https://raw.githubusercontent.com/CheeseCrustery/sshoot/main/sshoot # download sshoot
sudo chmod 755 /usr/local/bin/sshoot # set global execute permissions
```

## Setup
```
set new_user frogcam
set private_key /root/id_rsa
adduser --create-home $new_user # https://www.howtogeek.com/806104/add-a-user-to-linux/
su $new_user
chsh -s /usr/bin/fish # https://www.howtogeek.com/669835/how-to-change-your-default-shell-on-linux-with-chsh/
mkdir ~/.ssh
ssh-keygen -y -f $private_key > ~/.ssh/authorized_keys
chmod -R 700 ~/.ssh/
nano /etc/ssh/sshd_config
```
Set `PasswordAuthentication no`, `PubkeyAuthentication yes`, `AuthorizedKeysFile` and (if needed) `PermitRootLogin yes`

## Usage
Set up SSH on the server which you want to connect to. Then, run `sshoot [username]`.
