# 宋俊铎 · 个人主页

北京工商大学财政学专业在读本科生的个人主页，纯静态站点（HTML + CSS + 原生 JavaScript，无需构建），
可直接部署到 GitHub Pages。

## 目录结构

```
.
├── index.html              # 页面主体（所有文案都在这里）
├── assets/
│   ├── css/style.css       # 样式（含深/浅色两套主题变量）
│   └── js/main.js          # 交互脚本
├── .nojekyll               # 告诉 GitHub Pages 不要用 Jekyll 处理，直接发布静态文件
└── README.md
```

## 本地预览

直接双击 `index.html` 即可在浏览器中打开。

如需以本地服务器方式预览（更接近线上环境）：

```bash
# 有 Python 环境时
python -m http.server 8000
# 然后访问 http://localhost:8000
```

## 部署到 GitHub Pages

### 方式一：用户主页（推荐，地址最短）

1. 在 GitHub 新建一个仓库，仓库名必须是 `<你的用户名>.github.io`，例如 `songjunduo.github.io`。
2. 把本目录下的所有文件推送到该仓库的 `main` 分支：

   ```bash
   git init
   git add .
   git commit -m "init: personal homepage"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<你的用户名>.github.io.git
   git push -u origin main
   ```

3. 等待 1–2 分钟，访问 `https://<你的用户名>.github.io` 即可看到页面。

### 方式二：项目主页

1. 建一个任意名称的仓库，推送文件到 `main` 分支。
2. 进入仓库 **Settings → Pages**，Source 选择 **Deploy from a branch**，
   分支选 `main`、目录选 `/ (root)`，保存。
3. 稍等片刻，访问 `https://<你的用户名>.github.io/<仓库名>/`。

## 需要你手动修改的地方

| 位置 | 说明 |
| --- | --- |
| `index.html` 关于我 / 教育背景 / 关注方向 | 文案为通用模板，可按你的实际经历与兴趣调整 |
| `index.html` 课程与知识结构 | 按你所在年级的实际培养方案增删课程 |
| `index.html` 首屏头像 | 目前用「宋」字圆形色块占位。想换成照片：把图片放进 `assets/img/`，再把 `.avatar` 内的 `<span>宋</span>` 换成 `<img src="assets/img/avatar.jpg" alt="宋俊铎">`，并在 CSS 中给 `.avatar img` 加上 `width:100%;height:100%;object-fit:cover;border-radius:50%` |

## 当前部署状态

- 站点地址：<https://songjunduo.github.io/>
- 源码仓库：<https://github.com/songjunduo/songjunduo.github.io>
- 发布方式：GitHub Pages（legacy 构建，直接发布 `main` 分支根目录）

修改文件后推送到 `main` 分支，Pages 会自动重新构建，通常一分钟内生效。

## 已实现的功能

- 响应式布局，手机 / 平板 / 桌面均可正常浏览
- 深色 / 浅色主题切换，默认跟随系统，用户选择记录在 localStorage
- 顶部导航滚动吸顶、当前区块自动高亮、移动端汉堡菜单
- 区块滚动入场动画（对 `prefers-reduced-motion` 用户自动关闭）
- 一键复制邮箱、回到顶部按钮

## 许可

页面内容版权归宋俊铎所有；结构与样式可自由修改使用。
