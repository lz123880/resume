# 李政 · 个人简历网页

单文件静态简历网站：`index.html`（内联 CSS，无需任何构建工具），另附同内容的 Markdown 版本 `resume.md`。

> 已部署线上地址：**https://lz123880.github.io/resume/** ｜ 仓库：**https://github.com/lz123880/resume**

## 仓库结构

```
.
├── index.html   # 简历网页（单文件，内联 CSS）
├── resume.md    # 同内容的 Markdown 版本
└── README.md    # 本说明文件
```

## 如何本地预览

方式一（最简单）：直接双击 `index.html` 用浏览器打开。

方式二（推荐，体验与线上一致）：

```bash
# 进入本仓库目录后任选其一：
python -m http.server 8000
# 或
npx serve .
```

然后浏览器访问 <http://localhost:8000>。

## 如何修改内容

1. 用任意编辑器（VS Code / 记事本均可）打开 `index.html`。
2. 所有需要替换的占位信息均以 `【待补充…】` 黄色高亮标注，全文搜索 `【` 即可逐个定位替换：
   - 顶部：所在城市、GitHub 用户名；
   - 技能：可视化工具；
   - 教育背景：主修课程、成绩排名；
   - 工作经历：订单量、满意度数据；
   - 项目经历：项目名称、时间、数据规模、结论、链接；
   - 所获奖项。
3. 修改姓名、电话、邮箱：搜索 `李政`、`18788605564`、`2738415526@qq.com`。
4. 头部圆形区域当前显示姓名首字，如需换成个人照片，把 `<div class="avatar">李政</div>` 替换为
   `<img class="avatar" src="photo.jpg" alt="李政的照片">`，并把照片放进仓库同目录。
5. 改完 Markdown 版 `resume.md` 保持与网页内容一致即可。

## 导出 PDF

浏览器打开页面后按 `Ctrl + P`（macOS：`Cmd + P`）→ 目标打印机选"另存为 PDF"→
勾选"背景图形"（保留深蓝头部）→ 保存。已内置 `@media print` 样式，A4 单栏排版不会乱。

## 如何发布到 GitHub Pages

### 第 1 步：创建仓库

登录 [github.com](https://github.com) → 右上角 **+** → **New repository**。

**仓库命名建议（二选一）：**

| 方案 | 仓库名 | 访问地址 | 适用 |
|------|--------|----------|------|
| 用户主页站点（推荐） | `<你的用户名>.github.io` | `https://<你的用户名>.github.io` | 想要最短、最正式的简历链接 |
| 项目站点 | `resume` 或 `lizheng-resume` | `https://<你的用户名>.github.io/resume/` | 想把简历当作普通项目仓库 |

可见性选 **Public**（GitHub Pages 免费版要求），不要初始化 README（本地已有）。

### 第 2 步：推送代码

```bash
cd 本仓库目录
git init
git add .
git commit -m "feat: 个人简历网页"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

> 首次推送会弹出 GitHub 登录授权；若已安装 GitHub Desktop，也可直接用其 "Publish repository" 按钮完成。

### 第 3 步：开启 GitHub Pages

1. 仓库页面 → **Settings** → 左侧 **Pages**；
2. **Source** 选 `Deploy from a branch`；
3. **Branch** 选 `main`、目录选 `/ (root)` → **Save**；
4. 等待 1–2 分钟，页面顶部会出现访问地址：
   - 用户站点：`https://<你的用户名>.github.io`
   - 项目站点：`https://<你的用户名>.github.io/resume/`

### 第 4 步（可选）：自定义域名

Settings → Pages → Custom domain 填入你的域名，并在域名服务商处添加 CNAME 记录指向 `<你的用户名>.github.io`。

## 更新简历

以后修改内容后重新发布：

```bash
git add .
git commit -m "update: 更新简历内容"
git push
```

GitHub Pages 会自动重新部署，约 1 分钟后线上生效。
