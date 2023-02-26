# sshoot
Setting up SSH with RSA authentication seems like a straightforward process, but the configuration process has many pitfalls. If you're not careful, these will cost you some time at best and lock you out of your server at worst. sshoot is a simple command line tool that will automatically check for many of these common mistakes and give you hints on how to fix them.

## Installation
For Ubuntu:
```
sudo apt install wget fish # install wget to download, and fish to execute the tool
sudo wget --output-document=/usr/local/bin/sshoot --quiet https://raw.githubusercontent.com/CheeseCrustery/sshoot/main/sshoot # download sshoot
sudo chmod 755 /usr/local/bin/sshoot # set global execute permissions
```

## Usage
Set up SSH on the server which you want to connect to. Then, run `sshoot [username]`.
