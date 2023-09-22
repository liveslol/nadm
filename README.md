# nadm - Not Only a Dotfiles Manager

## Overview

**nadm** (Not Only a Dotfiles Manager) is a simple project of mine, because I just wanted to create a dotfiles manager so it's not phenomenal and I don't really work on it anymore. It's all just one bash script so you can use it as a template if you want.

## Installation

To install **nadm**, you can use the following command:

```
sudo curl -o /usr/local/bin/nadm https://raw.githubusercontent.com/notbluie/nadm/main/nadm && sudo chmod +x /usr/local/bin/nadm
```
Now, if you want to use it comfortably, you'll need to add those lines to your .bashrc /.zshrc or shell config:

```
export nadmenv="$HOME/.local/share/nadm/dotfiles"
alias nadmenv='cd "$nadmenv"'
```
What it does, is that if you want to go into your enviroment (which will be explained below) you can just do ```nadmenv``` instead of ```cd ~/.local/share/nadm```
## Usage
As you can see from the name, you don't have to use only for dotfiles. It's meant to be used like this:
So you have multiple files / folders on your system that you all want to add to one repository. You create a git repo but you don't want to manually re-copy the files there everytime you make changes in one of them. That's when nadm comes in. You add all of them into the enviroment and then with just one command it synchronizes all of the files to be exactly as you have them on your system.

The commands are:
- ```nadm init```creates the enviroment at ~/.local/share/nadm
- ```nadm add <path>``` adds the specified file / folder to the enviroment (and remembers it's path for the update)
- ```nadm remove <path>``` removes the specified file / folder from the enviroment (and it's path)
- ```nadm update``` takes all the saved paths from the added files and re-copys them so they're synchronized
- ```nadm uninstall``` removes the nadm enviroment (if you want to fully remove nadm you'll have to remove the script lcoated at /usr/local/bin/nadm 

To go to the enviroment, you can either do ```cd ~/.local/share/nadm/dotfiles``` or if you did the optional steps during installation you can just do ```nadmenv```.
