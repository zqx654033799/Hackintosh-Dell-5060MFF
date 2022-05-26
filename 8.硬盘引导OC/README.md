
## 硬盘引导OC
* 当前目录 PE.zip 解压后得到 PE.cdr
* 打开 PE.cdr
* 操作步骤3相同
```C
diskutil eraseDisk FAT32 "WINPE" MBR disk2
cp -rp /Volumes/win10pe/* /Volumes/WINPE/
```
* 插入U盘，设置U盘第一启动项，进入WinPE
* 将EFI文件夹下的OC目录 拷贝到硬盘EFI分区下EFI文件夹下
* BIOS 添加OC引导即可
