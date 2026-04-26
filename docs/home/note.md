# 个人笔记
> 这里存放着个人笔记，不要偷看哦(其实偷看也无所谓的啦)
  # 双系统时间异常
  > 这个问题真是让人头疼，其实原因很简单:<br>
  > window使用的时间是主板时间
  > 但是Linux使用的是[UTC时间](https://zhuanlan.zhihu.com/p/135951778)<br>
  > linux会把主板时间改为UTC时间，也就是比北京时间慢8个小时的样子<br>
  >> ** *注意* **如果你有主板自动唤醒设置并且希望使用UTC时间，需要把唤醒时间调慢8小时
  > [解决方案](https://blog.iyatt.com/?p=10644)网上有很多,个人更建议选用UTC时间

  # 无法显示密码授权框
  > 其实就是没安装
```sh
sudo pacman -S polkit-gnome
```
  > 你需要设置自动启动，以niri为例，在~/.config/niri/config.kdl中加入以下
```自动启动
spawn-at-startup "/usr/lib/polkit-gnome/polkit-gnome-authentication-agent-1"
```

  # 代理相关
  > Linux不用代理实在是太难了<br>
  > 推荐使用[Fclash](/home/tool.md#Fclash)或[nekoray](https://github.com/MatsuriDayo/nekoray)或[v2rayN](/home/tool.md#v2rayN),可惜nekoray已经挂了,就不提供nekoray教程了<br>
  > 机场推荐[mitce](//mitce.net)(我没广告费，真只是推荐),大概4元就一个月了,香港那边延迟很低的<br>
  > 为了安全考虑，终端和系统图形化界面不是一个代理，系统代理无法自动应用于终端，[可以参考](https://blog.csdn.net/Min_Xiansen/article/details/144010739),以下命令可以临时将系统代理应用于终端
```sh
proxy_mode=$(gsettings get org.gnome.system.proxy mode)
proxy_host=$(gsettings get org.gnome.system.proxy.socks host)
proxy_port=$(gsettings get org.gnome.system.proxy.socks port)
if [ "$proxy_mode" = "'manual'" ]; then
    export http_proxy=socks5://${proxy_host//\'/}:${proxy_port}
    export https_proxy=socks5://${proxy_host//\'/}:${proxy_port}
    export all_proxy=socks5://${proxy_host//\'/}:${proxy_port}
fi
```

  # Desktop文件的编辑
  > desktop文件所在位置为*\~/.local/share/applications/*<br>
  > desktop文件图标位置为*\~/.local/share/icons/*<br>
  > 以下为.desktop格式
```sh
[Desktop Entry]
Version=1.0
Name=appName
Comment=Description
Exec=/path/to/executable
Icon=/path/to/icons
Terminal=false
Type=Application
Categories=Utility;Development;
```
  > 其中[Desktop Entry],Name,Exec,Type为必选，其他为可选
  > [补充](//blog.csdn.net/danshiming/article/details/149305616)

  # Arch系安装deb包
  > 我最推荐的方案是不安装deb包，因为没有好的方案，都是存在问题的

  1. 使用debtap转化为zst包
  > 以下命令安装debtap(好像很慢)
```sh
yay -S debtap
```
  > 以下命令可以转化
```sh
#先更新debtap
sudo debtap -u
#开始转化,过程中会问你包名之类的内容，不知道就直接回车
sudo debtap 你要转化的deb包路径.deb
```
  2. 使用ace环境容器
  > 可以自己找一个容器，这里我举一个例子,这是星火应用市场官方提供的
```sh
yay -S amber-ce-bookworm
```
  > 接着就可以用以下命令启动容器，在容器中安装deb包了
```sh
bookworm-run
```
  3. apm环境安装，[请看](/home/system#星火应用市场)
# npm换源
> 可以安装nrm后换源
```sh
npm install -g nrm
nrm ls
nrm use taobao
```
>也可以直接换源
```sh
npm config set registry https://registry.npmmirror.com
```

# 配置git与github互联
> 开始之前你需要一个github账户，当然如果你用的是其他托管平台也不会有问题<br>
> 我们使用的是ssh互联，在互联开始前我们需要设置一些git属性<br>
> 这些属性在git使用commit时需要，因为git需要作者名才能commit,但是其实你乱设置也不会有任何致命问题
```sh
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
> 接下来开始正式工作
1. 生成一个ssh密钥对,你需要安装openssh,但大部分linux会默认安装
> 如果你去查找其他文章你会发现他们还设置了别的属性，但其实你什么都不设置也能用<br>
> 这个操作需要你提供一个保存路径，如果不提供默认会在~/.ssh中生成密钥对
```sh
ssh-keygen
```
2. 你需要把这对密钥对的公钥给github,私钥你则自己留着
> 点开你在github上的头像-->点击Setting(设置)-->点击ssh and GPG keys(ssh和GPG密钥)-->在ssh中点击New SSH keys(你也可以[点击这里](//github.com/settings/ssh/new)直接打开该页面)
> 在Title中随便填一个你喜欢的，Key type可以不变，在Key中填入你的公钥(如果你用的是默认设置，公钥会保存在~/.ssh文件夹中并使用.pub为文件后缀)
> 最后点击Add SSH Keys就完成了。github会根据你提供的公钥自动识别私钥。
> 你可以使用以下命令查看是否成功，如果成功会显示出sucess字样
```sh
ssh -T git@github.com
```
3. 因为是ssh密钥所以必须要ssh仓库才能使用哦,git会自行使用你的ssh密钥，你可以在你仓库的code按钮找到ssh链接(请不要使用里面的https链接，那样会出现鉴权错误)，类似于以下命令可以克隆仓库，请自行更改链接
```sh
git clone git@github.com:username/reposity.git
```
> 当然如果你是一个新仓库也可使用类似以下命令
```sh
git remote add origin git@github.com:username/reposity.git
git push -u origin main
```
> 最后注意：全过程其实写的一点也不详细，最好配合其他各个资料查看
