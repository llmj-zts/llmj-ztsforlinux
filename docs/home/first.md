# 系统环境
> 这里存放着系统必备的软件
  # 应用市场
  - ## yay
  > yay可以在archlinux上下载用户包:虽然国内比较慢
    1. 将以下archlinux源添加到/etc/pacman.conf末尾
```清华源
[archlinuxcn]
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```
    2. 接下来更新密钥
```sh
pacman -Sy archlinuxcn-keyring
```
    3. 最后安装yay
```sh
pacman -S yay
```
  > 有关导入archlinuxcn源只会在这里讲一遍，之后不会有，没看到算你倒霉

  - ## flatpak
  > 跨平台必装:可惜他装的软件启动很慢
    1. 直接使用pacman安装
```sh
pacman -S flatpak
```
    2. 换源
```sh
flatpak remote-modify flathub --url=https://mirrors.ustc.edu.cn/flathub
```
    3. 各大软件市场gnome-software或discover都支持flatpak

 

  # 下载器
  - ## Motrix
  > [Motrix](//motrix.app)是支持linux且**非常好用**的图形化下载器
      1. 推荐下载[AppImage](https://yhsb.lanzouw.com/ihHt23f5dbra)包
      2. 使用yay安装:在国内通常很慢
```yay
yay -S motrix
```
