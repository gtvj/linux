# Linux repository

## Purpose

To capture information related to my migration to Linux as my primary OS. 

## Machine set-up

Follow these steps to configure a fresh Linux (Ubuntu) install for my development and productivity settings on my Dell XPS 13.

### Install Ubuntu

Restore the computer to factory settings using _either_: 

* Dell Recovery tool (within the OS)
* Booting from the recovery USB

### Get updates

* Use **Software updater** to get updates
* **restart** when prompted
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
* `git config --global user.name "Gwyn Jones"`


    
### Optional steps

#### Cosmetic

Here are a few things I like to do:

* Menu bar:
    * Show battery percentage
    * Turn Bluetooth off
* Clear the Launcher by right clicking items and selecting 'Unlock from launcher'
* In Ubuntu 'Appearance' settings set:
    * Set 'Launcher icon size' smaller (28 is good)
    * 'Auto-hide the Launcher' with 'Reveal sensitivity' to highest setting
    
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



