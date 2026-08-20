# Watermark Studio Pro 项目大纲与规范

## 📌 项目概况
- **项目定位**：专业级纯前端免安装图像去水印工作台 (Watermark Studio Pro)
- **在线演示 (GitHub Pages)**：https://shinelee2014.github.io/watermark-studio-pro/
- **GitHub 远程仓库**：https://github.com/shinelee2014/watermark-studio-pro
- **分支规范**：`main`（主分支，直接关联 GitHub Pages 自动部署）

---

## ⚡ 核心强制开发规则 (Mandatory Rules)

1. **【强制】代码修改同步自动推送 GitHub**：
   - 每次对话或任务中对本项目任何文件（`index.html`、`watermark-remover.html`、`watermark-remover-pro-local.html`、`README.md` 等）完成修改和本地验证后，**必须自动执行 `git add .`、`git commit` 并 `git push origin main` 同步推送到 GitHub 仓库**，确保 GitHub Pages 在线版与本地代码时刻保持 100% 实时同步。
2. **【强制】单文件零外部依赖架构**：
   - 必须保持 100% 纯前端本地内存运行，所有密集计算在 Web Worker 线程处理，严禁增加强制性后端服务器依赖。
3. **【强制】双版本维护机制**：
   - `index.html`（GitHub Pages 在线版 / 单图精修 / 双引擎文字定位）
   - `watermark-remover-pro-local.html`（本地批量旗舰版 / 批量多图队列 / 并发处理 / 批量导出）
   - 修改共有算法逻辑时，两版本需同步更新。

---

## 🛠️ 技术架构
- **算法层**：Telea FMM 快速行进法、增强型拉普拉斯偏微分扩散、半透明逆 Alpha 还原。
- **定位层**：Sobel 边缘梯度密度自适应扫描 + 浏览器端 AI 深度 OCR (Tesseract.js)。
- **渲染层**：Canvas 2D 视口系统（10%~1500% 无限缩放、平移抓手、前后卷帘对比分割线、历史快照撤销重做）。
