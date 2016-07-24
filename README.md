Dnsmasq for OpenWrt
===

简介
---

 本项目是 [dnsmasq][1] 在 OpenWrt 上的移植与功能增强  
 当前版本: 2.75 


dnsmasq从2.73版本开始具有以下功能
---

 - `--ignore-address` 选项, 忽略指定的 IP, 过滤虚假DNS答复  
 - `--min-cache-ttl` 选项, 可设置 DNS缓存最小有效期 

必须赞一下上面这两个功能的提交者是[@aa65535](https://github.com/aa65535/openwrt-dnsmasq) ，他深深体会到GFW所害的广大中国网友无法获得纯净dns之苦恼，在v2ex发过的帖子[《dnsmasq: 新添加一个 --ignore-address 选项》](https://www.v2ex.com/t/157952)讲述如何commit给dnsmasq开发者的，勇气可嘉。

编译
---

 - 从 OpenWrt 的 [SDK][S] 编译  

   ```bash
   # 以 ar71xx 平台为例
   tar xjf OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2.tar.bz2
   cd OpenWrt-SDK-ar71xx-*
   # 下载 Patch & Makefile
   git clone https://github.com/lixingcong/openwrt-dnsmasq.git package/dnsmasq
   # 选择要编译的包 （实际上可以选择full版，更强大，但是体积大）
   # Base system -> dnsmasq 
   make menuconfig
   # 开始编译
   make package/dnsmasq/compile V=99 
   # 找到包
   cd bin/ar71xx/packages/base && ls -l
   ```

配置
---

 - [默认配置文件][4]

 - [与 ss-tunnel 搭配][8]

----------

 Name                     | Description
 -------------------------|-----------------------------------
 [openwrt-chinadns][5]    | ChinaDNS-C for OpenWrt
 [openwrt-shadowsocks][7] | Shadowsocks-libev for OpenWrt
 [openwrt-redsocks2][R]   | RedSocks2 for OpenWrt
 [openwrt-shadowvpn][6]   | ShadowVPN for OpenWrt
 [openwrt-dist-luci][L]   | LuCI Applications for OpenWrt-dist


  [1]: http://www.thekelleys.org.uk/dnsmasq/doc.html
  [3]: https://sourceforge.net/projects/openwrt-dist/files/dnsmasq/
  [4]: https://github.com/lixingcong/dnsmasq-openwrt/blob/master/files/dnsmasq.conf
  [5]: https://github.com/aa65535/openwrt-chinadns
  [6]: https://github.com/aa65535/openwrt-shadowvpn
  [7]: https://github.com/shadowsocks/openwrt-shadowsocks
  [8]: https://github.com/lixingcong/dnsmasq-openwrt/tree/master/etc
  [R]: https://github.com/aa65535/openwrt-redsocks2
  [S]: http://wiki.openwrt.org/doc/howto/obtain.firmware.sdk
  [L]: https://github.com/aa65535/openwrt-dist-luci
