# Raspberry Pi Zero W
[OpenWrt Page](https://openwrt.org/toh/tp-link/archer_a7_v5)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/23.05.2/targets/ath79/generic/openwrt-imagebuilder-23.05.2-ath79-generic.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-23.05.2-ath79-generic.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-23.05.2-ath79-generic.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-23.05.2-ath79-generic.Linux-x86_64/{.,}* archerA7 && \
cd archerA7
```

## Make Firmware Image
```
make image PROFILE="tplink_archer-a7-v5"  \
PACKAGES="luci-proto-relay relayd luci" \
FILES="files"
```

```
rm -rf ~/Downloads/generic && \
scp -r bbrietzke@titan.local:/home/bbrietzke/openwrt/archerA7/bin/targets/ath79/generic ~/Downloads
