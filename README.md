# Michael Smith — Cosmic Portfolio (Static Version)

这是一个专为独立设计师与数字创作者量身定制的高端暗黑风格个人作品集网页。该项目已重构为**极简的纯静态网页结构**（无需运行任何编译命令或配置环境），非常适合完全没有代码背景的创作者使用和维护。

## 📁 目录文件结构

网站仅由两个主要代码文件组成，双击即可打开预览：
* `index.html` — 网站的骨架与内容（包括文字、图片链接以及所有的动效控制逻辑）。
* `index.css` — 网站的色彩系统、自定义动效基础配置以及细节微调。

---

## ✍️ 个人内容修改指南

您可以直接用文本编辑器（如 Notepad++、VS Code 或是电脑自带的记事本）打开 `index.html` 来修改所有的内容。

### 1. 修改您的名字与职业
* 在 `index.html` 中搜索 `Michael Smith`，将其替换为您的名字。
* 搜索 `Creative`，您可以在 `<script>` 标签的 `HERO_ROLES` 数组中修改循环滚动的职业名称（例如 `"UI/UX Designer", "Product Designer", "Visual Artist"`）。

### 2. 更换作品展示图片与标题
* 寻找 `SECTION 3: SELECTED WORKS` 区块。
* 您可以看到有 4 个项目卡片（`work-card`）。修改其中的 `src="..."` 属性来换成您自己的 UI 作品图片链接。
* **推荐**：您可以在此文件夹内新建一个 `images` 文件夹，将您的作品图片放进去，然后将链接改为 `./images/project1.png` 等本地相对路径。

### 3. 修改社交链接与邮箱
* 在文件底部搜索 `hello@michaelsmith.com`，将其替换为您自己的工作邮箱。
* 在 footer 栏中，修改社交平台对应的跳转链接（把 `https://twitter.com` 等换成您的个人主页）。

---

## ☁️ 如何部署到 Cloudflare Pages 并在 GitHub 备份？

### 第一步：在 GitHub 建仓并上传
1. 登录您的 [GitHub 官网](https://github.com/) 账号。
2. 点击右上角 **`+`** -> **`New repository`**（新建仓库）。
3. 起个名字（例如 `portfolio`），点击 **`Create repository`** 创建。
4. 在您的本地项目文件夹内打开终端（Git Bash 或 PowerShell），运行以下命令将这两个文件推送到 GitHub：
   ```bash
   git init
   git add .
   git commit -m "upload portfolio"
   git branch -M main
   git remote add origin 您的仓库链接(以.git结尾)
   git push -u origin main
   ```

### 第二步：一键绑定 Cloudflare Pages
1. 登录 [Cloudflare 控制台](https://dash.cloudflare.com/)。
2. 点击左侧导航栏 **`Workers & Pages`** -> **`Create`** -> **`Pages`** -> **`Connect to Git`**。
3. 选择您刚才在 GitHub 上建好的 `portfolio` 仓库。
4. **非常重要**：在 **Build settings**（构建设置）里：
   * **Framework preset**（框架预设）：选择 **`None`**。
   * **Build command**（构建命令）：**留空（什么都不填）**。
   * **Build output directory**（打包输出目录）：**留空（什么都不填）**。
5. 点击 **`Save and Deploy`**。

5秒钟后，您的网站就成功发布到全球互联网了！您以后在本地修改文件后，只需通过 Git 重新 Push 到 GitHub，网站便会瞬间全自动更新。
