# LuluAgent 安装包

这里只发布编译好的 APK，源码和签名材料存放在独立的私有仓库。

[下载最新版本](https://github.com/leesama/lulu-dist/releases/latest)

鹿鹿 App 的「我的/设置 → 检查更新」会从本仓库读取最新版本。下载安装仍由用户确认，签名一致的新版可以直接覆盖安装并保留配置和数据。

## 自动发布

源码主分支每次推送都会触发 GitHub Actions 构建。发布新包时同时递增 `versionName` 和 `versionCode`，CI 会完成正式签名、校验 APK、上传附件，然后将新 Release 设为 Latest。

已发布的同版本安装包不会被覆盖。每个自动发布版本同时提供 `release-manifest.json`，记录版本号、构建提交、签名指纹和 APK 的 SHA-256。
