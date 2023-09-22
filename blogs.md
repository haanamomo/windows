## 命令行查看配置

```sh
wmic cpu get NumberOfCores

# 按内存条显示，一般看第一个数字
wmic memorychip get capacity
```

## 快捷键

### win 

`win` 搜索

`win + shift + s`	截屏

`win + e`		打开文件管理器

`win + tab` 		任务管理

`win + h`		语音输入

`win + .` 		输入表情符号

`win + z` 		分屏管理


### edge 

`f11` 		全屏

`f9` 		退出沉浸式阅读

### massigra

`f`		图片放大

### flashpad

`alt + z` 		呼出

`esc` 		退出

`control -`	分隔符

## windows应用

* aida64: 硬件检测
* Everything ：搜索文件
* CrystalDiskMark：检查硬盘读取写入的速度
	> [CrystalDiskMark怎么看](https://www.jianshu.com/p/fb235b1e76df)

极速轻量应用

* clibor：剪贴板历史
* flashpad: 笔记软件
* MassiGra：看图软件

## 安装http-server


1.  [官网](https://nodejs.org/en/download)下载node.js
2.  打开`node.js command prompt`
3.  `npm install -g http-server`
4.  `cd <dir>; http-server`

## 画图取色

* `win + shift + s`截图后粘贴到画图里
* 用取色器取色
* 点击`编辑颜色`查看rgb值

## Git Bash安装zsh

* 去[Git官网](https://git-scm.com/download/win)下载并安装Git Bash。
* 下载[.zst压缩包](https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64), 在`File:`后面
* 解压两次.zst，可以用bandizip
* 把文件拷贝到Git Bash安装的根目录，默认是`C:\Program Files\Git`，`etc`等目录应直接在`C:\Program Files\Git`下
* 打开Git Bash输入`zsh`，首次启动需要配置
* 在`~/.bashrc`写入以下内容使用zsh为默认终端：
  ```shell
  if [ -t 1 ]; then
      exec zsh
  fi
  ```
* 重开后测试当前终端`echo $0`

- [powerlevel10k](https://github.com/romkatv/powerlevel10k)

## ffmpeg

ffmpeg批量裁剪音频

```
cd C:\Users\1\Downloads\<dir>
mkdir outdir;
Foreach ($i in @(Get-ChildItem *.mp3)) { ffmpeg -i $i -ss 2 outdir\$(Split-Path $i -leaf)}
```

## 无权限修改文件

点击文件，右键`properties`，选择第二个`Security`, 选择最后一个`Users(你的用户名)`，在下面添加`Modify`和`Write`的权限

## 面板添加Path

搜索“Environment”，点击“Advanced-Environment Variables”，选中Path，点击Edit，点击New

## Powershell修改Path

* 显示：`$ENV:Path.Split(";")`
* 追加：`$ENV:Path="C:\Program Files\xxx;"+$ENV:Path`
* 删除：`Set-Item ENV:Path $ENV:Path.Replace("<somePath>;", "")`
* 替换：`Set-Item ENV:Path $ENV:Path.Replace("<old>", "<new>")`

## 局域网共享文件

* 首先点击文件浏览器中的网络，开启共享功能。
* 找到局域网内的计算机，通过命令行内的`ipconfig`查找ip，或者输入电脑名。如果想要修改为好记一点的电脑名，按`win`后搜索`计算机`或者`重命名`
* 在文件浏览器中输入`\\ip`或者`\\name`
* 输入本地账户的账号密码。如果是用Microsoft账户登录，则账号是Microsoft账户名， 密码是Microsoft账户密码

如果上述失败，在控制面板中找到`程序-启用或关闭Windows功能`，勾选SMB及子选项。