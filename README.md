# FluxLink

基于开源项目 [FlClash](https://github.com/chen08209/FlClash) v0.9.2 源码重新编译的安卓代理客户端。本仓库**只用于发布安装包**，不存放应用源码。

- 上游版本：FlClash `v0.9.2`（commit `7fd417f`），许可证 GPL-3.0
- 本版本：`0.9.2`（versionCode `2026102701`）
- 包名：`com.zdx8.clashnova`
- 与官方 FlClash 的差异：仅品牌名、包名、URL scheme、更新检查开关，共 8 处，完整 diff 见 [`changes/fluxlink-rebrand.patch`](changes/fluxlink-rebrand.patch)

## 下载

到 [Releases](../../releases/latest) 下载 `FluxLink-0.9.2-universal.apk`。

| 项 | 值 |
| --- | --- |
| 大小 | 144.3 MB（138 MiB） |
| SHA-256 | `39914220ef955a964dfb8b48eefca05be40bf1f37a222a5ecf6ac4192bd29996` |
| 支持架构 | arm64-v8a、armeabi-v7a、x86_64 |
| 系统要求 | Android 7.0（API 24）及以上 |
| 签名 | v2 + v3，RSA 4096，`CN=FluxLink` |
| 证书 SHA-256 | `b0a2f9c6cd148e5a7b7d2569ab4c6586b3253a810bff057a0f7152802df4f61e` |

## 安装

```bash
adb install FluxLink-0.9.2-universal.apk
```

或把 APK 传到手机后点击安装，需允许「安装未知来源应用」。

首次启动需同意免责声明，然后导入你自己的订阅链接。首次连接时系统会弹出一次 VPN 授权请求，选择允许即可。

## 与官方版的区别

1. 应用名 `FlClash` → `FluxLink`（桌面图标、通知、关于页统一）
2. 包名 `com.follow.clash` → `com.zdx8.clashnova`，可与官方版共存安装，配置互不影响
3. URL scheme `flclash://` → `fluxlink://`；仍保留 `clash://`、`clashmeta://` 以支持订阅一键导入
4. 已关闭上游更新检查：上游 Release 是另一签名的官方包，装上不会覆盖本包，因此不做提示
5. 使用独立签名密钥，**不能覆盖安装官方版，也不能继承官方版配置**
6. 应用图标沿用上游资源

## 已知限制

- 无自动更新，升级需手动下载新 APK 覆盖安装（同一签名，可直接覆盖）
- 体积较大：内置三套 CPU 架构的内核库
- 声明了定位权限，用于显示当前 Wi-Fi 名称；拒绝不影响代理功能
- 仪表盘加载时会向第三方 IP 查询服务请求一次公网 IP 归属信息，该结果只显示在本地界面

## 许可与源码

本项目遵循 **GPL-3.0**，许可证全文见 [`LICENSE`](LICENSE)。分发二进制时的源码提供方式见 [`SOURCE.md`](SOURCE.md)。

## 免责声明

本仓库仅为个人重编译存档，与上游作者无隶属关系，也未获得其背书。软件按「现状」提供，不附带任何担保。请遵守你所在地区的法律法规及所使用网络服务商的条款。
