# Redmi-AX3000-fix-TTL
## 红米ax3000修复iptables缺失的修改出口ttl功能
hzyitc大佬制作的[红米ax3000固件](https://github.com/hzyitc/openwrt-redmi-ax3000)还是非常稳定好用的，可惜的是为了兼顾双系统的原因，导致第二分区仅有18mb的可怜容量
也因此大佬制作的固件非常的精简。因为校园网检测出口TTL的原因，在终端使用修改出口TTL的命令 ``iptables -t mangle -A PREROUTING -j TTL --ttl-set 64``发现报错 ``unknown option "--ttl-set"``
![报错图](https://github.com/tanxiaofx/Redmi-AX3000-fix-TTL/blob/main/image/IMG_0396.jpeg?raw=true)
### 解决方案
1:可以尝试在系统——软件包 中搜索``iptables-mod-ipopt``和``iptables-mod-conntrack-extra``这两个组件，但是软件包大概率会搜索不到这两个组件的依赖"kmod"

2:[下载组件包](https://github.com/tanxiaofx/Redmi-AX3000-fix-TTL/releases/tag/1.0) 来手动安装，非常适合刚配置校园网的无网环境。仅需要在软件包中上传完整这7个文件安装即可，已经排好了顺序。


安装后再使用命令不会出现报错
![效果图](https://github.com/tanxiaofx/Redmi-AX3000-fix-TTL/blob/main/image/IMG_0397.jpeg?raw=true)
