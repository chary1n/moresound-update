# 摩声 · 更新源

这个仓库只放更新清单和安装包，源码不在这里。

- `update.json`：App 启动时读的更新清单（版本、构建号、更新内容、安装包地址）
- Releases：每个版本的安装包，文件名与清单里的地址一致

App 从这些地址依次尝试读取清单：GitHub Releases 的 latest 接口、
本仓库 main 分支的 `update.json`（raw 与 jsDelivr）。

发布新版本：改 `app.json` 的 `version` / `android.versionCode` 后重新出包，
在源码仓库执行 `scripts/publish-update.sh <apk> notes.txt`，
把生成的 `update.json` 提交到这里，安装包作为 `v<版本>` 的 Release 资源上传。
