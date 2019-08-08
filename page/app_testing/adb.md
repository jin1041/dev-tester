# 常用的 adb 及 aapt 命令

## adb

***Q*：adb命令是什么？**

***A*：adb 是安卓调试桥，用于电脑端与模拟器或真实设备交互。**

------

#### 常用adb命令

**adb -s <seriaNum> command**   *指定相应的seriaNum号的设备去执行adb 命令*

**adb devices**	*获取连接状态*

- **device**  *已经连上*
- **offline**   *未连接成功或者无响应*
- **no device**  *没有设备/模拟器连接*
- **unauthorized**  *手机没有信任*

**adb start-server**	*启动 adb 服务*

**adb kill-server**	*停止 adb 服务*

**adb version**	*查看 adb 版本*

**adb shell**	*进入 adb 命令行*

**adb connect	<device-ip>**	*通过 ip 地址连接设备*

**adb install xxx.apk**	*安装apk*

**adb install -r xxx.apk**	*覆盖安装apk*

**adb uninstall [-k] <packageName>** *卸载应用，-k 保留数据和缓存*

**adb logcat | grep xxx**	*查看端上日志*

**adb logcat -c**	*清空日志*

**adb logcat -v time \*:W**	*查看warning日志，并且输出时间戳*

**adb shell getprop**	*获取系统属性*

**adb shell getprop ro.product.model**	*查看设备型号* 

**adb shell getprop ro.build.version.release**	 *查看安卓系统版本*

**adb shell wm size**	*查看屏幕分辨率*

**adb shell; su; cat /data/misc/wifi/\*.conf**	*查看连过的wifi密码*

**adb shell ps**	*查看进程*

**adb kill 'pid'**	*杀死进程*

**adb reboot**	*重启手机*

------

#### pm 命令

**adb shell pm list packages**	*查看所有的应用程序*

**adb shell pm list packages -s**	*只显示系统应用程序*

**adb shell pm list packages -3**	*只显示第三方应用程序*

**adb shell pm clear <packageName>**	*清楚应用程序缓存数据*

------

#### am 命令

**adb shell dumpsys activity activites | [findstr|grep] mFocusedActivity**	*查看前台控件*

**adb shell am start -n activityName**	*调起一个activity*

**adb shell am force-stop <packageName>**	*强制停止应用*

**adb shell am start -d scheme**	*adb启动一个页面*

------

#### 文件管理

**adb pull <设备里的文件路径> [电脑的文件路径]**	*复制文件到电脑*

**adb push <电脑里的文件路径> [设备里的目录]**	*复制文件到设备*

------

#### 按键操作

**adb shell input keyevent <eventNum>**	*执行按键操作*

**adb shell screencap -p /sdcard/sc.png**	*屏*幕截屏，-p 表示以png格式输出

**adb shell screenrecord	/sdcard/filename.mp4**	*屏幕录制*

## aapt