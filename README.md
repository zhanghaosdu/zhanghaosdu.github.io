# 张浩的个人学术主页

正式网址：https://zhanghaosdu.github.io

仓库：https://github.com/zhanghaosdu/zhanghaosdu.github.io

固定中文，Next.js + React + TypeScript + Tailwind CSS，支持深色模式、桌面及手机布局。

## 源码与发布文件

- `site-source.zip`：完整可运行源码；解压后即可修改配置并构建。
- `site-build.zip`：已经验证的静态网站构建产物。
- `.github/workflows/deploy.yml`：将构建包发布到 GitHub Pages。

源码与静态构建文件分开打包，避免网页上传造成目录结构丢失。源码不包含原始私人简历、密码、访问令牌或其他登录信息。

## 本地运行

需要 Node.js 20.9+，建议 Node.js 22；以及 pnpm。

```powershell
pnpm install
pnpm dev
```

## 修改内容

`content/profile.ts`：个人简介原文、经历、荣誉、服务、专利和动态。

`content/publications.ts`：全部 16 条成果，已合并 Google Scholar 的 15 条记录及简历中的 AGIRA；`selected: true` 的代表作排前。论文不显示外部链接或切换控件。

`content/projects.ts`：科研项目。

`app/globals.css`：字号、间距与布局。

最新动态位于个人简介后、论文前。主页学术经历仅展示山东大学博士后和博士经历；原始教育记录仍保留在配置及下载简历中。

## 更新网站

在源码目录运行：

```powershell
pnpm build
python scripts/package-pages.py
```

需要 Python 3。生成当前目录的 `site-source.zip` 与 `site-build.zip`；在 GitHub 仓库中上传替换这两个文件并提交，GitHub Actions 自动重新发布。请勿把 `node_modules`、`.next`、原始私人 PDF 或登录信息上传到仓库。

网站 SEO、分享地址、sitemap 默认使用正式 GitHub Pages 网址。公开简历位于 `public/cv/Hao-Zhang-CV.pdf`。

全部内容核对与来源说明见源码中的 `CONTENT-REVIEW.md`。

页面已移除下载简历按钮、论文副标题、论文信息核对说明及来源标记说明；原始参考数据仍保存在源码配置中。
