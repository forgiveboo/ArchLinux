# ArchLinux使用日常
### 将ranger默认编辑器改为nvim
- 方法1：将系统的默认编辑器改为nvim `echo export EDITOR=/usr/bin/nvim >> ~/.zshrc`
- 方法2：[将Ranger默认编辑器改成nvim](https://blog.csdn.net/zmhzmhzm/article/details/106765480)
   1. 打开~/.config/ranger/rifle.conf, 找到以下代码段:
   ```
   #-------------------------------------------
   # Misc
   #-------------------------------------------
   # Define the "editor" for text files as first action
   mime ^text,  label editor = $EDITOR -- "$@"
   mime ^text,  label pager  = "$PAGER" -- "$@"
   !mime ^text, label editor, ext xml|json|csv|tex|py|pl|rb|js|sh|php = $EDITOR -- "$@"
   !mime ^text, label pager,  ext xml|json|csv|tex|py|pl|rb|js|sh|php = "$PAGER" -- "$@"
   ```
   2. 将上面两个$EDITOR修改成nvim, 如下:
   ```
   #-------------------------------------------
   # Misc
   #-------------------------------------------
   # Define the "editor" for text files as first action
   mime ^text,  label editor = nvim -- "$@"
   mime ^text,  label pager  = "$PAGER" -- "$@"
   !mime ^text, label editor, ext xml|json|csv|tex|py|pl|rb|js|sh|php = nvim -- "$@"
   !mime ^text, label pager,  ext xml|json|csv|tex|py|pl|rb|js|sh|php = "$PAGER" -- "$@"
    ```
### error: failed to commit transaction (invalid or corrupted package)
`sudo pacman -Sy archlinux-keyring`
### 安装yay
- 在/etc/pacman.conf中添加archlinxcn源
```
[archlinuxcn]
Server = https://aur.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```
- 更新源

`sudo pacman -Syy`
- 安装archlinxcn-keyring

`sudo pacmam -S archlinuxcn-keyring`
- 安装yay

`sudo pacman -S yay`
### 安装带有模糊特效的picom
[AUR源](https://aur.archlinux.org/packages/picom-jonaburg-git/)
> 几乎不需要任何配置就可以实现高斯特效

### 查询网卡
`ls /sys/class/net`
