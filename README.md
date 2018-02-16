## dnsmasq-regex for OpenWrt/LEDE

Thanks to [@aa65535](https://github.com/aa65535/openwrt-dnsmasq)

This is the [dnsmasq-regex](https://github.com/lixingcong/dnsmasq-regex) Makefile for OpenWrt 15.05(or higher) or LEDE.

## Compile

克隆仓库，检出分支

### OpenWrt

	# 以 OpenWrt 15.05 的ar71xx 平台为例
	tar xjf OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2.tar.bz2
	cd OpenWrt-SDK-ar71xx-*
	
	# 克隆openwrt分支
	git clone -b openwrt https://github.com/lixingcong/dnsmasq-regex-openwrt package/dnsmasq

### LEDE

	# 以 LEDE 17.01.4 的ar71xx 平台为例
	tar xjf lede-sdk-17.01.4-ar71xx-generic_gcc-5.4.0_musl-1.1.16.Linux-x86_64.tar.xz
	cd lede-sdk-17.01.4-*
	
	# 克隆lede分支
	git clone -b lede https://github.com/lixingcong/dnsmasq-regex-openwrt package/dnsmasq

编译

	# 选择要编译的dnsmasq，按M键选中
	# Base system -> dnsmasq 
	make menuconfig
	
	# 开始编译
	make package/dnsmasq/compile V=99
	
	# 找到ipk包
	find bin | grep dnsmasq


## Regex domains config examples

[conf-files-example](https://github.com/lixingcong/dnsmasq-regex-openwrt/tree/master/conf-files-example)