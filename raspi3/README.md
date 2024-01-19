# Raspberry Pi 3
[OpenWrt Page](https://downloads.openwrt.org/releases/23.05.2/targets/bcm27xx/bcm2710/)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/23.05.2/targets/bcm27xx/bcm2710/openwrt-imagebuilder-23.05.2-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
tar -Jxf openwrt-imagebuilder-23.05.2-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-23.05.2-bcm27xx-bcm2710.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-23.05.2-bcm27xx-bcm2710.Linux-x86_64/{.,}* raspi3  && \
cd raspi3
```

## Make Firmware Image for Router
```
make image PROFILE='rpi-3' \
PACKAGES='luci luci-proto-relay relayd ' \ 
'memcached haproxy mosquitto-nossl' \
FILES='files'
```

## Default Firmware
```
make image PROFILE='rpi-3' \
PACKAGES='luci luci-proto-relay relayd' \
FILES='files'
```

```
rm -rf ~/Downloads/bcm2710 && \
scp -r bbrietzke@10.0.0.242:/home/bbrietzke/OpenWRT_config/raspi3/bin/targets/bcm27xx/bcm2710 ~/Downloads
```
