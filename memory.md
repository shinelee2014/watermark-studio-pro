# Watermark Studio Pro 关键技术决策与踩坑记录 (memory.md)

## 💡 核心技术决策
1. **GitHub Pages 部署与根目录 index.html**：
   - 根目录的 `index.html` 直接作为 GitHub Pages 静态入口，`watermark-remover.html` 作为镜像备份；
   - 每次提交到 `main` 分支后，GitHub Pages 会在数十秒内自动重新构建并上线。
2. **多线程 Web Worker 采用 Blob URL 动态创建**：
   - 避免跨域或本地 `file://` 协议的安全限制，Worker 脚本内嵌在 HTML 的 `<script id="workerScript" type="text/javascript-worker">` 中，通过 `new Blob([...])` 和 `URL.createObjectURL` 实例化。
3. **局部 ROI 裁剪加速**：
   - 仅裁剪 Mask 选区及其外延 20px 上下文送入 Worker，极大减少多维数组遍历体积，4K 大图提速数十倍。

---

## ⚠️ 历史踩坑与避坑指南 (Pitfalls)
1. **【严重教训】多版本核心交互引擎一致性保障**：
   - 衍生或创建独立版本（如从在线单图版衍生本地批量版）时，**绝不可为了聚焦批量队列而对工具栏交互（画笔、橡皮擦 destination-out、矩形框选 marquee、魔棒吸附、抓手平移、撤销重做历史栈）做任何阉割或硬编码占位**；
   - 所有版本必须全量继承完整的画布工具调度与事件分发逻辑，并经过自动化多工具全流程测试后方可交付。
2. **Telea 算法中待修复像素自身权值排除**：
   - 在 Telea Fast Marching 遍历窄带插值时，必须通过 `if (dx === 0 && dy === 0) continue;` 和 `if (flags[np] !== 0) continue;` 严格排除待修复像素自身，否则由于距离为 0 导致自身原始水印颜色权重极大，产生白色残影。
3. **低对比度浅灰半透明水印定位**：
   - 浅灰色文字（如 AI 生成角标）在白色/米色背景上，不能仅依赖绝对亮度（Luminance）阈值；必须采用 Sobel 边缘梯度算子计算笔画密度，并提供方位快捷辅助标签与深度 OCR 识别。
4. **PowerShell 命令执行注意**：
   - Windows PowerShell 环境下组合命令使用 `;`，不要使用 `&&`。
