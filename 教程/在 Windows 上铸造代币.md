# 在 Windows 上铸造代币

- [在 Windows 上铸造代币](#在-windows-上铸造代币)
  - [简介](#简介)
  - [环境准备](#环境准备)
    - [开始之前](#开始之前)
    - [安装 Microsoft C++ 生成工具 和 Windows SDK](#安装-microsoft-c-生成工具-和-windows-sdk)
    - [安装 Cargo](#安装-cargo)
    - [安装 melminter 和 melwalletd](#安装-melminter-和-melwalletd)
  - [开始铸币](#开始铸币)
  - [附录](#附录)
    - [参考链接](#参考链接)
    - [改动说明](#改动说明)
    - [反馈方式](#反馈方式)
    - [官方链接](#官方链接)
    - [许可协议](#许可协议)
    - [免责声明](#免责声明)

## 简介

MEL 是 Themelio 公链的「低波动性代币」和链上主要代币，具有内生信任、去中心化等特性，需要利用 CPU 计算并铸造中间代币 ERG，再将 ERG 兑换为 MEL 获得。

**特别说明**：铸造 ERG 的原理和 BTC、ETC 挖矿的原理有本质上的不同，因此，请尽量表述为铸造而不是挖矿。

## 环境准备

### 开始之前

准备一台用于铸币的计算机，这是我的测试机环境（虚拟机）：

- 操作系统：Windows 10 Enterprise LTSC 21H2

- 内存：4 GiB

- 处理器：AMD Ryzen 3700X 2-Core

通常较新版本的 Windows 都可以正常铸造 MEL。

如果你的铸币机器在中国大陆，那么建议准备一个 **速度较快** 的代理或者 VPN，因为在准备铸币环境时需要下载较多海外网站的文件。

### 安装 Microsoft C++ 生成工具 和 Windows SDK

下载地址：<https://aka.ms/vs/16/release/vs_buildtools.exe>

下载完成之后，打开下载好的文件，点击继续。

![点击继续](在%20Windows%20上铸造代币/converted/install-build-tools-and-windows-sdk-1.webp)

安装完成之后会自动打开，然后点击单个组件。

![点击单个组件](在%20Windows%20上铸造代币/converted/install-build-tools-and-windows-sdk-2.webp)

搜索 **MSVC v142 - VS 2019 C++ x64/x86**，然后勾选 **MSVC v142 - VS 2019 C++ x64/x86 生成工具(最新)**。

![勾选 MSVC v142 - VS 2019 C++ x64/x86 生成工具(最新)](在%20Windows%20上铸造代币/converted/install-build-tools-and-windows-sdk-3.webp)

继续搜索 **Windows SDK**，勾选最新版的 Windows 10 SDK，如果你使用 Windows 11，则勾选下方的 Windows 11 SDK，然后点击右下角的安装。

![勾选 Windows SDK](在%20Windows%20上铸造代币/converted/install-build-tools-and-windows-sdk-4.webp)

等待安装完成。

![等待安装完成](在%20Windows%20上铸造代币/converted/install-build-tools-and-windows-sdk-5.webp)

### 安装 Cargo

打开 <https://www.rust-lang.org/learn/get-started>，点击如图所示的位置（如果你的系统是 32 bit，则点击左边的按钮）。

![下载 Cargo](在%20Windows%20上铸造代币/converted/install-cargo-1.webp)

打开下载好的文件。

![打开下载好的文件](在%20Windows%20上铸造代币/converted/install-cargo-2.webp)

点击回车键，会自动开始安装。

![安装 Cargo](在%20Windows%20上铸造代币/converted/install-cargo-3.webp)

安装完成的截图：

![安装完成的截图](在%20Windows%20上铸造代币/converted/install-cargo-4.webp)

### 安装 melminter 和 melwalletd

按键盘上的 Windows + R 键，输入 `cmd`，Windows 键在大多数键盘上是 Ctrl 右边的按键。然后点击回车键打开 cmd。

![打开 “运行”](在%20Windows%20上铸造代币/converted/install-melminter-and-melwalletd-1.webp)

![打开 cmd](在%20Windows%20上铸造代币/converted/install-melminter-and-melwalletd-2.webp)

输入 `cargo install --locked melminter melwalletd` 并按回车键，会自动开始安装组件，此步骤需要等待的时间较长，请保持耐心。

![安装 melminter 和 melwalletd](在%20Windows%20上铸造代币/converted/install-melminter-and-melwalletd-3.webp)

## 开始铸币

按键盘上的 Windows + R 键，输入 `cmd`，然后按回车键打开 cmd。

输入:

```powershell
melminter --payout <你的钱包地址>
```

例子：

```powershell
melminter --payout t19rcw46nfdy3vfwejw1a4qpng3s2km6myevcm5erjk0e2094rg640
```

输入完成后按回车键就可以开始执行铸币程序了，执行程序后，会提示让你发送 0.1 MEL 到它指定的地址（当作初始的手续费）：

![输入铸币命令](在%20Windows%20上铸造代币/converted/mint-1.webp)

发送 0.1 MEL 到铸币地址后，过一会，就可以看到开始铸币了：

![开始铸币](在%20Windows%20上铸造代币/converted/mint-4.webp)

## 附录

### 参考链接

- 阮一峰.「中文技术文档的写作规范」 GitHub. n.p. 2022-04-13. Web. 2022-07-17. <https://github.com/ruanyf/document-style-guide>.

- DaoCloud.「写作规范和格式规范」 DCS 文档. n.p. n.d. Web. 2022-07-17. <https://guide.daocloud.io/dcs/写作规范和格式规范-9153803.html>.

- LeanCloud.「文案风格指南」 LeanCloud 开放资源. n.p. n.d. Web. 2022-07-17. <https://open.leancloud.cn/copywriting-style-guide/>.

- wikiHow.「引用网站上的文献」 wikiHow. n.p. n.d. Web. 2022-09-07. <https://zh.wikihow.com/引用网站上的文献>.

- Themelio. 「Themelio docs」 Themelio. n.p. 2022-04-15. Web. 2022-09-23. <https://docs.themelio.org/try-themelio/melminter/>

- Rust. 「Install Rust」 Rust. n.p. n.d. Web. 2022-09-23. <https://www.rust-lang.org/tools/install>

### 改动说明

2022-09-23. 删除多余内容。

2022-09-23. 初稿。

详细信息：<https://github.com/ArtoriaShirou/Themelio-Personal-Notes/commits/main/教程/在%20Windows%20上铸造代币.md>

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

### 许可协议

本文采用知识共享 署名-非商业性使用-相同方式共享 4.0 国际 许可协议进行许可。要查看该许可协议，可访问 <https://creativecommons.org/licenses/by-nc-sa/4.0/> 或者写信到 Creative Commons, PO Box 1866, Mountain View, CA 94042, USA。

### 免责声明

本文只是个人笔记和想法，不是投资建议。投资有风险，入市需谨慎。
