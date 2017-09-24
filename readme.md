In order to ensure I can replicate my config, I have this repo cover what is needed to get my cluster online.

First we setup a controller node:
- Raspberry Pi 3 w/ official touch screen display
- OS Raspbian Jessie: http://downloads.raspberrypi.org/raspbian/images/raspbian-2017-07-05/
- Image the SD card with the OS
- Setup WIFI and remote ssh on boot
	- enable ssh: create file 'ssh' on the root of the SD card from source machine
	- setup wifi: create 'boot/wpa_supplicant.conf' on the SD card from the source machine
		- contents: `network={
    ssid="YOUR_SSID"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}`
- boot the system and get the IP from router