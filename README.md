# luci-app-mosdns

[MosDNS](https://github.com/IrineSistiana/mosdns) is a plug-in DNS forwarder. Users can splicing plug-ins as needed to customize their own DNS processing logic.

## How to build

- Enter in your openwrt dir

- Openwrt official SnapShots

  ```shell
  # remove v2ray-geodata package from feeds (openwrt-22.03 & master)
  rm -rf feeds/packages/net/v2ray-geodata

  git clone https://github.com/sbwml/luci-app-mosdns package/mosdns
  git clone https://github.com/sbwml/v2ray-geodata package/v2ray-geodata
  make menuconfig # choose LUCI -> Applications -> luci-app-mosdns
  make V=s
  ```

- Non-Openwrt official source

  ```shell
  # drop mosdns and v2ray-geodata packages that come with the source
  find ./ | grep Makefile | grep v2ray-geodata | xargs rm -f
  find ./ | grep Makefile | grep mosdns | xargs rm -f

  git clone https://github.com/sbwml/luci-app-mosdns package/mosdns
  git clone https://github.com/sbwml/v2ray-geodata package/v2ray-geodata
  make menuconfig # choose LUCI -> Applications -> luci-app-mosdns
  make V=s
  ```

--------------

## How to install prebuilt packages

- Login OpenWrt terminal (SSH)

- Install `curl` package
  ```shell
  opkg update
  opkg install curl
  ```

- Execute install script (Multi-architecture support)
  ```shell
  sh -c "$(curl -ksS https://raw.githubusercontent.com/sbwml/luci-app-mosdns/v4/install.sh)"
  ```

--------------

![](https://user-images.githubusercontent.com/16485166/206000249-3fdc64ea-cb4d-47f6-8247-c029f54e405e.png)


