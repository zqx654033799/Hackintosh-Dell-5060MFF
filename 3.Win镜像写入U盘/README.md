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
* regedit-HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SecurityHealthService\Start-3改4
#### 关闭Windows自动更新
* services.msc-Windows Update-常规 启动类型改为“禁用” / 恢复 失败操作改为“无操作”
* gpedit.msc-计算机配置-管理模版-Windows组件-Windows更新-配置自动更新设置禁用 / 删除使用所有Windows更新功能的访问权限设置启用
* taskschd.msc-任务计划程序库-Microsoft-Windows-WindowsUpdate-项目全部设置禁用
* regedit-HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\UsoSvc\Start-2改4 / FailureActions修改二进制数据 将“0010”、“0018”行的左起第5个数值 “01”改为“00”
```C
00000000 xx xx xx xx xx xx xx xx
00000008 xx xx xx xx 01 xx xx xx
00000010 xx xx xx xx 01 xx xx xx
00000018 xx xx xx xx xx xx xx xx
00000020 xx xx xx xx xx xx xx xx
00000028 xx xx xx xx xx xx xx xx
```
