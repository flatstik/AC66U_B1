Experimental OpenWrt snapshot for ASUS bcm53xx routers with Broadcom 802.11ac Wi-Fi, using the out-of-tree **b43-next** driver ([aleferri/b43-next](https://github.com/aleferri/b43-next) 625d9063). Pre-release: for testing, not for production.

Built by GitHub Actions from branch [`b43-next-all`](https://github.com/flatstik/AC66U_B1/tree/b43-next-all) at @SHA@: OpenWrt main with openwrt/openwrt#26717, #26718, #26719 and the router names of #26734, #26853, #26879. `config.buildinfo` and `feeds.buildinfo` reproduce the build.

## Images

| Image | Routers |
|---|---|
| `...-asus_rt-ac56u-squashfs.trx` | RT-AC56U, RT-AC56R |
| `...-asus_rt-ac68u-squashfs.trx` | RT-AC68U, RT-AC66U B1, RT-AC68W, RT-AC68P |

`...-initramfs.trx` are RAM-only images for testing. The Wi-Fi firmware (784.2) is in the images.

## Installation

- From OpenWrt: `sysupgrade -n openwrt-...-squashfs.trx`
- From DD-WRT: `mtd -r write openwrt-...-squashfs.trx linux`

LAN address is 192.168.1.1, Wi-Fi is off until enabled in LuCI or `/etc/config/wireless`. If the WAN side also uses 192.168.1.0/24, connect only a LAN port first and change the LAN address.

## Known issues

- RT-AC56U 2.4 GHz (BCM43217): uploads from two-stream clients on HT40 stall (aleferri/b43-next#54); use HT20 there.
