# Nitro5-AN515-58-WebCam-Module

```sh
sudo apt update
sudo apt upgrade
sudo apt install build-essential -y 
cd ~  # change to your home directory
apt-get source linux-modules-extra-$(uname -r)
cd ~/linux-*/drivers/media/usb/uvc 
mv uvc_driver.c uvc_driver.old
```

Download my version for AN515-58 **Kernel 6.2**
```sh
wget https://raw.githubusercontent.com/rexionmars/Nitro5-AN515-58-WebCam-Module/master/uvc_driver_kernel_6.2/uvc_driver.c
```
Download my version for AN515-58 **Kernel 6.5**
```sh
wget https://raw.githubusercontent.com/rexionmars/Nitro5-AN515-58-WebCam-Module/master/uvc_driver_kernel_6.5/uvc_driver.c
```
Compile new module

```sh
make -j4 -C /lib/modules/$(uname -r)/build M=$(pwd) modules  
sudo cp uvcvideo.ko /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc/ 
```
Finaly
```sh
sudo reboot
```
