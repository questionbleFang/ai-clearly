# AI, Clearly

面向老年人的互动 AI 素养网站。纸艺拼贴风格、日常 AI 示例、术语解释、防诈骗练习和独立互动课程。

纯 HTML、CSS、JavaScript，无需 npm、API key、数据库或付费主机。已包含最新的花园提示词。

## 最简单的发布方式：网页上传

1. 在自己的 GitHub 账号下创建 **Public** 仓库，建议名为 `ai-clearly`。
2. 解压本压缩包，将其中的 `docs` 文件夹和 `README.md` 上传到仓库根目录。不要直接上传 ZIP，也不要多套一层 `ai-clearly-github` 文件夹。
3. 打开仓库 **Settings → Pages**。
4. 在 **Build and deployment → Source** 选择 **Deploy from a branch**。
5. 选择 **main** 分支、**/docs** 文件夹，然后 **Save**。
6. 等待 Pages 部署完成，使用 Settings → Pages 显示的地址。

普通项目仓库地址是 `https://你的用户名.github.io/ai-clearly/`。如果希望地址仅为 `https://你的用户名.github.io/`，仓库必须命名为 `你的用户名.github.io`（将“你的用户名”替换为真实 GitHub 用户名）。两种方式均支持本网站。

## 可选：GitHub Actions 自动部署

如果使用 Git 上传全部文件（包含 `.github/workflows/pages.yml`），请在 **Settings → Pages → Source** 选择 **GitHub Actions**，而不是上述分支方式。

之后向 `main` 推送更新即可自动部署；也可打开 **Actions → Deploy AI Clearly to GitHub Pages → Run workflow** 手动发布。首次上传后才开启 Pages 时，可以手动运行一次。

只选择一种部署方式。网页上传的初学者使用上面的分支方式即可，无需上传隐藏文件夹。

### Git 命令（在解压后的目录运行）

先创建空的 GitHub 仓库，替换下面地址里的 `YOUR_USERNAME`：

```bash
git init -b main
git add .
git commit -m "Add AI Clearly website"
git remote add origin https://github.com/YOUR_USERNAME/ai-clearly.git
git push -u origin main
```

## 修改网站

| 文件 | 用途 |
| --- | --- |
| `docs/index.html` | 首页、介绍、术语解释、防诈骗内容、来源 |
| `docs/home.css` | 首页颜色、布局、字体、响应式样式 |
| `docs/home.js` | 日常提示词、复制按钮、防诈骗反馈、字号控制 |
| `docs/lesson.html` | 课程页面结构与研究来源 |
| `docs/app.js` | 课程内容、题目、答案与进度 |
| `docs/styles.css` | 课程基础样式 |
| `docs/lesson-theme.css` | 课程的主题样式 |
| `docs/assets/family-collage.png` | 首页拼贴插画 |

可在 GitHub 打开对应文件，点击铅笔编辑并提交。按已选择的 Pages 发布方式，提交到 `main` 后会自动更新网站。

所有本地资源使用相对路径，适配项目子目录、用户名主页和自定义域名。修改时避免把路径写成 `/home.css` 这类从域名根目录开始的形式。

## 本地预览

安装 Python 后，在仓库根目录运行：

```bash
python3 -m http.server 8000 --directory docs
```

打开 `http://localhost:8000`。复制到剪贴板功能需要浏览器允许，正式 Pages 网站使用 HTTPS。

## 自定义域名

免费 `github.io` 地址无需购买域名。购买自己的域名后，在 **Settings → Pages → Custom domain** 设置，并按 GitHub 官方说明配置 DNS。不要把 ChatGPT Sites 的 DNS 记录用于 GitHub Pages。

本仓库没有预设 CNAME，不会绑定不属于你的域名。采用 Actions 部署时，如需要 CNAME 文件，请将真实域名写入 `docs/CNAME`。

## 进度与隐私

课程进度和字号使用浏览器 localStorage。网站没有真实 AI 接口；日常提示词是示例。迁移域名后，旧域名的浏览器进度不会自动迁移。不包含分析追踪、用户账号、服务器或密钥。

当前 ChatGPT Sites 网站不会因上传本仓库而改变。两个站点部署后各自独立，之后修改需要更新各自版本。

## 内容与素材

内容保留官方防诈骗、隐私和 AI 研究来源。首页插画为 AI 生成，视觉方向参考 Calgary Seniors；本项目与该机构没有隶属或背书关系，未复用其品牌素材。

这是教育项目，尚未完成老年用户可用性评估。未指定开源许可证；公开仓库不等于自动授予他人任意复用许可，项目所有者可后续选择许可证。

## 官方文档

- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
