# 系统美化
> 有关系统美化的笔记


# 任务栏
> 任务栏美化可以选用以下软件
## Noctalia
> [noctalia](https://noctalia.dev/)是一个开源的niri或hyprland的任务栏,优点是占用较小
1. 可以用yay安装
```sh
yay -S noctalia-shell-git
```
> ** 注意 **noctalia-shell-git是测试版，下载速度比正式版快所以才给予这条
## dms
> [Danklinux](//danklinux.com)是一个开源的niri或hyprland的任务栏，集成度很高<br>
> ** 注意 **无论哪种方式安装都需要访问到google,所以国内必须要[代理](/home/note#代理有关)才可以正常安装
1. 可以通过官方提供的一键命令
```sh
curl -fsSL https://install.danklinux.com | sh
```
2. 可以直接通过yay安装
```sh
yay -S dms-shell-bin
```

# 主题安装 

## sddm
> sddm主题有很多，推荐一个项目[qlock-main](//github.com/Darkkal44/qylock),它有很多主题，包括星铁之类的游戏
```sh
git clone https://github.com/Darkkal44/qylock.git
cd qylock-main
chmod +x sddm.sh && ./sddm.sh
```

## Grub
> grub主题也有很多，推荐一个项目[Gorgeous-GRUB](//github.com/Jacksaur/Gorgeous-GRUB),它收集了很多好看的grub主题

