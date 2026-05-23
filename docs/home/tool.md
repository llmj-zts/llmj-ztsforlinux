# 食用工具
> 这里存放着很多食用工具


# neovim
> [neovim](https://github.com/neovim/neovim)是一个优化版本的[vim](https://github.com/vim/vim),最大的优化是支持lua插件<br>
```sh
sudo pacman -S neovim 
```
> 本身其实与vim没有区别，但是一旦加入插件就是天差地别了<br>
> 其中最推荐的插件是[lazyvim](https://github.com/LazyVim/LazyVim)作为开箱即用的超级好用的插件<br>
> 可以使用官方的[一键安装方法](https://www.lazyvim.org/installation)(安装前请确保你已经安装neovim和[nerdfont](/home/system.md#常用字体安装))<br>
> 因为在linux端配置过于简单，所以不提供已配置完的文件了，如果无法与系统剪贴板同步记得安装剪贴板工具
```sh
sudo pacman -S wl-clipboard
```
> 需要使用python代码补全需要安装pyright,需要使用C/C++代码补全需要安装clangd,这里不提供示例了


# localsend
> [localsend](//localsend.org)是一个局域网互传文件的工具，功能很强<br>
1. 推荐使用[AppImage](https://yhsb.lanzouw.com/ihHt23f5dbra)包
2. 也可以使用pacman安装
```sh
sudo pacman -S localsend
```

# kdeconnect
> [kdeconnect](//kdeconnect.kde.org/)作为kde全家桶的一员，真是太好用了<br>
> 当然如果你是kde桌面那它的兼容性更好
```sh
sudo pacman -S kdeconnect
```
> 请在手机端下载这个[软件](//yhsb.lanzouw.com/iXGrw3nlutqd)

# 代理软件
## Fclash
> [Fclash](https://github.com/chen08209/FlClash)是一个非常好用的clash代理软件,很适合中国宝宝体质<br>
1. 推荐使用[AppImage](https://yhsb.lanzouw.com/iA4yu3ijlw7g)包
2. 这玩意没aur和pacman的包
## v2rayN
> [v2rayN](https://github.com/2dust/v2rayN)是一个gui型v2ray客户端
1. 这玩意AppImage包太大,就不提供了
2. 有aur包,以下命令安装
```sh
yay -S v2rayn-bin
```
> ** 注意 **这玩意用yay安装下载奇慢，开代理可以加快，但你就在下载代理啊！！！
## ClashVerge
> [clashverge](https://github.com/Clash-Verge-rev/clash-verge-rev)是一个gui的clash代理软件
1. 这玩意没有AppImage包
2. 有可以自行编译的aur包，下载速度很快
```sh
yay -S clash-verge-rev
```

# QefiEntryManager
> [QefiEntryManager](https://github.com/Inokinoki/QEFIEntryManager)是一个非常好用的efi图形化管理工具
```sh
yay -S qefientrymanager
```
> ** 注意 ** 如果你不知道如何使用，请不要盲目尝试！！！去项目官网查看教程！！！<br>

# CrossOver
> [crossover](https://www.crossoverchina.com/)这是一个商业以wine做的软件，可以让你在linux上使用window应用<br>
> 实测下来安装自己的应用就是一坨，但下载它应用市场的应用非常好<br>
> 价格的话是190多一辈子，有时候会打折便宜挺多，如果有能力还是去买下官方的吧
1. 首先你要[安装CrossOver](https://www.crossoverchina.com/xiazai.html),bin文件是可执行文件来的
2. 无限试用的话方法不一，自己[查](https://cn.bing.com/search?q=crossover%E6%97%A0%E9%99%90%E8%AF%95%E7%94%A8linux)吧
