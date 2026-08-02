# Kaneo for LazyCat

这是 [Kaneo](https://github.com/usekaneo/kaneo) 的懒猫微服 LPK v2 打包项目，包名为 `community.lazycat.app.kaneo`。

## 功能

- 使用 PostgreSQL 16 持久化项目数据。
- 从 `ghcr.io/usekaneo/kaneo` 自动发现 Kaneo 稳定版，通过 `ghcr.1ms.run/usekaneo/kaneo` 加速拉取并校验镜像 digest；PostgreSQL 镜像不参与自动更新。
- 记录成功注册、登录或修改后的凭据，并在登录页自动填充。
- 接入懒猫文件选择器，覆盖 Kaneo 的文件导入、上传和下载入口。
- GitHub Actions 只发布到喵喵商店，不发布到官方商店。

## 本地构建

```bash
lzc-cli project release -o .lazycat-build/kaneo.lpk
lzc-cli lpk info .lazycat-build/kaneo.lpk
```

## 自动发布

工作流使用 `ca-x/lazycat-github-action@v1`，需要仓库或组织提供以下 GitHub Secrets：

- `APPSTORE_URL`
- `APPSTORE_TOKEN`

发布产物使用版本化文件名 `community.lazycat.app.kaneo-v<version>.lpk`。
