# Raspberry Pi 3
[OpenWrt Page](https://downloads.openwrt.org/releases/22.03.5/targets/bcm27xx/bcm2710/)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/22.03.5/targets/bcm27xx/bcm2710/openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.5-bcm27xx-bcm2710.Linux-x86_64/{.,}* raspi3  && \
cd raspi3
```

## Make Firmware Image
```
make image PROFILE='rpi-3' \
PACKAGES='luci luci-proto-relay relayd' \
FILES='files'
```

```
rm -rf ~/Downloads/bcm2710 && \
scp -r bbrietzke@titan:/home/bbrietzke/openwrt/raspi3/bin/targets/bcm27xx/bcm2710 ~/Downloads
```
