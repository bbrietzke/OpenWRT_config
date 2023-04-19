# GLiNet MT300-N v2
[OpenWRT Page](https://openwrt.org/toh/gl.inet/gl-mt300n_v2)
[GLiNet Firmware Upgrades](https://dl.gl-inet.com/?model=mt300n-v2)

## Acquire OpenWRT Firmware
```
wget https://downloads.openwrt.org/releases/22.03.3/targets/ramips/mt76x8/openwrt-imagebuilder-22.03.3-ramips-mt76x8.Linux-x86_64.tar.xz
tar -Jxf openwrt-imagebuilder-22.03.3-ramips-mt76x8.Linux-x86_64.tar.xz && \
mv openwrt-imagebuilder-22.03.3-ramips-mt76x8.Linux-x86_64 mt76x8 && \
cd mt76x8
```

## Make Firmware Image
```
make image PROFILE='glinet_gl-mt300n-v2' \
PACKAGES='luci'
FILES=''
```

## Copy image for Distribution
```
export SERVERNAME=basil.lan && \
rm -rf ~/Downloads/mt76x8 && \
scp -r ubuntu@$SERVERNAME:/home/ubuntu/openwrt/mt76x8/bin/targets/ramips/mt76x8 ~/Downloads
```