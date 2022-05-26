### mac OS下操作
## 挂载U盘-EFI分区
* OpenCore Configurator.zip 解压后得到 OpenCore Configurator app
* 打开OpenCore Configurator app，工具-挂载EFI
* 打开EFI分区，将当前目录下的EFI文件夹拷贝到分区根目录
* 须替换三码 EFI/OC/config.plist - PlatformInfo-Generic-MLB/SystemSerialNumber/SystemUUID
* 完成后，将U盘 插入新电脑，选择U盘启动
* 引导选择Install macOS Big Sur，完成安装
</br>
</br>

### 自用 
#### MacOS下禁止开机自动挂载Windows分区
* 打开磁盘管理
* 找到windows分区
* 鼠标右键-显示简介
* 找到 文件系统UUID：561E38E8-FC6A-4DA8-89FD-86EB43DF3221
* 打开终端，输入
```C
sudo vi /etc/fstab
UUID=561E38E8-FC6A-4DA8-89FD-86EB43DF3221 none ntfs noauto 0 0
```
