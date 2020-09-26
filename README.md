# PhantomMC

一个基于 Python 的 Minecraft 离线模式网络通信程序

本程序不含 WebGUI，仅提供 API 层面的支持

如需要参考我们的 WebGUI 交互界面，请前往 PhantomMC-WebGUI 分支

![github-logo](https://github.com/Mr-Notch/PhantomMC/blob/master/github-logo.png?raw=true)



# 开源协议

**本程序遵循 GPL-3.0 开源协议。**

开发语言：

- Web-GUI 部分：Python、PHP
- 受控端部分：Python、Java、DOS
- 主控端部分：Python
- Minecraft Mod：Java



# 使用说明

> 本程序仅用作公益性质的、Minecraft 服务器、Minecraft 论坛、Minecraft 交流会等组织合理合法使用
>
> 禁止将本程序用于开发游戏盒子等违反 Minecraft EULA 的项目

**本程序由 Hydrogen Studio、HGR-Community、Mr-Notch 等组织与个人进行创作与维护**



# 工作原理

> Phantom 通过 主控端、受控端、WebGUI、Minecraft Mod 四大板块进行 控制、被控、交互、终端处理。
>
> Phantom 能实现小规模地在 Minecraft 处于离线模式情况下的 “局域网” 通信、多人联机等
>
> 嗯，就这样吧



## 🎨 主控端 Palette

调色板（palette）是 PhantomMC 的主控端代号。（下文简称调色板）

调色板基于 Python 通过 PhantomAPI 与受控端通信，并通过 WebGUI 进行一系列的控制与操作

使用 async 异步处理每个受控端的请求，降低主控端服务器的工作负荷



## 🍦 受控端 Cream

冰淇淋（cream）是 PhantomMC 的受控端代号。（下文简称冰淇淋）

冰淇淋基于 Python 主语言，并通过 DOS 命令行与 Windows 进行通信。

受控端通过 PhantomAPI 与主控端通信，受控端负责执行主控端所发出的指令并在终端计算机上使用命令行执行



## ⚓ 客户端模组 Anchor

锚（anchor）是 PhantomMC 的客户端模组代号。（下文简称锚）

锚通过 SpongeMixin 介入 Minecraft 源码并使用 PhantomAPI 与受控端通信来达到修改 Minecraft 的目的

锚目前仅支持 1.12.2 的 Minecraft Forge 客户端



## 通信方式

启动使用了 Anchor 的 Minecraft 客户端后，Anchor 向终端机安装的受控端发送接入信息。

受控端通过访问主控端的公网入口来注册终端机的唯一ID（SID）

SID 包含了 终端机配置信息、Minecraft 客户端信息、终端机时间 等

主控端将 SID 写入至数据库内，并联系 WebGUI 来向受控端发送一个控制面板网页入口

受控端收到主控端发来的网页入口后，通过 Anchor 的 Mixin 插入 PhantomUI 代码，并启动 Minecraft

启动完成后，Minecraft 的主界面、ESC界面的 “向局域网开放” 变为 “打开Phantom面板” 。

使用者通过该控制面板即可操作 Minecraft 客户端并向其他使用者开放



## 接入方式

受控端使用 Frp 协议映射 Minecraft 的局域网端口

主控端服务器拥有公网IPv4与IPv6地址

所有受控端 Frp 开放的端口均由主控端管理，避免冲突

Frp 服务器同样拥有公网IPv4地址，并通过TCP协议传输数据



## API 与 Mixin 混淆表

### I. PhantomAPI

> API 内容过多，请前往下方链接处查看
>
> 点我看



### II. Mixin 混淆表

> 混淆表内容过多，请前往下方链接处查看
>
> 点我看



# ❤ Powered by You !
