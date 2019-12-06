# EFI-B360m_d2v_OpenCore_dvi_uhd630
OC引导工具 EFI 配置文件

Open Core版本: 0.5.3 详情: [Open Core 最新自动编译版](https://github.com/williambj1/OpenCore-Factory)、[Open Core 官方版](https://github.com/acidanthera/OpenCorePkg/releases)

Clover引导文件请看这里：[Clover引导](https://github.com/Matchas-xiaobin/EFI-B360m_d2v_dvi_uhd630)

# 参考资料
很多教程和系统下载: [黑果小兵的部落阁](https://blog.daliansky.net/)
XJN大佬的OC教程: [使用OpenCore引导黑苹果](https://blog.xjn819.com/?p=543)
黑果小兵的OC教程: [精解OpenCore](https://blog.daliansky.net/OpenCore-BootLoader.html)

# 机器配置
```
CPU: intel i5-8400
主板: GIGABYTE B360m d2v
内存: 16G
显卡: UHD630
声卡: Realtek® ALC887芯片
网卡: Realtek® GbE 网络芯片(10/100/1000 Mbit)
```

# 更新记录
### 2019.12.6
```
1. 更新缓冲帧信息，限制视频端口为2个，解决开机到登陆界面鼠标键盘卡顿的问题。目前还是会有3秒左右小卡顿，已经没啥影响了，可以把另一个你不用的接口在屏蔽一下，应该就完全不卡了;
2. 屏蔽核显的数字音频功能，解决唤醒后重启的问题(不太确定, 暂时测试是没问题.);
3. 机型更换成 Macmini8,1 (所以如果之前用了我的EFI, 更新这个后, 机型会变, 需要重新登录Apple ID);
4. 升级OC版本为 0.5.3 正式版;
5. RTC重命名为ARTC(应该是没啥意义和实际作用, 白苹果强迫症);
```

# 目前进度
```
1. 核显DVI输出，显存1536M ---11月30号更新缓冲帧信息，显存2048M
2. 声卡ID 11 前面板 选 耳机，后面板 选 内置扬声器，未测试麦克风
3. 有线网卡 正常
4. USB 3.0 2.0 正常
   USB这个需要定制，可能在别的同型号电脑上不正常
5. 睡眠正常
6. 唤醒正常 ---12月6日 修复AppleALC导致唤醒重启的问题
7. 关机正常
8. 无花屏现象
```

# 目前碰到问题
```
1. DVI连接显示器的，开机读条到4分之3左右会黑屏大约1~2秒，然后进入用户登录界面。
2. VGA连接显示器的，开机读条到4分之3左右会黑屏大约10~20秒，然后进入用户登录界面。
3. USB定制端口可能会出现问题，原因应该是不同机箱前置面板的USB端口可能不一样，定制USB可解决该问题。
```

# 其他问题
```
1. 插耳机没声音的，记得在音频里选一下耳机，或者内置扬声器。
2. 通过DVI或者VGA输出实测都可以。
3. 不保证一定能用，不会搞，全是在网上找别的大佬的文件后折腾，在自己电脑上是可以正常运行了。
4. 安装镜像是用的 黑果小兵 的二合一镜像，搜索 黑果小兵 就可以找到，里面有很多教程。
5. 没有尝试麦克风是否可用，因为没有麦克风设备。
6. 如果你的USB3.0或者2.0用不了，请自行定制USB3.0，因为有可能会端口不一样。
7. 如果开机鼠标键盘都无法使用，请换插一下其他USB口试试，不要用机箱前面板的USB口。
    如果还是不行，则删除这个文件 OC/kexts/USBPorts.kext;
    并且在配置文件里删掉这个kext。
    然后添加USB通用驱动后，去定制USB驱动。
```
