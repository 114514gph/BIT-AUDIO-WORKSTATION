# BIT AUDIO WORKSTATION

复古像素风音频处理工作站 · 纯前端 H5 应用

![Version](https://img.shields.io/badge/version-STABLE%201.3-green)
![License](https://img.shields.io/badge/license-AGPL--3.0-orange)
![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Mobile-blue)

## 简介

BIT AUDIO WORKSTATION 是一个功能完整的纯前端音频处理工作站，无需上传服务器，所有处理均在浏览器本地完成。复古像素风 UI，支持电脑端和手机端自适应。

## 功能特性

### 音质处理
- **8-bit 降采样**：1~8 bit 量化 + 1~64x 降采样
- **Dither 抖动**：低比特量化时添加 TPDF 噪声，减少量化失真
- **降噪**：自适应噪声门 + 高频嘶声压制
- **三段均衡器**：LOW / MID / HIGH ±15dB，垂直滑块
- **压缩器**：动态范围压缩
- **混响**：卷积混响
- **延迟**：带反馈的延迟效果
- **声像调节**：PAN 左右声道平衡
- **淡入淡出**：可调节时长

### 编辑功能
- **音频裁剪**：波形拖拽选区，支持多段反复裁剪
- **反向播放**：一键反转音频
- **倍速播放**：0~5x 实时变速
- **音量归一化**：自动最大化音量
- **削波指示**：实时削波检测

### 录制与导出
- **DJ 实时录制**：播放时的调音一并录制，暂停可继续
- **多格式导出**：WAV / MP3（64~320kbps 可调）/ OGG / FLAC
- **导出选择**：原曲或录制版

### 其他
- **随机示例音乐**：10 调式 × 40 和弦进行 × 25 鼓点 × 6 编曲风格
- **实时频谱仪**：48 频段对数频率映射
- **预设系统**：保存和加载处理参数
- **循环播放**：单曲循环
- **加载取消**：加载过程中可取消（防误触）

## 技术栈

- 纯 HTML / CSS / JavaScript，无框架依赖
- Web Audio API + AudioWorklet 实时处理
- lamejs（MP3 编码）+ libflacjs（FLAC 编码）内联
- 字体 base64 内嵌（Press Start 2P / VT323 / Cubic 11）
- 单文件自包含，也可拆分部署

## 项目结构

```
├── index.html          # 主页面（拆分版）
├── style.css           # 样式（含内嵌字体）
├── script.js           # 逻辑（含编码库）
├── bit-audio-workstation.html  # 单文件完整版（用于 Release）
└── README.md
```

## 使用方法

### 直接使用
下载 Release 中的 `bit-audio-workstation.html`，用浏览器打开即可。

### 源码部署
```bash
# 克隆仓库
git clone https://github.com/114514gph/BIT-AUDIO-WORKSTATION.git
cd BIT-AUDIO-WORKSTATION

# 启动本地服务器（推荐，避免 CORS 问题）
python3 -m http.server 8080

# 浏览器访问
open http://localhost:8080
```

## 浏览器兼容

- Chrome / Edge 90+
- Firefox 88+
- Safari 14+
- 移动端浏览器（Chrome / Safari）

## 版本历史

### STABLE 1.3
- 新增 Dither 抖动功能
- 移除快捷键系统
- MP3 比特率选择器改为自制按钮组
- UI 布局优化（按钮文字换行显示）
- 滑块点击即可跳转，移除长按检测

### STABLE 1.2
- 新增声像调节（PAN）
- 更名为 BIT AUDIO WORKSTATION

### STABLE 1.1
- 新增循环播放
- 新增快捷键系统（1.3 已移除）
- 新增快捷键帮助面板

### STABLE 1.0
- 淡入淡出
- 音量归一化
- 削波指示
- 预设系统
- 反向播放
- 混响 / 延迟 / 压缩器
- 实时频谱仪
- MP3 / FLAC 编码库内置

## 作者

MengYou® Studio™

## 版权

© 2023~2026 MengYou® Studio™ 保留所有权利

离线应用无需备案
