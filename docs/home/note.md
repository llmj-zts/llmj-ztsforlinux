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
