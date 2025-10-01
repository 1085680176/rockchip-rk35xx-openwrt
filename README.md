# rockchip-rk35xx-openwrt

![Status-Overview-system](https://github.com/1085680176/rockchip-rk35xx-openwrt/blob/main/Status-Overview-system.png)

##  **OEC/OECT专用**

1.基于[OpenWrt](https://openwrt.org/)、[LEDE](https://github.com/coolsnowwolf/lede)、[ophub](https://github.com/ophub/amlogic-s9xxx-openwrt)的源码云编译而成；

2.编译配置文件[config](https://github.com/1085680176/rockchip-rk35xx-openwrt/blob/main/config/lede-master/config)在[LEDE](https://github.com/coolsnowwolf/lede)的基础上进行了自定义简化；

3.云编译流程文件[workflow file](https://github.com/1085680176/rockchip-rk35xx-openwrt/blob/main/.github/workflows/build-openwrt-system-image.yml)在[ophub](https://github.com/ophub/amlogic-s9xxx-openwrt)的基础上进行了个性化删减；

4.在此感谢[LEDE](https://github.com/coolsnowwolf/lede)、[ophub](https://github.com/ophub/amlogic-s9xxx-openwrt)及其他各位大佬的分享。

##  **编译配置文件[config](https://github.com/1085680176/rockchip-rk35xx-openwrt/blob/main/config/lede-master/config)选择**

1.target选择rockchip_armv8而不是armsr_armv8，理由是选择armsr_armv8在“状态－概览”不显示CPU温度，而选择rockchip_armv8可以显示CPU温度；

2.删除了nftables相关内容,仅保留iptables，解决防火墙iptables与nftables冲突问题；

3.luci-app个性化调整，详见luci-app插件清单。

##  **附  luci-app插件清单**

1.必备

luci-app-firewall   # 防火墙和端口转发,必备

luci-app-opkg        #软件包，必备

2.自选

luci-app-adguardhome #广告屏蔽 

luci-app-arpbind    # IP/MAC 绑定 

luci-app-ddns   # 动态域名解析

luci-app-diskman   # 磁盘管理

luci-app-ramfree   # 释放内存

luci-app-samba4  # 网络共享（samba）

luci-app-smartdns  # SmartDNS 服务 

luci-app-syncthing  # Syncthing 同步 

luci-app-ttyd        #ttyd终端 

luci-app-turboacc    #Turbo ACC 网络加速

Enable BBR CCA      #BBR拥塞控制算法(CCA)
