### mac OS下操作
* 空白的U盘，要求格式FAT32
* 将当前目录下的EFI文件夹拷贝到U盘根目录下
* 将U盘插入新电脑，开机选择U盘启动
* 进入BIOS-SHELL
* 0x8DC 0x2
* 0x8DC 0x0

## 查看预分配显存
```C
setup_var 0x8DC
```
offset 0x8DC is: 0x01
## 设置64M预分配显存
```C
setup_var 0x8DC 0x2
```
offset 0x8DC is: 0x02

## 查看CFG Lock
```C
setup_var 0x8DC
```
offset 0x5BE is: 0x01
## 设置关闭CFG Lock
```C
setup_var 0x8DC 0x0
```
offset 0x8DC is: 0x00
