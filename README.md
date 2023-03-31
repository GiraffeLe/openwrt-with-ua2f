# openwrt-with-ua2f

## 更新日志：

3.30 添加了[可能遇到的问题及解决方案](https://github.com/GiraffeLe/openwrt-with-ua2f/wiki/%E4%B8%80%E4%BA%9B%E5%8F%AF%E8%83%BD%E5%87%BA%E7%8E%B0%E7%9A%84%E9%97%AE%E9%A2%98%E5%8F%8A%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)

3.20 ①更新了wiki里的后台设置，加了些图文。②上传了斐讯k2p的固件

## 介绍：

此方案是基于openwrt，利用ua2f插件+ttl伪装来实现多设备登录。

经测试可以绕过GiWifi校园网的设备检测。

适合想**省上网费用**（学生的钱也是钱）/**宿舍中智能设备较多**并且**具有计算机知识**的同学。

此方案并**不能破解giwifi(不充钱白嫖)**



-----

此固件使用的是官方源码，基于21.02版本。（因为最新版22.03版本删掉了iptables，会导致配置不成功）

~~仅装了ua2f一个插件，非常简陋（能用就行）~~

出于美观，我又编了一个带argon主题的固件（

---

22年暑假，某高校在未提前通知学生的情况下把宽带拆掉，并且统一使用giwifi（**寄wifi！**）来管理。

giwifi会**限制设备数量**，并且检测到多设备之后会将你的账号**强制下线**，15min之后才能重新登陆。

giwifi的网络质量也是**一言难尽**，相信各位用过giwifi的同学都知道这b网是什么吊样。

**在费用上面**，一个宿舍需要每月支出200元左右（giwifi使用的是一人一号）才能保证上网。而之前仅需支出30元即可满足整个宿舍上网（宿舍里用路由器共用一条宽带）学校和寄wifi赚麻了，只有学生输光光😭

-----

### Todo:

- [X] 使用方法/被检测后的措施

- [ ] 待补充



## 个人体验：

在配置好启动ua2f之后，如果正常的运行的话，一般不会被检测到。在我个人大半年的使用过程中，因非人为因素造成的被检测到然后断网的情况几乎没有。

并且不知道是这个固件的原因还是我们宿舍的校园网设备的原因，从去年到现在大半年几乎没有出现过别人的断网，网卡现象,**网络比较稳定**。经过测速网站测试之后也基本都能**跑满给的最大带宽。**

## 本系列文章大量参考：

 [SunBK201的openwrt编译与防检测部署](https://sunbk201public.notion.site/sunbk201public/OpenWrt-f59ae1a76741486092c27bc24dbadc59)

[校园网路由器多设备伪装指北](https://learningman.top/archives/304) 

[UA2F(github)](https://github.com/Zxilly/UA2F)

[openwrt官网](openwrt.org)

[恩山论坛](https://www.right.com.cn/forum/forum.php)

[红米AC2100刷breed(恩山)](https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=4066963&highlight=%CB%A2breed)

[红米AC2100刷openwrt教程(bilibili)](https://www.bilibili.com/read/cv18237601/)

[L大](https://github.com/coolsnowwolf/lede)

非常感谢这些大佬，在我编译固件的时候给予了不少帮助。

让我免于校园网的低质量的痛苦和省掉了不少不必要的额外上网费用。

## 一些准备：

### 设备：

路由器，网线（最好是两根），电脑，卡针/牙签也行。

### 软件：

#### PC端：

VMare Workstation(虚拟机) [下载链接](https://www.vmware.com/cn/products/workstation-player.html)

XShell(ssh工具，已经有别的ssh可以不下载) [下载链接(家庭/学校免费使用)](https://www.xshell.com/zh/xshell/)

#### 手机端：

juice ssh （谷歌商店）

## 大致步骤：

### 1.确认自己的路由器是否能刷openwrt

①：[openwrt官方固件下载](https://firmware-selector.openwrt.org/?version=22.03.3) 

在这里输入自己的路由器型号，如果能搜到，那就说明可以刷openwrt；如果搜不到，那大概率不能刷。

②：直接百度“xxx（路由器型号）能刷第三方固件吗？”

### 2.给路由器刷breed

[wiki刷breed](https://github.com/GiraffeLe/openwrt-with-ua2f/wiki/%E5%88%B7breed)

### 3.编译固件：（如果用的别人的固件的话可以跳过这一部分）

[wiki编译固件](https://github.com/GiraffeLe/openwrt-with-ua2f/wiki/%E6%9C%AC%E5%9C%B0%E7%BC%96%E8%AF%91%E5%9B%BA%E4%BB%B6)

### 4.后台设置：

 [wiki后台设置](https://github.com/GiraffeLe/openwrt-with-ua2f/wiki/%E5%90%8E%E5%8F%B0%E8%AE%BE%E7%BD%AE)
 
### 5.使用过程中可能遇到的问题及解决方案：

[问题及解决方案](https://github.com/GiraffeLe/openwrt-with-ua2f/wiki/%E4%B8%80%E4%BA%9B%E5%8F%AF%E8%83%BD%E5%87%BA%E7%8E%B0%E7%9A%84%E9%97%AE%E9%A2%98%E5%8F%8A%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)

## 不足：

~~1.因为openwrt是一个linux发行版，所以会被giwifi检测为手机端。如果在**宿舍断电**之后用手机登录giwifi的话，第二天则需要**手动登录**。~~

**解决方案：**

~~①在睡觉之前手动下线自己的账号。~~

②搞一个ups，给路由器单独供电。

2.不能使用多播插件，多播插件会用到mwan3，而ua2f会和mwan插件起**冲突导致ua2f失效**从而会被giwifi检测到踢下线。

