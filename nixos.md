# NixOS Lantxx安装wiki (施工中)

## 安装nixos
在引导界面选择Gnoma或KDE

### 进入系统后换国内源 (解决卡46%)
  
```
sudo vim /etc/nix/nix.conf
```
添加以下行
```
substituters = https://mirrors.tuna.tsinghua.edu.cn/nix-channels/store
```

```
!rm %
w! %
```
“:q”退出vim

### 开始常规安装设置
（省略）


### 情况一、选择NoDesktop安装
安装完成后重启系统

进入命令行界面

输入账号密码

#### 更改源
```
nix-channel --add https://mirrors.tuna.tsinghua.edu.cn/nix-channels/nixpkgs-unstable nixpkgs
nix-channel --update
```

#### 临时安装vim
``` 
nix-shell -p vim
```

### 开始进行你的NixOS配置吧！

#

### 配置NixOS

#### 1、国内源加速构建

shell：
```
nixos-rebuild switch --option substituters "https://mirrors.tuna.tsinghua.edu.cn/nix-channels/store"
```
.nix:
```
nix.settings.substituters = [
    https://mirrors.tuna.tsinghua.edu.cn/nix-channels/store
]
```

#### 2、flake配置

在```～/<your flake name>/```中初始化flake


#### 3、fcitx5配置输入法


##### 问题一、：配置页面没有中文输入法：
``` fcitx5 -r --enabel fcitx5-rime```    启用rime

     
