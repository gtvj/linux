# Machine setup for Ubuntu 17.04

## Upgrade to 17.04

* You can install 16.04 this from either the Dell Recovery or USB. 
* Having done this open 'Software and Updates' and got to the 'Updates' tab. Go to the 'Notify me of a new Ubuntu version' select 'For any new version'.
* You can then open 'Software updater' and update to 17.04. You may need to update to 16.10 first.

## Remove Dell Super Key

Within a terminal type `sudo apt remove dell-super-key` to remove the package that prevents the super key from working.

## Ignore trackpad while typing

Within 'System settings' under 'Mouse and Trackpad' choose 'Ignore trackpad while typing'

## Enable workspaces

Within 'Appearance' choose 'Enable workspaces' 

## Install Unity Tweak Tool and CompizConfig Settings Manager

See instructions in 16.04 setup instructions

## Install 'Pointing devices' and enabled palm rejection

This is an **important** one for peace of mind. The default palm rejection on the XPS/Ubuntu out of the box is dreadful.

Search Ubuntu Software for 'Pointing devices' and install the app (it's the one that's described as the successor to GSynaptics). This will allow you to configure palm rejection properly

## Install XMind

Having never got XMind to work in 16.x I've found that it does work in 17. To install it follow the [XMind 8 installation instructions](http://www.xmind.net/m/PuDC). The one amendment necessary is to the `xmind.desktop` file location. To get this to work I had to place it in `~/.local/share/applications/` rather than the location specified in the instructions.


