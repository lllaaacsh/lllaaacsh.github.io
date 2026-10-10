# 个人学术主页

纯静态 HTML/CSS，不需要 Jekyll 或任何构建步骤，样式改自 [Jon Barron 的模板](https://github.com/jonbarron/jonbarron_website)。

## 文件结构

```
index.html          主页内容（所有要改的东西都在这里）
stylesheet.css      样式（颜色变量在文件开头，自动适配深色模式）
images/             头像、论文缩略图、favicon
files/              CV.pdf、bibtex 等
.nojekyll           让 GitHub Pages 直接发布原始文件
```

## 修改内容

1. **头像**：直接替换 `images/profile.jpg`（正方形照片效果最好）。
2. **CV**：放到 `files/CV.pdf`。
3. **论文**：复制一个 `<div class="paper">…</div>` 块再改内容。缩略图放进 `images/`，宽高比约 16:10 效果最好。
   - 想让某篇论文显示黄色高亮背景，就写成 `class="paper highlight"`
   - 缩略图也可以换成循环播放的视频：`<video src="images/demo.mp4" autoplay loop muted playsinline></video>`
4. 不需要的版块（News / Awards / Service 等）直接删掉对应的 `<section>`。

## 本地预览

```bash
python3 -m http.server 8000
```

然后打开 http://localhost:8000（VS Code Remote 会自动转发端口）。

## 部署到 GitHub Pages

1. 在 GitHub 新建一个仓库，名字**必须**是 `<你的GitHub用户名>.github.io`
2. 推送：
   ```bash
   git init
   git add .
   git commit -m "Initial homepage"
   git branch -M main
   git remote add origin git@github.com:<用户名>/<用户名>.github.io.git
   git push -u origin main
   ```
3. 仓库 Settings → Pages → Source 选 `Deploy from a branch`，分支选 `main` / `(root)`
4. 等一两分钟后访问 `https://<用户名>.github.io/`
