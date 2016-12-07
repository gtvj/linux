# Machine set-up

Follow these steps to configure a fresh Linux (Ubuntu) install for my development and productivity settings on my Dell XPS 13.

## Install Ubuntu

Restore the computer to factory settings using _either_ the **Dell Recovery tool (within the OS)** or **Booting from the recovery USB**. Provide system configuration and restart when prompted.

## Get updates

* Use **Software updater** to get updates and **restart** if prompted
* Open **Ubuntu Software** and install any updates listed in the **updates** panel

## Install Synaptic Package Manager

Use **Ubuntu Software** to search for and install Synaptic Package Manager.

## Remove dell-super-key package

Use **Synaptic Package Manager** to:

Search for the `dell-super-key` package. Mark it for 'complete removal' and apply changes.

## Install CompizConfig Settings Manager

Use **Ubuntu Software** to search for and install CompizConfig Settings Manager.

## Install Unity Tweak Tool

Use **Ubuntu Software** to search for and install Unity Tweak Tool.

## Configure CompizConfig Settings Manager

Within CompizConfig Settings Manager: 

* Open the 'Ubuntu Unity Plugin' and go to its 'Launcher' tab
* For the 'Key to show the Dash, Launcher and Help Overlay' option:
    * Click the 'Disabled' button and check 'Enabled'
    * Click 'Grab key combination'
    * Set `<super>space` as the combination

## Install and configure development tools

### Vim

By default Ubuntu is provided with `vim-tiny` which does not support many of the commands I'm used to (such as change-inner-word etc.). Use Synaptic to locate and install the Ubuntu supported `vim-gnome` package and its dependencies.

This package **also allows you to run Vim in a GUI** like MacVim by either starting it with `vim -g` or as **GVim** from the launcher

### Git

To install and configure Git use:

* `sudo apt install git`
* `git config --global user.email "youremail@yourdomain.com"`
* `git config --global user.name "Your name"`
* `git config --global core.editor "vi"`

### Install Curl

Curl is needed for installing the latest LTS version of Node.js and NPM

* `sudo apt install curl`

### Node.js and NPM

Follow the instructions for installing Node.js via a package manager on **Ubuntu based distributions** provided on the [Node.js website](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions). At the time of writing these are: 

* `curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -`
* `sudo apt-get install -y nodejs`

Note: while there is a package called `nodejs` available on Synaptic it is quite old and does not work with some Grunt tasks.

### Install SASS

* Typing `sudo gem install sass` will install SASS

Note: this assumes Ruby is present (which can be checked via Synaptic)

### PHP

Using **Synaptic Package Manager**:

* Install `php` and its dependencies via Synaptic. Note: use the version that has the Ubuntu icon (since this is supported by the distribution.

### Install PhpStorm

* Download the `.tar` file from JetBrains (and check the checksum by passing it to `sha256sum`)
* Extract the file contents with `tar xzf PhpStorm2016.2.2.tar.gz` (using the name of the downloaded `.tar` file)
* The extracted folder will contain a file named `Install-Linux-tar.txt`. Follow the instructions (see the README of this repository for where to install it)

#### Enabling code formatting in PhpStorm

Unfortunately, the default keybinding to reformat code in PhpStorm `Ctrl + Alt + L` is also used by Unity to lock the screen. You can hand control over to PhpStorm by finding 'Keyboard' settings with the launcher and reassigning the related 'shortcut' to something else (like `Ctrl + Alt + Delete`)

#### PhpStorm settings repository

Set the PhpStorm settings repository to be [https://github.com/gtvj/phpstorm-settings](https://github.com/gtvj/phpstorm-settings)

### Install Firefox Developer Edition

At the time of writing this is a somewhat manual process since Firefox Developer edition is not available via Synaptic or Ubuntu software and I'm not keen in introducing PPAs.

* Download the `.tar` file from [mozilla.org](https://www.mozilla.org/en-GB/firefox/developer/)
* Extract the file contents with `tar xjf firefox-51.0a2.en-GB.linux-x86_64.tar.bz2` (replacing the filename shown with that which was downloaded)
* Move the extracted file to `/opt/` with `sudo mv firefox /opt/firefox_dev` (replacing 'firefox' with the name of the extracted folder)
* Create this 'desktop file' in the location shown `~/.local/share/applications/firefox_dev.desktop` and add the code below to it (note: the paths shown below should match the installation).

```
[Desktop Entry]
Name=Firefox Developer
GenericName=Firefox Developer Edition
Exec=/opt/firefox_dev/firefox
Terminal=false
Icon=/opt/firefox_dev/browser/icons/mozicon128.png
Type=Application
Categories=Application;Network;X-Developer;
Comment=Firefox Developer Edition Web Browser.

```
Having done this you should sign-in to Firefox and enable synchronisation. 

### Install xclip (to replicate OSX pbcopy and pbpaste)
* Use Synaptic to search for `xclip`
* Mark it for installation and click 'apply'

### Configure Bash

* Create a backup of `~/.bashrc` with `cp .bashrc .bashrc.bak`
* Append these commands to `~/.bashrc`

```bash
####################################################
# Custom settings from the Linux repository by @gtvj
####################################################

# Managing history
export HISTSIZE=10000 # 500 is the default
export HISTCONTROL=ignoreboth # ignoredups:ignorespace
export HISTIGNORE="history:pwd:exit:ls:ls -a:clear"

#########
# aliases
#########

# Git aliases
alias gst="git status"
alias glg="git log --oneline --decorate --graph"

# Alias xclip to mimic OSX pbcopy and pbpaste
alias pbcopy='xclip -selection clipboard'
alias pbpaste='xclip -selection clipboard -o'

# Aliases to launch software
# Note: For the time being I'm opting for aliases rather than adding items 
#       to PATH because it allows me to call them as I prefer in one step.
alias firefox="/opt/firefox_dev/./firefox"
alias phpstorm="/opt/PhpStorm-163.7743.50/bin/phpstorm.sh"

# Note: the pomodoro alias is dependent upon the phpstorm aliase
alias pomodoro="phpstorm & chromium-browser -url www.pluralsight.com"
```

## Optional steps

### Look and feel

Here are a few things I like to do:

* Keyboard:
    * Under 'System > Shortcuts' set the 'Lock screen' shortcut to `Ctrl + Alt + Delete` (might have been done above)
* Mouse & Touchpad:
    * Set 'Pointer speed' to fastest setting
* Menu bar:
    * Turn battery time on (not percentage)
    * Turn Bluetooth off
* Clear the Launcher by right clicking items and selecting 'Unlock from launcher'
* In Ubuntu 'Appearance' settings set:
    * Set 'Launcher icon size' smaller (28 is good)
    * 'Auto-hide the Launcher' with 'Reveal sensitivity' to highest setting
    * Select the 'enable workspaces' option
* Terminal:
    * Within Terminal Preferences change the current Profile to:
	* Uncheck 'Use colours from system theme'
	* Under 'Palette' choose the XTerm built-in scheme
