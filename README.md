# fixssh
Setting up SSH with RSA authentication seems like a straightforward process, but the configuration has many pitfalls. If you're not careful, these will cost you some time at best and lock you out of your server at worst. fixshh is a simple command line tool that will automatically check for many of these common mistakes and give you hints on how to fix them. But don't worry: fixssh will never change any configuration by itself.

## Installation
For Ubuntu:
```
sudo apt-add-repository ppa:fish-shell/release-3 # add ppa with the latest version of fish https://launchpad.net/~fish-shell/+archive/ubuntu/release-3
sudo apt update
sudo apt install wget fish # install wget to download, and fish to execute the tool
sudo wget --output-document=/usr/local/bin/fixssh --quiet https://raw.githubusercontent.com/CheeseCrustery/sshoot/main/fixssh # download fixssh
sudo chmod 755 /usr/local/bin/fixssh # set global execute permissions
```

## Usage
Just run `fixssh [--user=USER] [--ascii-only]`. The tool will give you instructions for everything else.
