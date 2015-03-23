XXXXXLinux版项目安装
=======================

操作系统  CentOS-6.4-x86-64-bin-DVD1.iso
开发周期        2014-07-07 至 2014-08-30
开发人员               xxx@xxx.com.cn


历史记录
--------
* 2014-09-17 10:51  更新
* 2014-08-27 20:19  更新,更新raid1安装脚本, 只要安装一个脚本即可
* 2014-08-25 20:24  发布

软件路径
--------
* 操作系统
  - 下载位置: 172.16.110.65/dev2/iso/CentOS-6.4-x86_64-bin-DVD1.iso
* 软件
  - 下载位置: 172.16.110.65/dev2/tmp/xxx/xxxx-linux/
    + xxxxlinux-raid1-install-XXX.run 在raid1中安装的软件, 直接执行安装
    + xxxxlinux-ssd-install-XXX.run   在SSD  中安装的软件, 直接执行安装

安装raid1上的操作系统和软件
---------------------------
* 安装操作系统
  - 分区信息如下:  
    disk      mount   type   size  
    /dev/sda1 /boot   ext4   500M   
    /dev/sda2 /       ext4   10G   
    /dev/sda3         swap   2048M   
    /dev/sda4 /data   ext4   剩余空间  
  - 安装类型选择 Basic Server, 自定义的安装包选择如下:  
    + 开发工具
    + 服务器平台开发
    + 桌面
    + 中文支持
* 安装软件
  - 执行xxxxlinux-raid1-install-XXX.run 

Install ssd os
--------------
* 安装操作系统
  **安装前拔掉raid1系统的两块磁盘,如果有其他系统的磁盘也拔掉, 确保只有ssd盘接入.**  
  - 安装系统时不能接raid1，使用4pin供电,即要识别ssd盘为/dev/sda
  - 分区 /boot ext4 500M, swap 2048M, / ext4 剩余空间
  - 分区信息如下:  
    disk      mount   type   size  
    /dev/sda1 /boot   ext4   500M   
    /dev/sda2         swap   2048M   
    /dev/sda3 /       ext4   剩余空间  
  - 安装类型选择 Basic Server, 自定义的安装包默认即可
  - 执行xxxxlinux-ssd-install.run

* 安装软件
  - 执行xxxxlinux-ssd-install-XXX.run 

* 执行备份操作
  执行备份脚本ubackup -t 0, 该脚本会对raid1完成如下操作:
  - 1.使用dd备份mbr到/root/backup/mbr.disk
  - 2.使用dd备份/boot到/root/backup/boot.disk
  - 3.使用dd备份/到/root/backup/root.disk
  - 4.使用tar备份/data到/root/backup/data.tar.gz

test
----
* 常规测试
  - 测试系统信息
  - 测试实时监控信息
  - 测试消息功能

* 备份还原测试
  - 测试备份
  - 测试还原
