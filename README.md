# NasTV（影视中心 TV）

Android TV / 电视盒子的影视中心客户端。APK 通过 GitHub Releases 发布，App 内自动检查新版本并下载安装，不再需要 U 盘拷贝。

## 自动升级

- App 启动后每 6 小时最多检查一次 GitHub Releases
- 菜单 →「检查更新（GitHub）」可手动检查
- 发现新版本 →「下载并安装」→ 系统安装器覆盖安装
- Android 8+ 首次安装需在系统设置里允许「影视中心」安装未知应用（App 会自动跳转）
- GitHub 资产下载失败时自动改用 `ghproxy.net` 镜像重试

## 版本号

`versionName = 主.次.构建号`，末位与 `versionCode` 一致，例如 `2.5.89 / b89`。

## 发布

每个版本在 GitHub Releases 上传 `NasTV-v<versionName>-b<code>.apk`，App 从最新 Release 的 APK 资产读取版本号。
