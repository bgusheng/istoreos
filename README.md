iStoreOS 是入门级的路由系统，也是入门级的 NAS 系统，
基于原版 OpenWRT，在 ARS2 上经过长期迭代，最终开放适配到多个硬件平台

更多信息请参阅 https://github.com/istoreos


以下是 OpenWRT 原始的 README
--------

![OpenWrt logo](include/logo.png)
OpenWrt 项目是一个面向嵌入式设备的 Linux 操作系统。与其尝试创建一个单一、固定的固件，OpenWrt 提供了一个完全可写的文件系统以及软件包管理功能。这使你不再受厂商提供的应用程序选择和配置的限制，并可以通过使用软件包，根据自己的需求对设备进行定制。

对于开发者来说，OpenWrt 是一个用于构建应用程序的框架，无需围绕应用程序重新构建一个完整的固件；对于用户来说，这意味着可以对系统进行完全自定义，以各种厂商从未设想过的方式使用设备。

## Download
OpenWrt 为多种硬件架构提供了已经编译好的固件镜像，并且这些固件通常会预先选择一些适合用作家庭 WiFi 路由器的软件包。
如果你想快速找到一个可以从厂商原厂固件迁移到 OpenWrt 的固件镜像，可以尝试使用
*Firmware Selector（固件选择器*.

* [OpenWrt Firmware Selector](https://firmware-selector.openwrt.org/)
如果你的设备受到支持，请点击**Info**（信息） 链接查看安装说明，或者参考下面列出的支持资源。


## 

An advanced user may require additional or specific package. (Toolchain, SDK, ...) For everything else than simple firmware download, try the wiki download page:

* [OpenWrt Wiki Download](https://openwrt.org/downloads)

## Development

To build your own firmware you need a GNU/Linux, BSD or macOS system (case
sensitive filesystem required). Cygwin is unsupported because of the lack of a
case sensitive file system.

### Requirements

You need the following tools to compile OpenWrt, the package names vary between
distributions. A complete list with distribution specific packages is found in
the [Build System Setup](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)
documentation.

```
binutils bzip2 diff find flex gawk gcc-6+ getopt grep install libc-dev libz-dev
make4.1+ perl python3.7+ rsync subversion unzip which
```

### Quickstart

1. Run `./scripts/feeds update -a` to obtain all the latest package definitions
   defined in feeds.conf / feeds.conf.default

2. Run `./scripts/feeds install -a` to install symlinks for all obtained
   packages into package/feeds/

3. Run `make menuconfig` to select your preferred configuration for the
   toolchain, target system & firmware packages.

4. Run `make` to build your firmware. This will download all sources, build the
   cross-compile toolchain and then cross-compile the GNU/Linux kernel & all chosen
   applications for your target system.

### Related Repositories

The main repository uses multiple sub-repositories to manage packages of
different categories. All packages are installed via the OpenWrt package
manager called `opkg`. If you're looking to develop the web interface or port
packages to OpenWrt, please find the fitting repository below.

* [LuCI Web Interface](https://github.com/openwrt/luci): Modern and modular
  interface to control the device via a web browser.

* [OpenWrt Packages](https://github.com/openwrt/packages): Community repository
  of ported packages.

* [OpenWrt Routing](https://github.com/openwrt/routing): Packages specifically
  focused on (mesh) routing.

* [OpenWrt Video](https://github.com/openwrt/video): Packages specifically
  focused on display servers and clients (Xorg and Wayland).

## Support Information

For a list of supported devices see the [OpenWrt Hardware Database](https://openwrt.org/supported_devices)

### Documentation

* [Quick Start Guide](https://openwrt.org/docs/guide-quick-start/start)
* [User Guide](https://openwrt.org/docs/guide-user/start)
* [Developer Documentation](https://openwrt.org/docs/guide-developer/start)
* [Technical Reference](https://openwrt.org/docs/techref/start)

### Support Community

* [Forum](https://forum.openwrt.org): For usage, projects, discussions and hardware advise.
* [Support Chat](https://webchat.oftc.net/#openwrt): Channel `#openwrt` on **oftc.net**.

### Developer Community

* [Bug Reports](https://bugs.openwrt.org): Report bugs in OpenWrt
* [Dev Mailing List](https://lists.openwrt.org/mailman/listinfo/openwrt-devel): Send patches
* [Dev Chat](https://webchat.oftc.net/#openwrt-devel): Channel `#openwrt-devel` on **oftc.net**.

## License

OpenWrt is licensed under GPL-2.0
