# Vesc-bldc 环境到编译再到下载
By Gkbytes

这是一个VESC DC/BLDC/FOC 控制器的源码：



[https://github.com/vedderb/bldc/](https://github.com/vedderb/bldc/)



官网：



[https://vesc-project.com/](https://vesc-project.com/)



本杰明 韦德私人网站：



[http://vedder.se/](http://vedder.se/)




## Ubuntu环境准备：
1. 安装gcc-arm-embedded 工具链
```c
sudo add-apt-repository ppa:team-gcc-arm-embedded/ppa
sudo apt update
sudo apt install gcc-arm-embedded
```
2.  stlink v2
```c
wget vedder.se/Temp/49-stlinkv2.rules
sudo mv 49-stlinkv2.rules /etc/udev/rules.d/
sudo udevadm trigger
```

## 编译：
烧录固件前需要刷[bootloader](https://github.com/vedderb/bldc-bootloader)
* 编译
```c
git clone https://github.com/vedderb/bldc.git vesc_firmware
cd vesc_firmware
make
```

* 下载
```c
make upload
```
