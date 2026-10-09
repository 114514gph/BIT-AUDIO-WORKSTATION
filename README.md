<!-- 项目横幅 -->
<p align="center">
  <a href="https://github.com/114514gph/BIT-AUDIO-WORKSTATION">
    <img width="200" src="https://img.shields.io/badge/BIT-AUDIO%20WORKSTATION-00ff88?style=for-the-badge&logo=github" alt="BIT AUDIO WORKSTATION">
  </a>
</p>

<h1 align="center">BIT AUDIO WORKSTATION</h1>

<p align="center">
  复古像素风纯前端音频处理工作站 — 浏览器本地完成所有音频处理，无需上传
</p>

<!-- 徽章区域 -->
<p align="center">
  <img src="https://img.shields.io/github/v/release/114514gph/BIT-AUDIO-WORKSTATION?style=flat-square&logo=github" alt="Release">
  <img src="https://img.shields.io/github/license/114514gph/BIT-AUDIO-WORKSTATION?style=flat-square" alt="License">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/Web%20Audio%20API-00aaff?style=flat-square&logo=webaudio" alt="Web Audio API">
  <img src="https://img.shields.io/badge/Platform-Web%20%7C%20Mobile-ffaa00?style=flat-square&logo=googlechrome" alt="Platform">
  <img src="https://img.shields.io/badge/Privacy-Local%20Only-ff0066?style=flat-square" alt="Privacy">
</p>

---

## 特性

- **纯前端处理** — 所有音频运算在浏览器本地完成，文件不上传服务器，隐私安全
- **复古像素风** — CRT 扫描线效果 + 霓虹配色 + 像素字体，沉浸式复古体验
- **实时音频链** — AudioWorklet 驱动，所有参数拖动即时生效，零延迟
- **完整效果链** — bitcrush / noise gate / EQ / compressor / reverb / delay / pan / dither
- **多格式导出** — WAV / MP3（可调比特率）/ OGG / FLAC，编码库内置
- **响应式布局** — 电脑端多栏布局，移动端自动适配，手机也能流畅使用

---

## 快速开始

### 环境要求

现代浏览器（Chrome 90+ / Firefox 88+ / Safari 14+），无需安装任何依赖。

### 直接使用

下载 [最新 Release](https://github.com/114514gph/BIT-AUDIO-WORKSTATION/releases) 中的 `bit-audio-workstation.html` 文件，双击用浏览器打开即可使用。

### 源码部署

```bash
# 克隆仓库
git clone https://github.com/114514gph/BIT-AUDIO-WORKSTATION.git
cd BIT-AUDIO-WORKSTATION

# 启动本地服务器（推荐，避免 CORS 问题）
python3 -m http.server 8080

# 浏览器访问
# http://localhost:8080
```

### 基本使用

1. 拖拽音频文件到页面，或点击上传区域选择文件
2. 调整 bit depth / downsample / EQ / 效果器参数
3. 点击 PLAY 实时试听效果
4. 满意后点击 EXPORT 选择格式导出

---

## 功能列表

### 音质处理

| 功能 | 说明 |
|:----:|------|
| 8-bit 降采样 | 1~8 bit 量化 + 1~64x 降采样，复古芯片音质 |
| Dither 抖动 | TPDF 噪声，低比特量化时减少量化失真 |
| 降噪 | 自适应噪声门 + 高频嘶声压制 |
| 三段均衡器 | LOW / MID / HIGH ±15dB，垂直滑块调节 |
| 压缩器 | 动态范围压缩，防止削波失真 |
| 混响 | 卷积混响，营造空间感 |
| 延迟 | 带反馈的延迟效果器 |
| 声像调节 | PAN 左右声道平衡控制 |
| 淡入淡出 | 可调节时长，平滑过渡 |

### 编辑功能

| 功能 | 说明 |
|:----:|------|
| 音频裁剪 | 波形拖拽选区，支持多段反复裁剪 |
| 反向播放 | 一键反转音频方向 |
| 倍速播放 | 0.25~5x 实时变速不变调 |
| 音量归一化 | 自动最大化音量而不削波 |
| 削波指示 | 实时削波检测与警告 LED |
| 标记点 | 双击添加、点击跳转、右键删除 |
| AB 循环 | 选定区域内循环播放 |
| 波形缩放 | 1x~8x，滚轮缩放 + Shift 拖拽平移 |
| 播放列表 | 多文件队列，上一曲/下一曲，自动连播 |

### 录制与导出

| 功能 | 说明 |
|:----:|------|
| DJ 实时录制 | 播放时的调音一并录制，暂停可继续录制 |
| 多格式导出 | WAV / MP3（64~320kbps 可调）/ OGG / FLAC |
| 导出选择 | 导出原曲或录制版 |
| 随机示例音乐 | 10 调式 × 40 和弦 × 25 鼓点 × 6 编曲风格 |

### 其他功能

- 实时频谱仪 — 48 频段对数频率映射，柱状图/折线图/镜像三种样式
- 预设系统 — 保存和加载处理参数组合
- 循环播放 — 单曲循环
- 加载取消 — 加载过程中可取消（防误触设计）
- 音频信息详情 — 峰值/RMS/直流偏移/动态范围等技术参数

---

## 文档

| 章节 | 说明 |
|------|------|
| [安全策略](SECURITY.md) | 漏洞报告流程与支持版本 |
| [许可证](LICENSE) | CC BY-NC-SA 4.0 完整文本 |
| [版本历史](#版本历史) | 所有版本更新记录 |

---

## 开发指南

### 本地开发

```bash
# 克隆仓库
git clone https://github.com/114514gph/BIT-AUDIO-WORKSTATION.git
cd BIT-AUDIO-WORKSTATION

# 启动开发服务器
python3 -m http.server 8080

# 浏览器访问 http://localhost:8080
```

### 项目结构

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

### 技术栈

- 纯 HTML / CSS / JavaScript，零框架依赖
- Web Audio API + AudioWorklet 实时音频处理
- lamejs（MP3 编码）+ libflacjs（FLAC 编码）内联
- 字体 base64 内嵌（Press Start 2P / VT323 / Cubic 11 像素中文字体）
- 单文件自包含，也可拆分部署

---

## 浏览器兼容

| 浏览器 | 版本 | 支持 |
|:------:|:----:|:----:|
| Chrome / Edge | 90+ | 完整支持 |
| Firefox | 88+ | 完整支持 |
| Safari | 14+ | 完整支持 |
| 移动端 Chrome / Safari | - | 自适应布局 |

---

## 版本号规则

| 类型 | 格式 | 说明 | 示例 |
|:----:|:----:|------|:----:|
| 正常功能更新 | `STABLE x.y` | 新增功能，小版本 y+1 | `1.5` → `1.6` |
| Bug 修复 | `STABLE x.y.nnn (Bugfix)` | 主要修 bug，nnn 从 1 递增 | `1.5` → `1.5.1` → `1.5.2` |
| 实验性功能 | `BETA x.yXn` | 未经验证的新功能，n 是测试次数 | `1.6` → `BETA 1.6X1` → `STABLE 1.6` |

---

## 版本历史

<details>
<summary><b>STABLE 1.9.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.9
- 新增播放列表上一曲/下一曲快捷按钮（PREV / NEXT）
- 播放结束自动播放下一曲（播放列表模式）
- 上一曲/下一曲支持循环切换（首尾相连）

</details>

<details>
<summary><b>STABLE 1.8.x</b>（点击展开）</summary>

### STABLE 1.8
- 新增频谱样式切换：柱状图 / 折线图 / 镜像柱状图三种显示模式
- 样式选择自动保存，下次打开恢复
- 频谱绘制性能优化：预计算 bin 范围

</details>

<details>
<summary><b>STABLE 1.7.x</b>（点击展开）</summary>

### STABLE 1.7.2 (Bugfix)
- computeAudioStats 改为分块异步处理，大音频不再卡顿
- isSafeUrl 新增 IPv6 本地/内网地址拦截
- normalizeToggle 缓存 DOM 引用
- 播放列表添加上限保护（最多 20 项）

### STABLE 1.7.1 (Bugfix)
- 修复播放列表删除当前播放项后界面不切换的 bug

### STABLE 1.7
- 新增播放列表功能：多文件队列，列表切换播放
- 当前播放项高亮显示，显示时长信息

</details>

<details>
<summary><b>STABLE 1.6.x</b>（点击展开）</summary>

### STABLE 1.6.4 (Bugfix)
- 修复倍速播放暂停后再播放，进度条消失的 bug

### STABLE 1.6.3 (Bugfix)
- 修复 mp3BrEl is not defined 致命错误
- 波形峰值缓存优化

### STABLE 1.6.2 (Bugfix)
- ScriptProcessor 降级方案支持 Dither
- 大音频分块异步处理

### STABLE 1.6.1 (Bugfix)
- 修复 ditherToggleBtn 重复声明致命语法错误
- 修复 FLAC 编码采样值无 Math.round

### STABLE 1.6
- 新增音频信息详情面板

</details>

<details>
<summary><b>STABLE 1.5.x</b>（点击展开）</summary>

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
<summary><b>STABLE 1.0 ~ 1.4</b>（点击展开）</summary>

### STABLE 1.4 — AB 循环、波形缩放
### STABLE 1.3 — Dither 抖动、MP3 比特率选择器
### STABLE 1.2 — 声像调节（PAN）、更名 BIT AUDIO WORKSTATION
### STABLE 1.1 — 循环播放
### STABLE 1.0 — 淡入淡出、归一化、预设、反向、混响/延迟/压缩器、频谱仪、编码库内置

</details>

---

## 贡献

我们欢迎所有形式的贡献！

- 提交 Bug — 通过 Issue 报告
- 提出建议 — 讨论新功能与改进方向
- 改进文档 — 修正拼写、补充示例
- 提交代码 — Fork 仓库后提交 PR

---

## 许可证

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](LICENSE)

本作品采用 [知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议](LICENSE) 进行许可。

**您可以自由地：**
- **共享** — 在任何媒介以任何形式复制、发行本作品
- **改编** — 修改、转换或以本作品为基础进行创作

**惟须遵守下列条件：**
- **署名** — 必须给出适当的署名，提供指向本许可协议的链接
- **非商业性使用** — 不得将本作品用于商业目的
- **相同方式共享** — 修改后须以相同协议分发

---

<div align="center">

**Made with by MengYou Studio**

*复古像素风 · 纯前端 · 无上传 · 隐私安全*

© 2023~2026 MengYou Studio · 离线应用无需备案

</div>
