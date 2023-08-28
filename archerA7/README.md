# Raspberry Pi Zero W
[OpenWrt Page](https://openwrt.org/toh/tp-link/archer_a7_v5)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/22.03.5/targets/ath79/generic/openwrt-imagebuilder-22.03.5-ath79-generic.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-22.03.5-ath79-generic.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-22.03.5-ath79-generic.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.5-ath79-generic.Linux-x86_64 archerA7 && \
cd archerA7
```

## Make Firmware Image
```
make image PROFILE="tplink_archer-a7-v5"  \
PACKAGES="luci-proto-relay relayd luci \
kmod-usb-net-rndis kmod-usb-net-cdc-ncm kmod-usb-net-huawei-cdc-ncm kmod-usb-net-cdc-eem \
kmod-usb-net-cdc-ether kmod-usb-net-cdc-subset kmod-nls-base kmod-usb-core \
kmod-usb-net kmod-usb-net-cdc-ether kmod-usb2 \
kmod-usb-net-ipheth usbmuxd libimobiledevice usbutils \
prometheus-node-exporter-lua prometheus-node-exporter-lua-openwrt prometheus-node-exporter-lua-netstat \
prometheus-node-exporter-lua-nat_traffic prometheus-node-exporter-lua-wifi prometheus-node-exporter-lua-wifi_stations \
adblock luci-app-adblock"
FILES="files"
```

```
rm -rf ~/Downloads/generic && \
scp -r bbrietzke@titan.local:/home/bbrietzke/openwrt/archerA7/bin/targets/ath79/generic ~/Downloads
