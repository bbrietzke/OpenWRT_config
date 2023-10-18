# GLiNet MT300-N v2
[OpenWRT Page](https://openwrt.org/toh/gl.inet/gl-mt300n_v2)
[GLiNet Firmware Upgrades](https://dl.gl-inet.com/?model=mt300n-v2)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/23.05.0/targets/ramips/mt76x8/openwrt-imagebuilder-23.05.0-ramips-mt76x8.Linux-x86_64.tar.xz
tar -Jxf openwrt-imagebuilder-23.05.0-ramips-mt76x8.Linux-x86_64.tar.xz && \
rm openwrt-imagebuilder-23.05.0-ramips-mt76x8.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-23.05.0-ramips-mt76x8.Linux-x86_64 mt76x8 && \
cd mt76x8
```

## Empty Firmware Image
```
make image PROFILE='glinet_gl-mt300n-v2' \
PACKAGES='luci'
FILES=''
```

## Wireless Bridge Image
```
scp -r glinet_gl-mt300n-v2/config_bridge/ bbrietzke@titan.lan:/home/bbrietzke/openwrt/mt76x8/config
```
```
make image PROFILE='glinet_gl-mt300n-v2' \
PACKAGES='luci \
prometheus-node-exporter-lua prometheus-node-exporter-lua-openwrt \
prometheus-node-exporter-lua-netstat prometheus-node-exporter-lua-nat_traffic \
prometheus-node-exporter-lua-wifi prometheus-node-exporter-lua-wifi_stations \
luci-proto-relay relayd '
FILES='config'
```

## Copy image for Distribution
```
rm -rf ~/Downloads/mt76x8 && \
scp -r bbrietzke@titan.lan:/home/bbrietzke/openwrt/mt76x8/bin/targets/ramips/mt76x8 ~/Downloads
```


