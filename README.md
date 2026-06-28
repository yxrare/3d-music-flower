# 3D Music Flower

一个基于 Three.js 的浏览器端 3D 音乐粒子花。页面会生成高密度粉末感花束，上传本地音频后，花朵会从种子状态逐步绽放，并根据音乐频谱产生呼吸、闪烁和隐藏几何律动。

## Features

- 纯前端单文件实现，直接打开 `index.html` 即可运行
- Three.js 粒子系统绘制多花冠、花芯、枝叶和微尘
- 支持上传或拖放本地音频文件
- 支持多首音频播放队列
- 音频频谱驱动花朵缩放、粒子闪烁和隐藏数学轨迹
- 根据设备能力自动降低粒子数量，移动端更稳
- 无需后端，适合 GitHub Pages / Vercel / Netlify 静态部署

## Preview

打开页面后会先看到静态 3D 花束。选择或拖入音乐文件后，花束会收拢并随音乐重新生长。

## Quick Start

直接用浏览器打开：

```bash
open index.html
```

如果浏览器对本地文件权限比较严格，也可以启动一个本地静态服务：

```bash
python3 -m http.server 8080
```

然后访问：

```text
http://localhost:8080
```

## Usage

1. 点击左下角 `Having a moment` 选择一个或多个音频文件。
2. 也可以把音频文件直接拖进页面。
3. 点击播放按钮暂停或继续。
4. 上传多首歌时，页面会按选择顺序自动播放。

所有音频都只在本地浏览器中读取，不会上传到服务器。

## Tech Stack

- HTML / CSS / JavaScript
- Three.js r128
- Web Audio API
- CanvasTexture 粒子贴图

## Deploy

### GitHub Pages

1. 把仓库推送到 GitHub。
2. 进入仓库 `Settings -> Pages`。
3. Source 选择主分支和根目录。
4. 保存后等待 GitHub Pages 构建完成。

### Static Hosting

这个项目没有构建步骤。把 `index.html` 放到任意静态托管服务即可。

## Customization

常用可调参数都在 `index.html` 中：

- `particleBudget`：粒子数量上限
- `bloomDefs`：花朵位置、大小、倾斜和绽放顺序
- `stemDefs`：枝干位置和曲率
- `shapes`：隐藏粒子的数学轨迹模式
- `material.size`：粒子基础大小

## Notes

页面通过 CDN 加载 Three.js。如果离线运行，需要把 Three.js 下载到本地并修改脚本引用。
