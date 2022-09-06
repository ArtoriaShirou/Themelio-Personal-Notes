# 在 Linux 上铸造 MEL 代币

- [在 Linux 上铸造 MEL 代币](#在-linux-上铸造-mel-代币)
  - [简介](#简介)
  - [环境准备](#环境准备)
    - [开始之前](#开始之前)
    - [更新系统](#更新系统)
    - [安装必要组件](#安装必要组件)
    - [安装 Cargo](#安装-cargo)
    - [安装 melminter 和 melwalletd](#安装-melminter-和-melwalletd)
  - [开始铸币](#开始铸币)
  - [附录](#附录)
    - [参考链接](#参考链接)
    - [版本说明](#版本说明)
    - [反馈方式](#反馈方式)
    - [官方链接](#官方链接)

## 简介

MEL 是 Themelio 公链的 “低波动性代币” 和链上主要代币，具有内生信任、去中心化等特性，需要利用 CPU 计算并铸造获得。

**特别说明**：铸造 MEL 的原理和 BTC、ETH 挖矿的原理有本质上的不同，因此，请尽量表述为铸造而不是挖矿。

## 环境准备

### 开始之前

准备一台用于铸币的计算机，这是我的测试机环境（虚拟机）：

- 操作系统：Debian 11.4

- 内存：4 GiB

- CPU：AMD Ryzen 3700X 8-Core

个人推荐使用开源、由社区制作的 Linux 发行版：Debian，且本文的命令全部基于 Debian 11.4，如果你使用 CentOS 或者 Rocky Linux 请自行替换部分命令。

准备一个 **速度较快** 的代理工具或者 VPN，此步骤需要下载较多文件。

准备一个好用的 SSH 工具，Windows 平台推荐使用 Xshell（功能强大且个人使用免费），如果你的 Windows 版本较新可以选择使用自带的 OpensSSH。

### 更新系统

通过 SSH 工具连接你的 Linux 计算机，然后输入以下命令：

```shell
sudo apt update
sudo apt upgrade -y
```

**注意**：如果你的系统版本过旧且安装了大量的软件包，则不建议直接更新，请务必理清依赖关系后再更新，同时注意更新时的选项，谨慎选择以防无法连接服务器。

### 安装必要组件

输入以下命令：

```shell
sudo apt install curl build-essential -y
```

### 安装 Cargo

输入以下命令：

```shell
curl https://sh.rustup.rs -sSf | sh -s -- -y
source "$HOME/.cargo/env"
```

当以上命令执行成功后，就可以使用 `cargo` 命令了。

### 安装 melminter 和 melwalletd

输入以下命令：

```shell
cargo install --locked melminter melwalletd
```

因为安装用 Rust 编写的程序一般都需要从头开始编译，所以可能会比较慢，耐心等待一段时间就好。

## 开始铸币

输入以下命令：

```shell
melminter --threads $(nproc) --payout <你的钱包地址>
```

例子：

```shell
melminter --threads $(nproc) --payout t19rcw46nfdy3vfwejw1a4qpng3s2km6myevcm5erjk0e2094rg640
```

执行 melminter 铸币程序后，会提示让你发送 0.1 MEL 到它指定的地址（当作初始的手续费），发送完成后过一会就可以看到开始铸币了。

## 附录

### 参考链接

- 阮一峰. “中文技术文档的写作规范”. GitHub. n.p, 2022-04-13. Web. 2022-07-17. <https://github.com/ruanyf/document-style-guide>.

- DaoCloud. “写作规范和格式规范”. DCS 文档. n.p, n.d. Web. 2022-07-17. <https://guide.daocloud.io/dcs/写作规范和格式规范-9153803.html>.

- LeanCloud. “文案风格指南”. LeanCloud 开放资源. n.p, n.d. Web. 2022-07-17. <https://open.leancloud.cn/copywriting-style-guide/>.

### 版本说明

2022-07-24. 初稿

### 反馈方式

Telegram: <https://ShirouArtoria.t.me/>

Twitter: <https://twitter.com/ShirouArtoria>

email: <work@artoriashirou.me>

Discord: ArtoriaShirou#4266

### 官方链接

Themelio Twitter: <https://twitter.com/ThemelioLabs>

Themelio Discord: <https://discord.gg/usY39nY6vM>

Themelio Telegram: <https://t.me/themeliolabs>

Themelio 官网：<https://themelio.org>
