# 介绍

![Banner](/static/images/banner.png)

Arch Linux RISC-V 项目隶属 [PLCT Lab](https://plctlab.org) 旗下，是一个旨在为 RISC-V 架构进行软件可用性移植的开源项目。通过对源码进行一系列 Patch 和测试，使得其他平台软件能够分发到对应架构上并正常使用。

## 项目负责人

- Felix Yan / [@felixonmars](https://github.com/felixonmars): 项目主要负责人，下以肥猫代称

## 项目地址

- 代码仓库：[https://github.com/felixonmars/archriscv-packages](https://github.com/felixonmars/archriscv-packages)

## 签名密钥

[0xB5971F2C5C10A9A08C60030F786C63F330D7CB92](https://keys.openpgp.org/vks/v1/by-fingerprint/B5971F2C5C10A9A08C60030F786C63F330D7CB92)

打包并签名是一种常用的验证分发一致性的方式，如果是正在使用 Arch Linux 的用户，签名密钥已经包含在 archlinux-keyring 中，无需额外导入。

## 镜像站

- 加拿大 / Canada
    - 肥猫 (主站 / Main): [https://archriscv.felixc.at/](https://archriscv.felixc.at/)
- 罗马尼亚 / Romania
    - 肥猫: [https://mirrors.felixc.at/archriscv/](https://mirrors.felixc.at/archriscv/)
- 中国 / China
    - 中科院软件研究所: [https://mirror.iscas.ac.cn/archriscv/](https://mirror.iscas.ac.cn/archriscv/)
    - 南方科技大学: [https://mirrors.sustech.edu.cn/archriscv/](https://mirrors.sustech.edu.cn/archriscv/)
    - 武昌首义学院 (仅教育网 / CERNET only): [https://mirrors.wsyu.edu.cn/archriscv/](https://mirrors.wsyu.edu.cn/archriscv/)

打好的软件包通过主站进行分发，而镜像站负责提供软件包缓存，以达到负载均衡、加速下载的效果，使用时可以根据自己的网络情况进行选择。

镜像站的目录结构通常如下表所示：

|目录 / Directory |描述 / Description |
| :--: | :--: |
| /images | rootfs 基本环境 / rootfs stage tarball |
| /repo | 二进制包仓库 / binary repository |

## 移植进程

[https://archriscv.felixc.at/.status/status.htm](https://archriscv.felixc.at/.status/status.htm)

最新的打包状态可以在上述网站中获取，无论是开发者还是关心移植进度的用户都可以自行查看。为了更好的解读类表内容，常见的软件包状态如下：

|状态名 / Name | 描述 / Description |
| :--: | :--: |
| 2.6.1-1 -> 2.6.1-2 | 正常版本迭代 / Update |
| FTBFS | 无法从源代码直接构建 / Fails To Build From Source |
| Dependency '*' not satisfied. | 依赖不满足 |
| Leaf package, port it! | 无关联依赖包，可直接移植 |

## [快速上手](./Usage.md)

## [贡献指南](./Contribution.md)
