# ArchLinux使用日常
1. 将ranger默认编辑器改为nvim
    > 将系统的默认编辑器改为nvim `echo export EDITOR=/usr/bin/nvim >> ~/.zshrc`
2. error: failed to commit transaction (invalid or corrupted package)
   `sudo pacman -Sy archlinux-keyring`
