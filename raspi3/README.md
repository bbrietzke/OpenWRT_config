# Raspberry Pi 3
[OpenWrt Page](https://downloads.openwrt.org/releases/22.03.5/targets/bcm27xx/bcm2710/)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/22.03.5/targets/bcm27xx/bcm2710/openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64 raspi3  && \
cd raspi3
```

## Make Firmware Image
```
make image PROFILE='rpi-3' \
PACKAGES='luci-proto-relay relayd luci \
kmod-usb-net-rndis kmod-usb-net-cdc-ncm kmod-usb-net-huawei-cdc-ncm kmod-usb-net-cdc-eem \
kmod-usb-net-cdc-ether kmod-usb-net-cdc-subset kmod-nls-base kmod-usb-core kmod-usb-net kmod-usb-net-cdc-ether kmod-usb2 \
kmod-usb-net-ipheth usbmuxd libimobiledevice usbutils \
prometheus-node-exporter-lua prometheus-node-exporter-lua-openwrt prometheus-node-exporter-lua-netstat \
prometheus-node-exporter-lua-nat_traffic prometheus-node-exporter-lua-wifi prometheus-node-exporter-lua-wifi_stations \
mosquitto-nossl mosquitto-client-nossl luci-app-mosquitto \
redis-server redis-cli redis-utils \
squid luci-app-squid squid-mod-cachemgr' \
FILES='config'
```

## Make Asterisk PBX Image
```
make image PROFILE='rpi-3' \
PACKAGES='luci \
asterisk asterisk-pjsip asterisk-bridge-simple asterisk-codec-alaw asterisk-codec-ulaw asterisk-res-rtp-asterisk \
asterisk-app-sms asterisk-res-ari' \
FILES='config'
```

```
rm -rf ~/Downloads/bcm2710 && \
scp -r bbrietzke@titan:/home/bbrietzke/openwrt/raspi3/bin/targets/bcm27xx/bcm2710 ~/Downloads
```
