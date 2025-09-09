
# Lottie 帧率修改与预览工具（GitHub + Vercel 一键上线）

- 单页应用：`index.html`
- 功能：上传 Lottie JSON → 修改帧率（3 种模式）→ 预览改前/改后动画 → 下载处理结果（在本地浏览器执行，文件不上传服务器）
- 播放器：依赖线上 `lottie-web` CDN

## 快速部署

### GitHub
1. 新建一个公开仓库（或私有也行）。
2. 上传本目录的所有文件，确保主页文件名为 **index.html**。

### Vercel
- **方式一：GitHub 导入**
  1) 登陆 [vercel.com](https://vercel.com) → New Project → Import Git Repository。
  2) 选择刚刚的 GitHub 仓库，Framework 选 **Other**（或静态），Build/Output 保持默认。
  3) Deploy 完成后会得到 `https://xxx.vercel.app`。

- **方式二：CLI**
  ```bash
  npm i -g vercel
  vercel login
  vercel deploy --prod
  ```

## 自定义域名（可选）
在 Vercel 项目 **Settings → Domains** 添加你的域名，按提示在 DNS 里增加 CNAME。

## 注意
- 如果你需要 **纯离线**（不依赖 CDN）版本，请在仓库 issue 提出或自行将 lottie-web 的 `lottie.min.js` 以 `<script>` 内联到 `index.html`。
- 本工具不会上传你的 JSON，所有处理在浏览器完成。
