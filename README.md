# Redmi-AX3000-fix-TTL
## 红米ax3000修复iptables缺失的修改出口ttl功能
hzyitc大佬制作的[红米ax3000固件](https://github.com/hzyitc/openwrt-redmi-ax3000)还是非常稳定好用的，可惜的是为了兼顾双系统的原因，导致第二分区仅有18mb的可怜容量
也因此大佬制作的固件非常的精简。因为校园网检测出口TTL的原因，在终端使用修改出口TTL的命令´iptables -t mangle -A PREROUTING -j TTL --ttl-set 64´发现报错
