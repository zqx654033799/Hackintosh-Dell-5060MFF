### mac OS下操作
## 插入U盘
## 打开终端
输入：
```C
diskutil list
```
可以看到电脑中所有的磁盘，其中包含U盘
```C
/dev/disk2 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:          FDisk_partition_scheme                  *64.1 GB     disk2
   1:                 DOS_FAT_32 ⁨lash⁩                   64.1 GB     disk2s1
```
## 格式化U盘
U盘（disk2），需要格式化为FAT32格式

输入
```C
diskutil eraseDisk FAT32 "WIN10" MBR disk2
```
这里的“WIN10”是格式化后的U盘名称
## 打开ISO镜像
打开切割后的镜像

输入
```C
cp -rp /Volumes/镜像打开后的名字/* /Volumes/WIN10/
```
耗时比较长，完成后即可以插入新电脑进行Win系统安装了
</br>
</br>

### 自用 
#### 关闭Windows安全中心自动启动
* 任务管理器-启动- Windows security notification icon 启动禁用
* gpedit.msc-计算机配置-管理模版-Windows组件-Windows Defender 防病毒程序-关闭Windows Defender 防病毒程序
* regedit-HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SecurityHealthService-Start-3改4
