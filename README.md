# 黄金交易会议看板公开版

这是可部署到公网的 PWA 静态版本。部署后，任何人都可以通过公开网址访问，并可在手机上添加到主屏幕。

## 文件

- `gold-trend.html`：主看板
- `manifest.webmanifest`：PWA 安装配置
- `sw.js`：离线缓存与接口降级
- `gold-app-icon.svg`：App 图标

## 推荐部署方式

### Cloudflare Pages

1. 新建 GitHub 仓库，例如 `gold-meeting-dashboard`。
2. 上传本目录全部文件到仓库根目录。
3. 打开 Cloudflare Pages，连接该仓库。
4. Build command 留空。
5. Output directory 填 `/`。
6. 部署后得到公开网址。

### Vercel

1. 新建 GitHub 仓库并上传本目录。
2. 在 Vercel 导入该仓库。
3. Framework 选择 `Other`。
4. Build command 留空。
5. Output directory 留空或填 `.`。

### GitHub Pages

1. 新建公开仓库并上传本目录。
2. Repository Settings -> Pages。
3. Source 选择 `Deploy from a branch`。
4. Branch 选择 `main`，folder 选择 `/root`。
5. 访问生成的网址，例如 `https://用户名.github.io/仓库名/gold-trend.html`。

## 公开版限制

公开静态版可以显示 TradingView 组件和网页内策略内容，但不能读取你本机 Chrome 标签、不能调用本地 `localhost` Python 后台，也不能直接接入未授权的金十实时接口。

如果要让所有人也使用实时后台、AI 助手和新闻接口，需要再部署一个后端服务，并接入合法行情/新闻 API。
