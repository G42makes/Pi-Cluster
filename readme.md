In order to ensure I can replicate my config, I have this repo cover what is needed to get my cluster online.

First we setup a controller node:
- Raspberry Pi 3 w/ official touch screen display
- OS Raspbian Jessie: http://downloads.raspberrypi.org/raspbian/images/raspbian-2017-07-05/
- Image the SD card with the OS
- Setup WIFI and remote ssh on boot
	- enable ssh: create file 'ssh' on the root of the SD card from source machine
	- setup wifi: create 'wpa_supplicant.conf' on the SD card from the source machine
		- contents: `network={
    ssid="YOUR_SSID"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}`
	- see: https://raspberrypi.stackexchange.com/questions/10251/prepare-sd-card-for-wifi-on-headless-pi
- boot the system and get the IP from router
	- file system should resize and reboot
	- login(ssh, but the display should be working already, i just don't assume keyboard installed)
	- change 'pi' user password: `$ passwd`
- and install the pre-requisites for using this repo:
	- `$ sudo apt-get update`
	- `$ sudo apt-get install -y python-pip git python-dev libffi-dev libssl-dev sshpass`
	- `$ sudo pip install ansible`
	- `$ git clone https://github.com/G42makes/Pi-Cluster.git`
	- run stuff... TODO: write this and use `ansible-pull` command
