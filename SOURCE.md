# 源码提供声明（GPL-3.0 第 6(b) 条）

本仓库分发的 `FluxLink-0.9.2-universal.apk` 是以下开源代码的二进制编译产物，按 **GNU General Public License v3.0** 分发：

- 上游项目：<https://github.com/chen08209/FlClash>，tag `v0.9.2`，commit `7fd417fb9a9a277c6a9339a8ac87f907df7c25f7`
- 内核子模块：<https://github.com/chen08209/Clash.Meta>，commit `c5062921054902b25215a6a933e72ccd714c9bfa`（mihomo fork）
- 本仓库对上游所做的全部修改：见 [`changes/fluxlink-rebrand.patch`](changes/fluxlink-rebrand.patch)，共 22 个文件、191 行新增、134 行删除

## 书面要约

根据 GPLv3 第 6(b) 条，本仓库维护者作出如下要约：

> 任何第三方均可向仓库维护者索取本二进制对应的**完整源码**（Modified Source），有效期自 2026-10-27 起不少于三年。
> 索取方式：在本仓库提交 Issue，标题注明「Source request」。
> 提供形式：与上游 `v0.9.2` 同构的完整源码归档（含 `core/Clash.Meta` 子模块内容、全部构建脚本与补丁），通过文件传输或下载链接交付，不收取任何费用（不含接收方的网络费用）。

## 如何自行复现

1. 取上游源码：`git clone --depth 1 --branch v0.9.2 https://github.com/chen08209/FlClash.git`
2. 初始化内核子模块：`git submodule update --init --depth 1 core/Clash.Meta`
3. 应用补丁：`git apply changes/fluxlink-rebrand.patch`
4. 准备签名：生成自己的 keystore，并在 `android/local.properties` 写入 `storePassword` / `keyAlias` / `keyPassword`
5. 构建：`flutter build apk --release --dart-define=APP_ENV=stable`

工具链版本（本包实测）：Flutter 3.47.6、JDK 21、Gradle 9.8.0、AGP 9.4.1、Go 1.27.1、NDK 28.2.13676358。
