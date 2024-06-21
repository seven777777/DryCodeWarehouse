# node版本管理

## nvm（pc）
常用命令：
```
nvm ls 查看已经安装的所有nodejs版本
nvm install 版本号，可安装指定版本的nodejs
nvm use 版本号，即可切换到指定版本
nvm current 当前使用版本
nvm uninstall 版本号，卸载指定版本
```

## n（mac）
常用命令：
```
n 查看所有已安装node版本
显示版本界面，通过上下箭头选择node版本，回车选择
q/ctr+c 退出版本列表界面
n node-version 安装或使用指定版本的nodejs
eg：使用命令 n 8.12.0 时
当8.12.0版本没有安装时，则安装这个版本。
如果8.12.0版本已经安装了，则切换的这个node版本
n latest 使用或安装最新的官方发布
n stable 使用或安装稳定的官方发布
n lts 使用或安装最新的LTS官方版本
n rm 0.9.4 删除一个node版本
n rm 0.9.4 v0.10.0 删除一些版本
或者使用-代替rm： n - 0.9.4
n prune 删除当前版本外所有其他版本
3.6.1 删除除当前版本外所有其他版本：n prune
```