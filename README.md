# Booting RPI4 from SSD

install any os with rpi app :

### When the system boot up from the sd card start the following commands:

sudo apt update  && sudo apt upgrade -y
sudo rpi-update && sudo reboot

### now connect your ssd to the PI and check your block usually it's known as sda:
lsblk

## copy the files from your sd card to the ssd:
sudo dd if=/dev/sdcard of=/dev/ssd bs=4M status=progress && sync
in here change "sdcard" to your sdcard and "ssd" to your ssd, usually sdcard start with mm0 and ssd start with sda

### once it finished copy the files:
sudo raspi-config
this will open the menu, from the menu pick, "Advaince Options" then "Bootloader version" then "latest"

### finally go to "Advaince Options" then "Boot Order" then pick "USB Boot" then go to finish and reboot.
when the device reboot turn it off, remove the sdcard and keep the ssd connected.

power it on and that's it :) done.


