# scanditest

这是一个使用 Astro 搭建的瑞典语产品测评/导购静态站点。

线上域名：

```txt
https://www.scandi-test.com
```

## 项目结构

Astro 会根据 `src/pages/` 下的文件生成路由。

- `src/pages/index.astro` - 首页，包含站点介绍、评测方法和最新测评入口。
- `src/pages/robotdammsugarna-test-2026.astro` - 机器人吸尘器长篇测评页。
- `src/layouts/SiteLayout.astro` - 全站公共布局，统一管理 HTML 外壳、GTM、页眉和页脚。
- `src/components/BaseHead.astro` - SEO、canonical、Open Graph 和 Twitter meta。
- `src/components/Header.astro` / `src/components/Footer.astro` - 公共页眉和页脚。
- `src/styles/global.css` - 全局样式、主题色和响应式样式。
- `public/static/images/` - 测评页使用的产品图和作者图。

## 环境变量

GTM 统一配置在 `src/layouts/SiteLayout.astro` 中，不需要每个页面单独添加。

本地开发时可以在项目根目录创建 `.env` 文件；线上部署时在 Cloudflare 环境变量中配置同名变量：

```txt
PUBLIC_GTM_ID=GTM-XXXXXXX
```

如果没有配置 `PUBLIC_GTM_ID`，页面不会输出 GTM 代码。

## SEO

站点正式域名配置在 `astro.config.mjs`：

```js
site: "https://www.scandi-test.com"
```

Astro 会用这个地址生成 canonical URL 和 sitemap。

sitemap 地址：

```txt
/sitemap-index.xml
```

线上完整地址：

```txt
https://www.scandi-test.com/sitemap-index.xml
```

## 常用命令

以下命令都在项目根目录执行：

| Command                           | Action                                      |
| :-------------------------------- | :------------------------------------------ |
| `npm install`                     | 安装依赖                                  |
| `npm run dev`                     | 启动本地开发服务，默认地址 `localhost:4321` |
| `npm run build`                   | 构建生产版本到 `./dist/`                  |
| `npm run preview`                 | 本地预览构建结果                          |
| `npm run build && npm run deploy` | 构建并部署到 Cloudflare                   |
