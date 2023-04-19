# Raspberry Pi Zero W
[OpenWrt Page](https://openwrt.org/toh/raspberry_pi_foundation/raspberry_pi)

## Acquire OpenWRT Firmware
```
https://downloads.openwrt.org/releases/22.03.4/targets/bcm27xx/bcm2708/openwrt-imagebuilder-22.03.4-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-22.03.4-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.4-bcm27xx-bcm2708.Linux-x86_64 rpi0 && \
cd rpi0
```

## Make Firmware Image
```
make image PROFILE='rpi-0' \
PACKAGES='luci luci-proto-relay relayd kmod-usb-net-asix-ax88179'
FILES=''
```
