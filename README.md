# NasTV（影视中心 TV）

Android TV / 电视盒子的影视中心客户端。版本元数据通过 GitHub 仓库发布，App 内自动检查新版本并下载安装，不再需要 U 盘拷贝。

## 自动升级

- App 启动后每 6 小时最多检查一次 GitHub 的 `version.json`
- 菜单 →「检查更新（GitHub）」可手动检查
- 发现新版本 →「下载并安装」→ 系统安装器覆盖安装
- Android 8+ 首次安装需在系统设置里允许「影视中心」安装未知应用（App 会自动跳转）
- 元数据优先走 `api.github.com`，失败自动改用 `ghproxy.net` 镜像读 raw
- APK 本体走 NAS 局域网直链（`/nastv/NasTV-v*-b*.apk`），避开国内访问不稳定的 github.com 下载

## 版本号

`versionName = 主.次.构建号`，末位与 `versionCode` 一致，例如 `2.5.90 / b90`。

## 发布

1. 构建 `NasTV-v<versionName>-b<code>.apk`
2. 上传到 NAS `/vol1/1000/NAS 1/releases/nastv/`
3. 更新仓库根目录 `version.json`（versionCode/versionName/apkUrl/size/notes）

`version.json` 示例：

```json
{
  "versionCode": 90,
  "versionName": "2.5.90",
  "apkUrl": "http://192.168.1.200:15007/nastv/NasTV-v2.5.90-b90.apk",
  "size": 85116181,
  "notes": "更新说明"
}
```
