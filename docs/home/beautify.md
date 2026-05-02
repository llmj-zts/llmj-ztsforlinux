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
1. 可以通过官方提供的一键命令,但是这可能需要代理
```sh
curl -fsSL https://install.danklinux.com | sh
```
2. 现在已经可以使用pacman安装了
```sh
pacman -S dms-shell
```
> ** 注意 **如果你是niri请注意在选项中选择niri,不然会自动安装hyprland

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


# niri效果
## 模糊效果
> 我有生之年看到niri出[blur](https://niri-wm.github.io/niri/Window-Effects.html)了！！！<br>
> 以下是我的示例，可以把它加入到~/.config/niri/config.kdl的尾部
```sh
window-rule {
    opacity 0.8
    background-effect {
        blur true
	xray true
	noise 0.05
	saturation 1.5
    }
}
```

## 动态壁纸
> //github.com/GhostNaN/mpvpaper很明显诸如[mpvpaper](//github.com/GhostNaN/mpvpaper)其实也不算好用，这里给出一个网上的方案<br>
> 将视频转化为webp格式再用[swww](//github.com/LGFae/swww)等播放,这里给出一个ffmpeg的示例
```sh
ffmpeg -i input.mp4 -quality 100 -r 60 output.webp
```
> 其中<br>
> - quality是你需要的质量
> - r是你需要的帧率
- ps:为什么不用gif?因为有画质折损
