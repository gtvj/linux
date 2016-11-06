# Linux repository

## Purpose and approach

To capture information related to my migration to Linux as my primary OS.

The steps outlined below avoid PPAs and use the `/opt/` directory for manual installation of software (i.e. that which is not obtained via Ubuntu Software or Synaptic.

> Some PPAs are created for development or for beta or even alpha testing. They are not guaranteed to include stable or well-tested software. Anyone is allowed to create a PPA and there is no review procedure, so you’ll also want to install only PPAs from sources you trust. Use at your own risk. [The Official Ubuntu Book, 9th Edition](https://www.safaribooksonline.com/library/view/the-official-ubuntu/9780134512501/ch06.html)

## Machine set-up

Follow these steps to configure a fresh Linux (Ubuntu) install for my development and productivity settings on my Dell XPS 13.

### Install Ubuntu

Restore the computer to factory settings using _either_ the **Dell Recovery tool (within the OS)** or **Booting from the recovery USB**

### Get updates

* Use **Software updater** to get updates and **restart** when prompted
* Open **Ubuntu Software** and install any updates listed in the **updates** panel

### Install Synaptic Package Manager

Use **Ubuntu Software** to search for and install Synaptic Package Manager.

### Remove dell-super-key package

Use **Synaptic Package Manager** to:

* search for the `dell-super-key` package
* mark it for 'complete removal'
* apply changes

### Install CompizConfig Settings Manager

Use **Ubuntu Software** to search for and install CompizConfig Settings Manager.

### Configure CompizConfig Settings Manager

Within CompizConfig Settings Manager: 

* Open the 'Ubunty Unity Plugin' and go to its 'Launcher' tab
* For the 'Key to show the Dash, Launcher and Help Overlay' option:
    * Click the 'Disabled' button and check 'Enabled'
    * Click 'Grab key combination'
    * Set `<super>space` as the combination

### Install and configure development tools

#### Git

To install and configure Git use:

* `sudo apt install git`
* `git config --global user.email "youremail@yourdomain.com"`
* `git config --global user.name "Your name"`

#### NodeJS and NPM

Using **Synaptic Package Manager**:

* Install`nodejs` and `npm` packages along with the dependencies identified by Synaptic Package Manager

#### Install Atom text editor

* Download the latest `.deb` version of Atom from [atom.io](https://atom.io)
* Run `sudo dpkg --install atom-amd64.deb` (replacing `atom-amd64.deb` with the name of the file downloaded in the previous step
* Use `atom` command to launch Atom

#### Install Firefox Developer Edition

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
#### Install xclip (to replicate OSX pbcopy and pbpaste)
* Use Synaptic to search for `xclip`
* Mark it for installation and click 'apply'

#### Configure Bash

Append these commands to `~/.bashrc`

```bash
####################################################
# Custom settings from the Linux repository by @gtvj
####################################################

# Managing history
export HISTSIZE=10000 # 500 is the default
export HISTCONTROL=ignoreboth # ignoredups:ignorespace
export HISTIGNORE="history:pwd:exit:ls:ls -a:clear"

# Customising the command prompt
PS1="\W \$ > " # \W shows the current directory

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
alias firefox="/opt/firefox_dev/./firefox &"

```

### Install other software

#### Dropbox

* Install Dropbox via **Ubuntu Software**. When you first download it you'll:
     * be prompted to download the daemon.
     * need to sign in
* Choose the default destination `/home/gwyn/Dropbox/`
* Use Selective Sync to include only `Web Development Archive` and `WebDevelopment`

### Optional steps

#### Look and feel

Here are a few things I like to do:

* Screen Display:
    * Set 'Scale for menu and title bars' to 1.88 (and check that 'Resolution' is 3200 x 1800)
* Mouse & Touchpad:
    * Set 'Pointer speed' to fastest setting
* Menu bar:
    * Turn battery time on (not percentage)
    * Turn Bluetooth off
* Clear the Launcher by right clicking items and selecting 'Unlock from launcher'
* In Ubuntu 'Appearance' settings set:
    * Set 'Launcher icon size' smaller (28 is good)
    * 'Auto-hide the Launcher' with 'Reveal sensitivity' to highest setting
* Terminal:
    * Within Terminal Preferences change the current Profile to:
	* Uncheck 'Use colours from system theme'
	* Select the 'Grey on black' built-in scheme
	* Under 'Palette' choose the XTerm built-in scheme
    
## Keyboard shortcuts

Useful keyboard shortcuts (some of which are dependent on the steps outlined above) are: 

* Launcher:
    * `Super + Space` opens launcher
    * `Ctrl + Tab` switches between lenses
* Terminal:
    * `Ctrl + Alt + T` opens Terminal
* Window management:
    * `Ctrl + Super + [Up | Down]` Maximises, minimises or restores the current window
    * `Super + W` Spreads all windows
    * `Ctrl + Alt + D` Shows the desktop
    * `Ctrl + [T | W]` Creates or closes tabs (it also closes the application if there's only one tab)



