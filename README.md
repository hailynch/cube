# 奥熙的魔方

<p>
  <img alt="platform" src="https://img.shields.io/badge/platform-Web%20%2F%20PWA%20%2F%20Linux-blue">
  <img alt="tech" src="https://img.shields.io/badge/WebGL-渲染引擎-orange">
  <img alt="orders" src="https://img.shields.io/badge/魔方阶数-1%20%E2%80%93%20500%20%E9%98%B6-green">
  <img alt="license" src="https://img.shields.io/badge/license-MIT-brightgreen">
</p>

星空背景下的 N 阶魔方模拟器，基于 WebGL 渲染，支持 **1 – 500 阶**任意阶数魔方的打乱、求解、图案拼字与自动演示。既是网页应用（PWA），也可打包为 Linux 桌面应用（Electron）。

## 功能特性

- **任意阶数**：1 – 500 阶自由切换，阶数越高挑战越大
- **随机打乱**：可自定义打乱步数，随机生成打乱状态
- **自动还原**：按打乱与拧动步骤的逆序回放，任意阶数都能复原（不追求最短路径）
- **图案模式**：在顶面用蓝色贴纸拼出文字（白底），自定义输入文字（最多 12 字符，如「LEO」「奥熙」），建议 12 阶以上使用，阶数越高越清晰；图案打乱后同样可被还原
- **自动演示**：播放 / 暂停 / 单步执行 / 瞬间完成
- **流畅交互**：魔方上拖拽拧动层、空白处或右键拖拽旋转视角、滚轮/双指缩放、双击画布复位视角
- **离线可用**：PWA + Service Worker 缓存外壳与字体，支持手机「添加到主屏幕」

## 网页版（PWA）

纯静态文件部署，无需构建：`index.html`、`manifest.webmanifest`、`sw.js`、`icons/`。

本地预览（Service Worker 需要 http(s) 环境）：

```bash
npx serve .        # 或任意静态服务器
```

## 桌面版（Electron）

```bash
npm install
npm start          # 本地运行
npm run dist       # 打包 Linux AppImage 到 dist/
```

## 操作说明

### 鼠标 / 触摸

| 操作 | 效果 |
|------|------|
| 在魔方上拖拽 | 拧动一层 |
| 空白处 / 右键拖拽 | 旋转视角 |
| 滚轮 / 双指捏合 | 缩放 |
| 双击画布 | 复位视角 |

### 快捷键

| 按键 | 效果 |
|------|------|
| `空格` | 播放 / 暂停 |
| `S` | 随机打乱 |
| `R` | 自动还原 |
| `V` | 切换拧动 / 视角模式 |

## 目录结构

```
index.html            应用本体（单文件，含全部逻辑）
manifest.webmanifest  PWA 清单
sw.js                 Service Worker（离线缓存）
main.js               Electron 主进程
icons/                应用图标（SVG 源 + PNG 各尺寸）
```

## 许可证

[MIT](LICENSE)

## 作者

whg（[hailynch](https://github.com/hailynch)）
