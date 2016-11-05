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
    
## Keyboard shortcuts

Useful keyboard shortcuts (some of which are dependent on the steps outlined above) are: 

* Launcher:
    * `Super + Space` opens launcher
    * `Ctrl + Tab` switches between lenses
* Terminal:
    * `Ctrl + Alt + T` opens Terminal
* Window management:s
    * `Ctrl + Super + [Up | Down]` Maximises, minimises or restores the current window
    * `Super + W` Spreads all windows
    * `Ctrl + Alt + D` Shows the desktop



