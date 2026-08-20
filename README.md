# 🧽 Watermark Studio Pro

<p align="center">
  <b>100% 纯前端本地运行 · 零依赖 · 隐私安全 · 毫秒级高保真去水印工作台</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/Platform-GitHub%20Pages%20%7C%20Local-10b981.svg" alt="Platform">
  <img src="https://img.shields.io/badge/Status-Production%20Ready-success.svg" alt="Status">
  <img src="https://img.shields.io/badge/Privacy-100%25%20In--Browser%20Memory-purple.svg" alt="Privacy">
</p>

---

## 🌟 核心特性 (Features)

- 🔒 **100% 隐私安全**：所有图像计算均在浏览器本地内存中完成，**绝不上传任何服务器**，断网亦可顺畅使用。
- ⚡ **三大高保真算法引擎**：
  - **Telea 快速行进法 (FMM Inpainting)**：沿法线与梯度插值，保全背景细节与纹理，告别传统高斯模糊“毛玻璃感”。
  - **边缘感知拉普拉斯扩散 (Laplacian Diffusion)**：偏微分平滑扩散，适用于大面积纯色与平坦渐变背景。
  - **AI 半透明逆 Alpha 还原 (Reverse Alpha Blending)**：基于代数逆变换，针对 Gemini、Midjourney 等半透明角标 **100% 像素级无损还原**。
- 📝 **文字水印智能定位与消除 (Text Watermark Locator)**：
  - 支持直接输入文字（如 `AI生成`、`AI Generated`、`小红书` 等）；
  - **双引擎定位**：集成 **Sobel 边缘梯度自适应定位 (0ms)** 与 **浏览器端 AI 深度 OCR (Tesseract.js)**，支持全图扫描与左下/右下角标自适应锁定。
- 🔍 **专业修图画布视口 (Studio Viewport)**：
  - 鼠标滚轮中心缩放（10% ~ 1500%）、空格拖拽平移；
  - 画笔粗细指示圆环光标、前后卷帘对比分割线、历史快照撤销/重做 (`Ctrl+Z` / `Ctrl+Y`)。
- 📦 **双版本矩阵**：
  - **🌐 GitHub Pages 在线版 (`index.html`)**：零等待秒开，适合单图快速处理；
  - **⚡ 本地批量旗舰版 (`watermark-remover-pro-local.html`)**：支持一次性导入数十张图片，批量多线程并发消除与批量导出。

---

## 📊 版本对比 (Editions Comparison)

| 功能特性 | 🌐 GitHub Pages 在线版 (`index.html`) | ⚡ 本地批量旗舰版 (`watermark-remover-pro-local.html`) |
| :--- | :---: | :---: |
| **部署方式** | GitHub Pages 直接在线访问 / 单文件打开 | 本地离线运行 / 双击即用 |
| **首屏加载速度** | 极速秒开（文件体积几十 KB） | 本地秒开 |
| **多图批量队列** | 单图精修模式 | ✅ 支持 10~50 张多图队列排队 |
| **批量一键去除** | 手动逐张 | ✅ 一键批量全自动并发消除 |
| **批量打包导出** | 单图导出 (WebP/PNG/JPG) | ✅ 批量顺序导出所有处理结果 |
| **文字水印定位** | ✅ 边缘自适应 + 深度 OCR | ✅ 文字水印同步锁定 |
| **数据隐私** | 100% 浏览器内存（无后端） | 100% 本地内存运行 |

---

## ⌨️ 常用快捷键 (Hotkeys)

| 快捷键 | 功能说明 |
| :--- | :--- |
| `B` | 切换到 **涂抹画笔** 工具 |
| `E` | 切换到 **橡皮擦** 工具 |
| `R` | 切换到 **矩形框选** 工具 |
| `W` | 切换到 **色彩吸附魔棒** 工具 |
| `H` 或 `空格 + 鼠标拖拽` | 画布平移抓手 |
| `[` / `]` | 快速缩小 / 放大画笔粗细 |
| `Ctrl + V` | 直接从剪贴板粘贴截图导入 |
| `Ctrl + Z` / `Ctrl + Y` | 撤销 / 重做 (支持 16 步历史栈) |
| 按住 `\` 键 | 快速对比修复前原图 |
| `Ctrl + S` | 一键导出当前处理后图像 |
| `Esc` | 清空当前已绘制选区 |

---

## 🚀 GitHub Pages 快速部署指引

只需 3 步，即可将本项目部署为永久免费、随时随地可用的去水印在线工具：

### 1. 推送代码到 GitHub
在项目根目录下执行：
```bash
git init
git add .
git commit -m "feat: initial release of Watermark Studio Pro"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<你的仓库名>.git
git push -u origin main
```

### 2. 开启 GitHub Pages
1. 打开您的 GitHub 仓库页面，点击右上角的 **Settings**；
2. 在左侧侧边栏中点击 **Pages**；
3. 在 **Build and deployment** 下方的 **Branch** 选择：
   - 分支：`main`
   - 目录：`/(root)`
4. 点击 **Save** 保存。

### 3. 即刻在线体验
等待 30 秒后刷新页面，您将获得专属的公开访问网址：
`https://<你的用户名>.github.io/<你的仓库名>/`

---

## ⚖️ 开源协议 (License)

本项目采用 [MIT License](LICENSE) 开源协议。无论是个人使用还是商业集成均可自由使用与修改。
