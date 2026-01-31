# 游戏环节
> 这里是和游戏相关的工具和教程

# heroic
> [heroic](https://heroicgameslauncher.com/)是一个开源免费的游戏启动器，支持epic，gog,amazon平台的游戏<br>
> 这种开源软件很建议支持一下，有能力的捐下款
## 安装
> 因为AppImage包和其他离线包都比较大，就不提供了
1. 可以使用[flatpak](/home/system.md#flatpak)安装，这是最好的方法
2. 在[github上](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/releases)有不同的版本
## proton问题
> heroic自带一个proton和wine管理器，可以直接下载，但国内下载速度很慢
1. 直接开[代理](/home/note.md#代理相关)
2. 用[steam](#steam)下载到的可以被自动检测到
3. 手动下载并在设置里面选择proton路径，自己探索吧
> ** 注意 **其实就算你下载好了proton有些游戏还是会在启动中卡住，其实就是heroic要下载其他依赖，要么等要么代理吧，我真没办法

# steam
> [steam](https://s.team)算是反微软第一人了,做出[proton](https://github.com/ValveSoftware/Proton)也是没谁了,最好下载一个
## 安装
1. 可以使用[flatpak](/home/system.md#flatpak)安装
2. steam和archlinux有合作，可以直接用pacman安装
```sh
sudo pacman -S steam
```
## 添加其他游戏
1. 选择Add a Game
2. 选择Add a Non-steam Game
3. 选择Browser并选择游戏
4. 点开添加游戏的Properties(属性)
5. 在Compatibility（兼容性）中勾选Force...的选项（就这一个选项）
6. 建议选择Proton-GE以确保最佳兼容性
## Proton更多配置
> 一些必要或不必要的操作
### Proton-GE
> 原版steam有的proton兼容性并不完美，所以需要安装更完美兼容的[Proton-GE](https://github.com/GloriousEggroll/proton-ge-custom)
1. [下载]()并解压
2. 将解压的文件夹放在~/.steam/root/compatibilitytools.d中
3. 重启steam在兼容中查看是否多了个Proton-GE
### Protontricks
> 安装补丁或NET等都需要它
1. 可以使用pacman直接安装
```sh
sudo pacman -S protontricks
```
2. 一下命令可以直接打开它gui页面使用
```sh
protontricks --gui
```
