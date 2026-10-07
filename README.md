<div align="center">

# 🎛️ BIT AUDIO WORKSTATION

### 复古像素风 · 纯前端 H5 · 音频处理工作站

[![Version](https://img.shields.io/badge/STABLE-1.7.1-00ff88?style=for-the-badge&logo=github)](https://github.com/114514gph/BIT-AUDIO-WORKSTATION/releases)
[![License](https://img.shields.io/badge/CC%20BY--NC--SA%204.0-ff0066?style=for-the-badge&logo=creativecommons)](LICENSE)
[![Platform](https://img.shields.io/badge/Web%20%7C%20Mobile-00aaff?style=for-the-badge&logo=googlechrome)](#)
[![Audio](https://img.shields.io/badge/Web%20Audio%20API-ffaa00?style=for-the-badge&logo=webaudio)](#)

---

</div>

> 🎮 **像玩游戏一样处理音频** — 8-bit 降采样、实时频谱仪、DJ 录制、随机芯片音乐生成……所有处理均在浏览器本地完成，无需上传服务器，隐私安全。

---

## ✨ 核心亮点

| 🏗️ 纯前端 | 🎨 像素风 | 📱 自适应 | 🔒 隐私安全 |
|:---------:|:---------:|:---------:|:-----------:|
| 单文件 HTML，无框架依赖 | 复古 CRT 扫描线 + 霓虹配色 | 电脑/手机自动适配布局 | 音频不上传，本地处理 |

---

## 🎛️ 功能特性

### 音质处理

| 功能 | 说明 |
|:----:|------|
| 🎚️ **8-bit 降采样** | 1~8 bit 量化 + 1~64x 降采样，复古芯片音质 |
| 🌊 **Dither 抖动** | TPDF 噪声，低比特量化时减少量化失真 |
| 🔇 **降噪** | 自适应噪声门 + 高频嘶声压制 |
| 🎚️ **三段均衡器** | LOW / MID / HIGH ±15dB，垂直滑块调节 |
| 📊 **压缩器** | 动态范围压缩，防止削波失真 |
| 🏛️ **混响** | 卷积混响，营造空间感 |
| ⏱️ **延迟** | 带反馈的延迟效果器 |
| ↔️ **声像调节** | PAN 左右声道平衡控制 |
| 🎚️ **淡入淡出** | 可调节时长，平滑过渡 |

### 编辑功能

| 功能 | 说明 |
|:----:|------|
| ✂️ **音频裁剪** | 波形拖拽选区，支持多段反复裁剪 |
| 🔄 **反向播放** | 一键反转音频方向 |
| ⏩ **倍速播放** | 0.25~5x 实时变速不变调 |
| 🔊 **音量归一化** | 自动最大化音量而不削波 |
| ⚡ **削波指示** | 实时削波检测与警告 |
| 📍 **标记点** | 双击添加、点击跳转、右键删除 |
| 🔁 **AB 循环** | 选定区域内循环播放 |
| 🔍 **波形缩放** | 1x~8x，滚轮缩放 + Shift 拖拽平移 |
| 📃 **播放列表** | 加载多个音频文件，列表切换播放，一键移除 |

### 录制与导出

| 功能 | 说明 |
|:----:|------|
| 🎤 **DJ 实时录制** | 播放时的调音一并录制，暂停可继续录制 |
| 💾 **多格式导出** | WAV / MP3（64~320kbps 可调）/ OGG / FLAC |
| 📋 **导出选择** | 导出原曲或录制版 |
| 🎵 **随机示例音乐** | 10 调式 × 40 和弦 × 25 鼓点 × 6 编曲风格 |

### 其他实用功能

- 📈 **实时频谱仪** — 48 频段对数频率映射
- 💾 **预设系统** — 保存和加载处理参数组合
- 🔄 **循环播放** — 单曲循环
- ⏹️ **加载取消** — 加载过程中可取消（防误触设计）
- 📋 **音频信息详情** — 峰值/RMS/直流偏移/动态范围等技术参数

---

## 🚀 快速开始

### 方式一：直接使用

下载 [最新 Release](https://github.com/114514gph/BIT-AUDIO-WORKSTATION/releases) 中的 `bit-audio-workstation.html`，双击用浏览器打开即可。

### 方式二：源码部署

```bash
# 克隆仓库
git clone https://github.com/114514gph/BIT-AUDIO-WORKSTATION.git
cd BIT-AUDIO-WORKSTATION

# 启动本地服务器（推荐，避免 CORS 问题）
python3 -m http.server 8080

# 浏览器访问
# http://localhost:8080
```

---

## 🛠️ 技术栈

```
┌──────────────────────────────────────────────────────┐
│  纯 HTML / CSS / JavaScript · 零框架依赖              │
├──────────────────────────────────────────────────────┤
│  Web Audio API + AudioWorklet 实时音频处理            │
│  lamejs (MP3编码) + libflacjs (FLAC编码) 内联         │
│  字体 base64 内嵌 (Press Start 2P / VT323 /           │
│  Cubic 11 像素中文字体)                               │
│  单文件自包含 · 也可拆分部署                          │
└──────────────────────────────────────────────────────┘
```

---

## 📁 项目结构

```
BIT-AUDIO-WORKSTATION/
├── index.html                    # 主页面（拆分版）
├── style.css                     # 样式（含内嵌字体）
├── script.js                     # 逻辑（含编码库）
├── bit-audio-workstation.html    # 单文件完整版（Release 用）
├── README.md
├── SECURITY.md
├── LICENSE                       # CC BY-NC-SA 4.0
├── .gitignore
└── archive/                      # 历史版本归档
```

---

## 🌐 浏览器兼容

| 浏览器 | 版本 | 支持 |
|:------:|:----:|:----:|
| Chrome / Edge | 90+ | ✅ 完整支持 |
| Firefox | 88+ | ✅ 完整支持 |
| Safari | 14+ | ✅ 完整支持 |
| 移动端 Chrome / Safari | - | ✅ 自适应布局 |

---

## 📌 版本号规则

| 类型 | 格式 | 说明 | 示例 |
|:----:|:----:|------|:----:|
| 正常功能更新 | `STABLE x.y` | 新增功能，小版本 y+1 | `1.5` → `1.6` |
| Bug 修复 | `STABLE x.y.nnn (Bugfix)` | 主要修 bug，nnn 从 1 递增 | `1.5` → `1.5.1` → `1.5.2` |
| 实验性功能 | `BETA x.yXn` | 未经验证的新功能，n 是测试次数 | `1.6` → `BETA 1.6X1` → `STABLE 1.6` |

- Bugfix 版本不增加 y，只增加 nnn
- 下一次正常功能更新时，从最新 Bugfix 版本继续 +0.1
- BETA 版标记为 Pre-release，测试通过后转为 STABLE

---

## 📜 版本历史

<details>
<summary><b>🟢 STABLE 1.7.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.7.1 (Bugfix)
- 修复播放列表删除当前播放项后界面不切换的 bug（索引早退问题）

### STABLE 1.7
- 新增播放列表功能：支持加载多个音频文件，列表切换播放，一键移除
- 加载文件/URL/示例时自动添加到播放列表
- 当前播放项高亮显示，显示时长信息

</details>

<details>
<summary><b>🔵 STABLE 1.6.x</b>（点击展开）</summary>

### STABLE 1.6.4 (Bugfix)
- 修复倍速播放暂停后再播放，进度条消失/位置错误的 bug

### STABLE 1.6.3 (Bugfix)
- 修复 mp3BrEl is not defined 致命错误
- 波形峰值缓存优化（2048 bars 预计算）

### STABLE 1.6.2 (Bugfix)
- ScriptProcessor 降级方案支持 Dither
- 大音频分块异步处理，避免 UI 卡死

### STABLE 1.6.1 (Bugfix)
- 修复 ditherToggleBtn 重复声明致命语法错误
- 修复 FLAC 编码采样值无 Math.round

### STABLE 1.6
- 新增音频信息详情面板（峰值/RMS/直流偏移/动态范围）

</details>

<details>
<summary><b>🔵 STABLE 1.5.x</b>（点击展开）</summary>

### STABLE 1.5.3 (Bugfix)
- 修复 createReverbIR 重复定义致命回归
- 修复导出效果与实时播放不一致

### STABLE 1.5.2
- 导出时完整应用所有实时效果

### STABLE 1.5.1 (Bugfix)
- 批量修复 19 个 bug

### STABLE 1.5
- 新增标记点（Marker）功能

</details>

<details>
<summary><b>⚪ STABLE 1.0 ~ 1.4</b>（点击展开）</summary>

### STABLE 1.4 — AB 循环、波形缩放
### STABLE 1.3 — Dither 抖动、MP3 比特率选择器
### STABLE 1.2 — 声像调节（PAN）、更名 BIT AUDIO WORKSTATION
### STABLE 1.1 — 循环播放
### STABLE 1.0 — 淡入淡出、归一化、预设、反向、混响/延迟/压缩器、频谱仪、编码库内置

</details>

---

## 🔒 安全

本项目为纯前端应用，所有音频处理均在本地完成，不上传服务器。

- [📖 安全策略](SECURITY.md)
- [🐛 报告安全漏洞](https://github.com/114514gph/BIT-AUDIO-WORKSTATION/security/advisories)（请通过 Security Advisories 私下报告）

---

## 📄 许可证

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](LICENSE)

本作品采用 [知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议](LICENSE) 进行许可。

**您可以自由地：**
- 📤 **共享** — 在任何媒介以任何形式复制、发行本作品
- 🔧 **改编** — 修改、转换或以本作品为基础进行创作

**惟须遵守下列条件：**
- 📝 **署名** — 必须给出适当的署名，提供指向本许可协议的链接
- ❌ **非商业性使用** — 不得将本作品用于商业目的
- 🔄 **相同方式共享** — 修改后须以相同协议分发

---

<div align="center">

**Made with 💚 by MengYou® Studio™**

*复古像素风 · 纯前端 · 无上传 · 隐私安全*

© 2023~2026 MengYou® Studio™ · 离线应用无需备案

</div>
