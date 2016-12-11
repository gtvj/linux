# Using Laravel Homestead 

Before doing anything check the Laravel Homestead website to make sure VirtualBox and Vagrant instructions are **still the same as those shown below** (they might have changed)

* Install VirtualBox using the `.deb` installer from their website (remember to verify the checksum)
* Install Vagrant using 

Follow the instructions provided for getting Homestead set up. 

## Useful material

* Codecourse provide a really good [walkthrough playlist](https://youtu.be/tbPGuikTzKk?list=PLfdtiltiRHWEaImCreOC7UkK4U5Xv9LdI) on YouTube

## Daily use

* `cd ~/Homestead`
* `vagrant up`
* `vagrant ssh` - to remote into the VM
* `cd Code/project` (or wherever the root of your Laravel app is)
* Open a web browser and navigate to `http://laracasts.app` (or whatever your local app is being served from)
