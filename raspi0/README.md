# Raspberry Pi Zero W
[OpenWrt Page](https://openwrt.org/toh/raspberry_pi_foundation/raspberry_pi)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/23.05.2/targets/bcm27xx/bcm2708/openwrt-imagebuilder-23.05.2-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-23.05.2-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-23.05.2-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-23.05.2-bcm27xx-bcm2708.Linux-x86_64/{.,}* raspi0 && \
cd raspi0
```

## Make Firmware Image
```
make image PROFILE='rpi' \
PACKAGES='luci luci-proto-relay relayd \
usb-modeswitch kmod-mii kmod-usb-net kmod-usb-net-cdc-ether kmod-usb-net-cdc-mbim kmod-usb-net-cdc-ncm kmod-usb-net-huawei-cdc-ncm  \
kmod-usb-net-qmi-wwan kmod-usb-net-rndis kmod-usb-wdm kmod-usb-net-qmi-wwan kmod-usb-net-asix kmod-usb-net-ipheth  \
usbmuxd libimobiledevice uqmi wwan umbim comgt comgt-ncm kmod-usb-net-rtl8152 \
kmod-usb-serial-option kmod-usb-serial kmod-usb-serial-wwan usbutils \
kmod-usb-storage kmod-usb-storage-uas' \
FILES='files'
```

## Download to local machine
```
rm -rf ~/Downloads/bcm2708 && \
scp -r larissa:/home/bbrietzke/OpenWRT_config/raspi0/bin/targets/bcm27xx/bcm2708 ~/Downloads
```

https://downloads.openwrt.org/releases/23.05.2/targets/bcm27xx/bcm2708/openwrt-23.05.2-bcm27xx-bcm2708-rpi-ext4-factory.img.gz