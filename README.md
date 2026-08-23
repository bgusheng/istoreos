iStoreOS 是一款入门级路由系统，同时也是一款入门级 NAS 系统。
它基于原版 OpenWrt 开发，最初在 ARS2 平台上经过长期迭代，
最终逐步开放适配到多个硬件平台。

更多信息请参阅：https://github.com/istoreos

以下是 OpenWrt 原始 README 的中文翻译
--------

![OpenWrt logo](include/logo.png)

OpenWrt 项目是一个面向嵌入式设备的 Linux 操作系统。

OpenWrt 并不试图提供一个单一且固定不变的固件，而是提供了一个
完全可写的文件系统以及完善的软件包管理机制。

这使用户不再受限于设备厂商预先提供的应用程序和系统配置，
而是可以通过安装和使用不同的软件包，根据自己的需求自由定制设备，
从而满足各种不同的应用场景。

对于开发者而言，OpenWrt 是一个用于构建应用程序的系统框架，
无需为了运行某个应用而重新构建一个完整的固件。

对于普通用户而言，这意味着可以对设备进行高度自由的定制，
甚至可以以设备厂商从未设想过的方式使用设备。

阳光万里！


## 下载

OpenWrt 为多种硬件架构提供了已经编译好的固件镜像，
并且这些镜像通常包含一套适用于家庭 WiFi 路由器的软件包。

如果你想快速找到一个可以从厂商原厂固件迁移到 OpenWrt 的固件镜像，
可以使用 *Firmware Selector（固件选择器）*。

* [OpenWrt 固件选择器](https://firmware-selector.openwrt.org/)

如果你的设备受到 OpenWrt 支持，请点击对应的 **Info（信息）** 链接
查看详细的安装说明，或者参考下面列出的支持资源。


## 

对于高级用户来说，可能需要安装额外的或特定的软件包，
例如 Toolchain（工具链）、SDK 等。

如果你需要的不是简单的固件下载，
可以前往 OpenWrt Wiki 的下载页面：

* [OpenWrt Wiki 下载页面](https://openwrt.org/downloads)


## 开发

如果你想自行编译 OpenWrt，需要使用 GNU/Linux、BSD 或 macOS 系统。

注意：编译环境必须使用区分大小写的文件系统。

Cygwin 不受支持，因为其文件系统不具备完整的大小写敏感能力。


### 环境要求

编译 OpenWrt 需要安装以下工具。

不同 Linux 发行版中的软件包名称可能有所不同。
完整的、针对不同发行版的依赖列表，
请参考：

* [构建系统安装文档](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)

### 快速开始

1. 运行 `./scripts/feeds update -a`，
   获取 feeds.conf / feeds.conf.default 中定义的所有最新软件包信息。

2. 运行 `./scripts/feeds install -a`，
   为获取到的所有软件包创建符号链接，
   并将其放入 `package/feeds/` 目录。

3. 运行 `make menuconfig`，
   选择你需要的工具链、目标系统以及固件软件包。

4. 运行 `make` 开始编译。

   该命令会自动下载所需的源代码，
   编译交叉编译工具链，
   然后编译 GNU/Linux 内核以及所有选择的应用程序，
   最终生成适用于目标设备的固件。


### 相关仓库

OpenWrt 主仓库通过多个子仓库管理不同类别的软件包。

所有软件包都可以通过 OpenWrt 的软件包管理器 `opkg` 进行安装。

如果你希望开发 Web 管理界面，
或者将软件包移植到 OpenWrt，
可以根据具体用途参考下面的相关仓库。

* [LuCI Web 管理界面](https://github.com/openwrt/luci)：
  OpenWrt 的现代化 Web 管理界面。

* [OpenWrt Packages](https://github.com/openwrt/packages)：
  已经移植到 OpenWrt 的各类软件包。

* [OpenWrt Routing](https://github.com/openwrt/routing)：
  专门用于路由功能的软件包，例如 Mesh 等。

* [OpenWrt Video](https://github.com/openwrt/video)：
  用于 Xorg、Wayland 以及视频相关客户端和服务的软件包。


## 支持信息

有关 OpenWrt 支持的设备列表，请参阅：

* [OpenWrt 硬件数据库](https://openwrt.org/supported_devices)


### 文档

* [快速入门指南](https://openwrt.org/docs/guide-quick-start/start)

* [用户指南](https://openwrt.org/docs/guide-user/start)

* [开发者文档](https://openwrt.org/docs/guide-developer/start)

* [技术参考](https://openwrt.org/docs/techref/start)


### 支持社区

* [OpenWrt 官方论坛](https://forum.openwrt.org)：
  用于用户交流、项目讨论、技术咨询以及硬件选型建议。

* [OpenWrt 支持聊天](https://webchat.oftc.net/#openwrt)：
  频道为 `#openwrt`，服务器为 `oftc.net`。


### 开发者社区

* [Bug 报告](https://bugs.openwrt.org)：
  用于提交 OpenWrt 的 Bug。

* [开发者邮件列表](https://lists.openwrt.org/mailman/listinfo/openwrt-devel)：
  用于进行 OpenWrt 开发相关的讨论。

* [开发者聊天](https://webchat.oftc.net/#openwrt-devel)：
  频道为 `#openwrt-devel`。


## 许可证

OpenWrt 使用 GPL-2.0 许可证。
