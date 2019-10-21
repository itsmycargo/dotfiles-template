# Dotfiles Template

Use this repository as your starting point for your customised dotfiles.
This repository is designed to work with https://github.com/itsmycargo/dotfiles repository.


Please fork this repository under your own personal GitHub account.

## Configuration

### Installation Directories

It is possible to configure and customise installation process by adding extra scripts to correct directories. Every script must end with `.sh`, only those files will be run automatically. This allows to add extra supporting files to smae directories as well.

#### install.d

This directory holds extra scripts that are run during installation step. Scripts are run after RCM has been run, but before any homebrew installations.

#### post-install.d

This directory is run last during installation process. Any scripts here 

### ZSH Configuration

ZSH configuration has own special directory, `zsh`. In this directory, create topic folders by simply creating sub directories within. You can customise your ZSH setup easily by adding custom aliases, functions and path setup.

#### Customisation Files

** `path.zsh` **

These files are basic setup files that mostly sets up correct environment variables or adds key elements to PATH. These files are always loaded first.

** `completion.zsh` **

These files adds custom completion to the shell. These files are loaded last and after loading ZSH auto-complete functionality.

** `*.zsh` **

Anything else in the topic folders that are named ending `.zsh` are loded after `path.zsh` files and can basically do anything.

### Application Configuration

Anything else in this directory gets automcatically symlinked to your home directory, , folders are created as `.folder` and files inside folders are symlinked. Adding custom application configuration is as simple as creating new files or directories here.

## RCM

Dotfiles is using RCM for configuration management. RCM offers simple tool to move existing application configuration to your dotfiles repository, `mkrc` tool.

### Create global dotfile

To create common, shared dotfile from existing file, simply run in your home directory:

    $ mkrc ~/.config_file

If you have specific configruation file that differs from computer to computer (e.g. SSH config), you can create host specific dotfile with:

    $ mkrc -o ~/.ssh/config

