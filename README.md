# NEON HEART · Hand Particle

一个纯前端的摄像头手掌交互粒子爱心。

## 特性

- MediaPipe Hand Landmarker 实时追踪手部 21 个关键点
- 根据手掌尺寸（5→17 掌宽 + 0→9 掌高）控制爱心大小
- GPU 优先，GPU 初始化失败自动回退 CPU
- 约 27–30 FPS 手部推理，Canvas 60 FPS 粒子渲染，避免把页面卡死
- 电脑 / Android / iPhone 响应式布局
- 摄像头画面默认隐藏，可手动打开预览
- 所有手部推理在浏览器本地执行
- Render Static Site 可直接部署

## 本地 VS Code 测试

不要直接双击 `index.html`。摄像头权限通常需要 `localhost` 或 HTTPS。

### 方法 A：VS Code Live Server

安装 Live Server 插件后，右键 `index.html` → **Open with Live Server**。

### 方法 B：Python

```bash
python -m http.server 5500
```

然后访问：

```text
http://localhost:5500
```

## GitHub

```bash
git init
git add .
git commit -m "feat: neon hand tracking particle heart"
git branch -M main
git remote add origin https://github.com/YOUR_NAME/neon-heart-hand.git
git push -u origin main
```

## Render

Render → **New → Static Site** → 连接这个 GitHub 仓库。

- Build Command: `echo 'Static site: no build step required'`
- Publish Directory: `.`
- Branch: `main`

Render Static Site 会自动获得 `https://你的服务名.onrender.com`，并且默认可在后续 push 后自动重新部署。

## 注意

首次打开页面必须允许摄像头权限。iPhone / iPad 等移动端必须使用 HTTPS；Render 默认提供 HTTPS。
