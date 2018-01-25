Dnsmasq Config
===

此配置需要搭配 `ss-tunnel` (端口5353)使用  
dnsmasq 会自动载入 `/etc/dnsmasq.d` 中的配置文件  

 文件名               | 简介
----------------------|-------------------------------
`ads_filter.conf` | 广告屏蔽列表，也可以自定义域名 IP（等价于hosts效果）
`foregin_domains.conf`  | DNS查询使用 `ss-tunnel` 的域名, 目前只有被google,fb等域名
`iplist_black.conf` | 忽略返回的IP地址，需要根据ISP返回的具体结果自己定义，不保证有效

**PS:** iplist_black.conf来自ChinaDNS项目中的chinadns_iplist.txt，也可以使用这个[python小脚本](https://gist.github.com/lixingcong/c6b5e831fa250a77219befa1261b7ca3)生成虚假DNS回复的黑名单，使用脚本时候要注意部份地区的虚假DNS答复可能是正确的镜外ip但不对应查询请求，比如解析google.com时候ISP会返回facebook的IP，需要自己判断。
