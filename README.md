# 奥熙的魔方

星空背景下的 N 阶魔方模拟器：打乱、求解、图案模式（在魔方表面显示 LEO / 奥熙等文字）与自动演示。

## 网页版（PWA）

静态文件即可部署：`index.html`、`manifest.webmanifest`、`sw.js`、`icons/`。

本地预览：

```bash
npx serve .        # 或任意静态服务器（Service Worker 需要 http(s) 环境）
```

支持离线（Service Worker 缓存外壳与字体）、手机"添加到主屏幕"。

## 桌面版（Electron）

```bash
npm install
npm start          # 本地运行
npm run dist       # 打包 Linux AppImage 到 dist/
```

快捷键：`空格` 播放/暂停，`S` 打乱，`R` 求解，`V` 切换视角/拧动模式。

## 目录结构

```
index.html            应用本体（单文件，含全部逻辑）
manifest.webmanifest  PWA 清单
sw.js                 Service Worker（离线缓存）
main.js               Electron 主进程
icons/                应用图标（SVG 源 + PNG 各尺寸）
```
