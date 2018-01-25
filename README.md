## dnsmasq-regex for OpenWrt

Thanks to [@aa65535](https://github.com/aa65535/openwrt-dnsmasq)

This is the [dnsmasq-regex](https://github.com/lixingcong/dnsmasq-regex) Makefile for LEDE.

## Compile

	# 以 ar71xx 平台为例
	tar xjf OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2.tar.bz2
	cd OpenWrt-SDK-ar71xx-*
	# 下载 Patch & Makefile
	git clone https://github.com/lixingcong/dnsmasq-regex-openwrt.git package/dnsmasq
	# 选择要编译的包
	# Base system -> dnsmasq 
	make menuconfig
	# 开始编译
	make package/dnsmasq/compile V=99 
	# 找到包
	cd bin/ar71xx/packages/base && ls -l

## Config examples

[conf-files-example](https://github.com/lixingcong/dnsmasq-regex-openwrt/tree/master/conf-files-example)