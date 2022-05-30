# 基础设施

## 设备列表

设备主要分为 `x86_64(qemu)` 架构的编译机和 `riscv(native)` 开发板两种，具体跳板地址和端口可以在群置顶中找到。

## 添加用户

> [https://github.com/plctlab/felix-infra](https://github.com/plctlab/felix-infra) <br/>
> [https://github.com/plctlab/riscv-lab-access](https://github.com/plctlab/riscv-lab-access)

编译机上的用户是根据上述两个仓库中的配置文件进行自动创建和部署的。

- 1. 首先需要准备好你的 `Github` 用户名和一个 SSH 公钥 ([为 Github 账户添加 SSH Key](https://docs.github.com/cn/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account))。添加好之后访问 [https://github.com/axionl.keys](https://github.com/axionl.keys) 进行验证（这里以我自己的用户名 `axionl` 为例）
- 2. 派生 `riscv-lab-access` 仓库后，将自己的用户名添加到 [developers.list](https://github.com/plctlab/riscv-lab-access/blob/main/developers.list)，申请合并。注意到如果不是使用 `Github` 首选的 `SSH Key` 的话也可以在后面以 `#` 分隔开，添加自己的密钥地址，记得确保地址能够被访问。
- 3. 派生 `felix-infra` 仓库后，将自己想创建的用户名和 Github 名称添加到 [userMap.json](https://github.com/plctlab/felix-infra/blob/main/userMap.json) 上（似乎约定成俗按字母顺序排列）。

## 连接机器

部署好后可以通过 ssh 访问服务器，因为机器较多，通常使用 [ssh config](https://www.man7.org/linux/man-pages/man5/ssh_config.5.html) 来进行配置管理，一个典型的配置如下:

```config
Host ARCHRV_US
    HostName <找群置顶的地址>
    Port 22
    IdentityFile ~/.ssh/git/axionl
    User axionl
```

由于 ssh 本身具有不稳定性，在访问特别是构建软件包的时候记得使用 `tmux` 保持一个回话，避免因为网络波动而中断打包流程，同时也记得在使用完成之后手动释放会话，登陆后可见提示如下。

```bash
Welcome to a powerful Arch Linux builder with RISC-V support.

This system IS NOT backed up. Please ensure you DO NOT keep valuable data here!

Usage Info
  - Use the devtools helpers to build packages.
  - Don't forget to set your PACKAGER in ~/.makepkg.conf.
  - Chroots are kept in /var/lib/archbuild (~chroots).

Last login: Sun May 15 04:36:34 2022 from <Your IP Address>
[axionl@minun ~]$ tmux
```