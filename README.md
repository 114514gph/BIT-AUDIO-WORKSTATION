# BIT AUDIO WORKSTATION

复古像素风音频处理工作站 · 纯前端 H5 应用

![Version](https://img.shields.io/badge/version-STABLE%201.5.3-green)
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
- **循环播放、AB 循环、标记点（Marker）**：单曲循环
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

## 版本号规则

| 类型 | 格式 | 说明 | 示例 |
|------|------|------|------|
| 正常功能更新 | `STABLE x.y` | 新增功能，小版本 y+1 | `1.5` → `1.6` |
| Bug 修复 | `STABLE x.y.nnn (Bugfix)` | 主要修 bug，不增加 y，nnn 从 1 递增 | `1.5` → `1.5.1 (Bugfix)` → `1.5.2 (Bugfix)` |
| 实验性功能 | `BETA x.yXn` | 未经验证的新功能，X 是分隔符，n 是测试次数 | `1.6` → `BETA 1.6X1` → 测试通过 → `STABLE 1.6` |

- Bugfix 版本不增加 y，只增加 nnn
- 下一次正常功能更新时，从最新 Bugfix 版本继续 +0.1
- BETA 版标记为 Pre-release，测试通过后转为 STABLE

## 版本历史


### STABLE 1.5.3 (Bugfix)
- 修复 createReverbIR 重复定义导致 ensureCtx() 崩溃的致命回归 Bug
- 修复导出时压缩器参数硬编码（改为从 compSlider 读取）
- 修复导出时延迟反馈量、混响/延迟干湿比与实时播放不一致
- 修复 bypass 时压缩器行为与实时播放不一致
- 修复 MP3 编码采样值无 Math.round、clamp 范围不对称
- 修复 URL 加载未应用协议白名单（禁止内网/本地）
- 修复 scheduleProcess pending 丢失更新（参数变化被遗忘）
- 修复 normalizeToggle/mp3BitrateBtns 依赖浏览器全局 id 映射
- 修复 mp3BitrateBtns HTML id 错误（id="$('mp3BitrateBtns')"）
- 删除 loadScript 死代码和 mp3Bitrate 无效引用

### STABLE 1.5.2
- 修复导出时实时效果未应用到离线渲染（压缩器/混响/延迟/淡入淡出/声像/播放速度）
- 修复 encodeOgg 异常路径未关闭 AudioContext 导致的资源泄漏
- 修复 localStorage 预设数据校验缺失（防止篡改导致 NaN 传播）
- 导出时使用完整 OfflineAudioContext 管线渲染所有效果

### STABLE 1.5.1 (Bugfix)
- 修复标记点缩放时 const 重新赋值导致崩溃
- 修复 AB 循环不工作（整首播完才跳转）
- 修复反向播放后裁剪 reversedBuffer 不同步
- 修复 AudioWorklet 超时 Blob URL 泄漏
- 修复 speedSlider=0 除零错误
- 修复波形只显示左声道（改为混合双声道）
- 修复 WAV 16位采样转换无取整、正负不对称
- 修复下载文件名未净化（路径遍历风险）
- 修复缩放拖拽与选区拖拽冲突
- 添加 URL 加载协议白名单（禁止内网/本地）
- 添加 .btn.on 激活态样式
- 页脚版本号修正

### STABLE 1.5
- 新增标记点（Marker）功能：双击添加、点击跳转、右键删除、缩放自适应
- 新增 AB 循环（1.4 引入，1.5 修复）
- 新增波形缩放（1.4 引入，1.5 修复）

### STABLE 1.4
- 新增 AB 循环：选定区域内循环播放
- 新增波形缩放：1x~8x，滚轮缩放 + Shift 拖拽平移

### STABLE 1.3
- 新增 Dither 抖动：TPDF 噪声，低比特量化时减少失真
- 移除快捷键系统（存在兼容性问题，后续考虑回归）
- MP3 比特率选择器改为自制按钮组
- UI 布局优化

### STABLE 1.2
- 新增声像调节（PAN）：左右声道平衡
- 更名为 BIT AUDIO WORKSTATION

### STABLE 1.1
- 新增循环播放
- 新增快捷键系统（1.3 已移除）

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
