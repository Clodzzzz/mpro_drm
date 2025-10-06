# MPRO DRM

A simple DRM driver for VoCore MPRO screen.
Updated to allow multiple screens on Pi.
This has only been tested with Open Marine version of Pi on a 5 and up to 3 vocore screens.

#Usage

sudo apt install raspberrypi-kernel-headers build-essential -y
git config --global http.sslVerify false
git clone https://github.com/clodzzzz/mpro_drm.git
cd mpro_drm
make
sudo mkdir -p /lib/modules/$(uname -r)/kernel/drivers/mpro/
sudo cp mpro.ko /lib/modules/$(uname -r)/kernel/drivers/mpro/
sudo insmod mpro.ko 	# This loads it	
sudo depmod -a		# This makes it permanant

sudo raspi-config
Enable VNC
Open VNC and then make screens active and rotate them

