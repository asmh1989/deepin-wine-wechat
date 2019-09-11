# 自用 deepin-wine-wechat 2.6.8.65

> 参考https://github.com/wszqkzqk/deepin-wine-ubuntu

> 在`Kubuntu 19.04`上测试, 支持双屏

## 使用

* 运行`./install.sh` 或者 `./KDE-install.sh` 即可

## 我遇到的问题

* 刚启动后输入中文是方块, 不要紧张, 可以切换下几个输入框后输入后, 会正常, 然后就一直正常输入
* kde 下任务栏图标右键失效的问题, 有个解决办法是登录前关闭特效`Shift+Alt+F12`, 成功后再次切换, 然后就可以正常操作了, 就是图标区域背景变黑, 但不影响使用


## UPDATE:  修复中文输入方块问题

```
下载字体: https://github.com/owent-utils/font/blob/master/%E5%BE%AE%E8%BD%AF%E9%9B%85%E9%BB%91/MSYH.TTC

#1.添加字体
cp msyh.ttc ~/.deepinwine/Deepin-WeChat/drive_c/windows/Fonts

#2.修改系统注册表
gedit ~/.deepinwine/Deepin-WeChat/system.reg
#修改以下两行
"MS Shell Dlg"="msyh"
"MS Shell Dlg 2"="msyh"

#3.字体注册
gedit msyh_config.reg
#内容添加
REGEDIT4
[HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink]
"Lucida Sans Unicode"="msyh.ttc"
"Microsoft Sans Serif"="msyh.ttc"
"MS Sans Serif"="msyh.ttc"
"Tahoma"="msyh.ttc"
"Tahoma Bold"="msyhbd.ttc"
"msyh"="msyh.ttc"
"Arial"="msyh.ttc"
"Arial Black"="msyh.ttc"
#注册
WINEPREFIX=~/.deepinwine/Deepin-WeChat deepin-wine regedit msyh_config.reg
```
