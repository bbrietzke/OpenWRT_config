# NanoPi NEO 3
[OpenWrt Page](https://openwrt.org/toh/hwdata/friendlyarm/friendlyarm_nanopi_neo)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/22.03.5/targets/sunxi/cortexa7/openwrt-imagebuilder-22.03.5-sunxi-cortexa7.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-22.03.5-sunxi-cortexa7.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-22.03.5-sunxi-cortexa7.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.5-sunxi-cortexa7.Linux-x86_64 sunxi  && \
cd sunxi
```

## Make Firmware Image
```
make image PROFILE='friendlyarm_nanopi-neo' \
PACKAGES='luci \
' \
FILES='config'
```

## Make Asterisk PBX Image
```
make image PROFILE='friendlyarm_nanopi-neo' \
PACKAGES='luci \
asterisk asterisk-pjsip asterisk-bridge-simple asterisk-codec-alaw asterisk-codec-ulaw asterisk-res-rtp-asterisk \
asterisk-app-sms asterisk-res-ari' \
FILES='config'
```

```
rm -rf ~/Downloads/bcm2710 && \
scp -r bbrietzke@titan:/home/bbrietzke/openwrt/raspi3/bin/targets/bcm27xx/bcm2710 ~/Downloads
```
