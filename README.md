# 芝士分子 Cheesefans

`cheesefans.com` 的个人门户网站，用来收纳在线工具、实验项目和后续知识作品。

## 技术选型

- Astro：静态输出、SEO 友好、首屏简单，不需要为门户页引入完整前端运行时。
- TypeScript：保留类型检查能力，后续扩展组件和内容集合更稳。
- 原生 CSS：当前页面交互少，避免引入 UI 框架和额外样式依赖。
- 静态部署：无后端依赖，适合 Cloudflare Pages、Vercel、Netlify 或任意静态托管。

## 信息结构

- `https://cheesefans.com`：个人门户首页。
- `https://cube.cheesefans.com`：魔方模拟器。
- `https://score.cheesefans.com`：在线文本乐谱编辑器。

首页当前包含：

- 品牌首屏：说明“芝士分子 / Cheesefans”的定位。
- 在线工具入口：跳转到两个二级域名 app。
- 关于站点：解释命名和做工具的原则。
- 后续扩展：文章、实验室、关于我。

## 本地开发

```bash
npm install
npm run dev
```

`dev` 脚本会显式禁用 Astro telemetry，并关闭 Astro 在 agent 环境中的自动后台 dev server，避免本地受限目录或自动后台进程导致启动失败。

如果 PowerShell 执行策略拦截 `npm.ps1`，可以使用：

```bash
npm.cmd install
npm.cmd run dev
```

## 构建

```bash
npm run build
```

构建产物会输出到 `dist/`。

## 部署建议

推荐使用 Cloudflare Pages：

1. 将仓库推送到 GitHub。
2. 在 Cloudflare Pages 里连接该仓库。
3. 构建命令填写 `npm run build`。
4. 输出目录填写 `dist`。
5. 将自定义域名绑定到 `cheesefans.com`。

两个 app 可以分别作为独立 Pages 项目或独立静态站部署，并绑定：

- `cube.cheesefans.com`
- `score.cheesefans.com`
