# Raspberry Pi Zero W
[OpenWrt Page](https://openwrt.org/toh/raspberry_pi_foundation/raspberry_pi)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/22.03.4/targets/bcm27xx/bcm2708/openwrt-imagebuilder-22.03.4-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-22.03.4-bcm27xx-bcm2708.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.4-bcm27xx-bcm2708.Linux-x86_64 rpi0 && \
cd rpi0
```

## Make Firmware Image
```
make image PROFILE='rpi' \
PACKAGES='luci luci-proto-relay relayd kmod-usb-net-asix-ax88179 \
prometheus-node-exporter-lua prometheus-node-exporter-lua-openwrt prometheus-node-exporter-lua-netstat \
prometheus-node-exporter-lua-nat_traffic prometheus-node-exporter-lua-wifi prometheus-node-exporter-lua-wifi_stations \
usb-modeswitch kmod-mii kmod-usb-net kmod-usb-net-cdc-ether kmod-usb-net-cdc-mbim kmod-usb-net-cdc-ncm kmod-usb-net-huawei-cdc-ncm  \
kmod-usb-net-qmi-wwan kmod-usb-net-rndis kmod-usb-wdm kmod-usb-net-qmi-wwan kmod-usb-net-asix kmod-usb-net-asix-ax88179 kmod-usb-net-ipheth  \
usbmuxd libimobiledevice uqmi wwan umbim comgt comgt-ncm \
kmod-usb-serial-option kmod-usb-serial kmod-usb-serial-wwan usbutils'
FILES=''
```

```
rm -rf ~/Downloads/bcm2708 && \
scp -r ubuntu@catnip.lan:/home/ubuntu/openwrt/rpi0/bin/targets/bcm27xx/bcm2708 ~/Downloads
```