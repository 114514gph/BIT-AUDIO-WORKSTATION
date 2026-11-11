<!-- 项目横幅 -->
<p align="center">
  <a href="https://github.com/114514gph/BIT-AUDIO-WORKSTATION">
    <img width="200" src="https://img.shields.io/badge/GITHUB-BIT%20AUDIO%20WORKSTATION-00ff88?style=for-the-badge&logo=github" alt="GITHUB BIT AUDIO WORKSTATION">
  </a>
</p>

<h1 align="center">BIT AUDIO WORKSTATION</h1>

<p align="center">
  复古像素风纯前端音频处理工作站 — 浏览器本地完成所有音频处理，无需上传
</p>

<!-- 徽章区域 -->
<p align="center">
  <a href="https://github.com/114514gph/BIT-AUDIO-WORKSTATION/releases"><img src="https://img.shields.io/github/v/release/114514gph/BIT-AUDIO-WORKSTATION?style=flat-square&logo=github" alt="Release"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-ff0066?style=flat-square" alt="License"></a>
  <a href="https://github.com/114514gph/BIT-AUDIO-WORKSTATION/pulls"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square" alt="PRs Welcome"></a>
  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API"><img src="https://img.shields.io/badge/Web%20Audio%20API-00aaff?style=flat-square&logo=webaudio" alt="Web Audio API"></a>
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
| 音频裁剪 | 波形拖拽选区，支持多段反复裁剪，选区也可直接另存为片段 |
| 反向播放 | 一键反转音频方向 |
| 倍速播放 | 0.25~5x 实时变速不变调 |
| 音量归一化 | 自动最大化音量而不削波 |
| 削波指示 | 实时削波检测与警告 LED |
| 标记点 | 双击添加、点击跳转、右键删除，播放头处也能一键打点 |
| 切段导出 | 按标记点把音频切成多段 WAV，一次打包成 ZIP 下载 |
| 插入静音 | 在播放头位置插入指定时长的静音段，可撤销 |
| 追加音频 | 把另一段音频接到末尾，自动对齐采样率与声道 |
| AB 循环 | 选定区域内循环播放 |
| 波形缩放 | 1x~8x，滚轮缩放 + Shift 拖拽平移 |
| 播放列表 | 多文件队列，上一曲/下一曲，自动连播 |

### 录制与导出

| 功能 | 说明 |
|:----:|------|
| DJ 实时录制 | 播放时的调音一并录制，暂停可继续录制 |
| 多格式导出 | WAV / MP3（64~320kbps 可调）/ OGG / FLAC |
| 导出选择 | 导出原曲或录制版；选区可单独导出为片段，不改动原音频 |
| 导出整理 | 可选自动去掉头尾静音，也可用标签里的艺术家与标题拼文件名 |
| 撤销与重做 | 裁剪、删除、去静音最多退三步，退多了还能 REDO 重做回来 |
| MP3 标签 | 导出时写入标题、艺术家、专辑、年份、流派（ID3v2.3），载入 MP3 时自动读取已有标签 |
| 随机示例音乐 | 10 调式 × 40 和弦 × 25 鼓点 × 6 编曲风格 |

### 其他功能

- 实时频谱仪 — 48 频段对数频率映射，柱状图/折线图/镜像三种样式
- 实时频谱图 — 时频热力图，绿色到红色映射，可随时关闭省出空间
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

<details open>
<summary><b>STABLE 1.43.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.43
- 新增插入静音：在播放头位置插入指定时长的静音段，时长 0.1~60 秒，可撤销重做
- 新增追加音频：把另一段音频文件接到当前音频末尾，适合拼接录音、串接片段
- 追加时自动对齐采样率（线性插值重采样）和声道（单声道复制、双声道缩混），采样率或声道不一致也能接上
- 插入与追加都计入撤销栈，波形、峰值、标记点随编辑一起刷新

</details>

<details>
<summary><b>STABLE 1.42.x</b></summary>

### STABLE 1.42
- 新增按标记切段导出：以标记点为切点把音频分成多段，每段一个 WAV，一次性打包成 ZIP，不用再一段段导出
- 切段导出走纯存储打包，不压缩也不重新编码，音质和单独导出 WAV 完全一致
- 短于 0.1 秒的碎片会自动并入相邻段，避免切出一堆听起来没内容的碎文件
- 超过 30 分钟的音频会提示先裁剪，防止切段时把内存吃满
- 标记菜单新增「在播放头打标记」，播放到想标记的位置马上打点，不用再双击估位置
- 标记菜单新增跳到上一标记 / 下一标记，走到头会自动环绕
- 标记点数量、导出 CSV、导入 CSV 等原有行为保持不变

</details>

<details>
<summary><b>STABLE 1.41.x</b></summary>

### STABLE 1.41
- UNDO 从只能退一步升级成撤销栈，连续裁剪、去静音最多能退三步
- 新增 REDO，撤销撤多了可以重做回去，来回对比也不用重新载入文件
- 两个按钮都会按可撤销/可重做的剩余步数自动置灰，不会出现点了没反应的情况
- 栈内的快照有总量预算，短音频留三步，长音频自动压到一两步，避免同时留多份缓冲
- 一旦做了新的编辑，重做栈立刻清空，不会出现和当前音频对不上的旧状态
- 窄屏下传送栏改为自动换行，按钮多了也不挤在一起

</details>

<details>
<summary><b>STABLE 1.40.x</b></summary>

### STABLE 1.40
- 传送栏 REV 旁边多了一个 UNDO，用来撤销上一步会改动音频本身的操作
- 覆盖裁剪保留、裁剪删除、去除静音三种情况，这些操作以前点错只能重新载入文件
- 撤销之后波形、峰值、标记点一起回到上一步，接着就能重新调整
- 只保留最近一步，没有可撤销内容时按钮置灰，点了会提示没有可撤销的编辑
- 超过约 5 分钟的长音频暂不记录撤销，避免同时留两份缓冲占内存
- 换文件、切播放列表、处理声道时会自动清空记录，不会把上一首的状态带过来

</details>

<details>
<summary><b>STABLE 1.39.x</b></summary>

### STABLE 1.39
- 导出面板新增「出口整理」两个开关，专门处理导出前后最琐碎的两件事
- 去首尾静音：录音开头结尾那段空场会自动裁掉，阈值和最短静音时长沿用 SILENCE 面板的设置
- 整首静音的音频不会被裁成空文件，仍然完整导出
- 去静音发生在编码之前，所以任何格式、任何采样率都生效，选区导出同样适用
- 用标签命名：勾选后文件名自动变成 `艺术家 - 标题`，标签来自 MP3 标签栏或载入时读到的标签
- 标题为空时自动回退到自定义文件名或原文件名，不会出现无名文件
- 两个开关都会记住状态，下次打开还是上次的选择

</details>

<details>
<summary><b>STABLE 1.38.x</b></summary>

### STABLE 1.38
- 波形上拖出一段后，可以直接把这一段导出成文件，原曲保持不动
- 新按钮放在选区工具栏里，KEEP / DELETE 之外多一个 PART
- 片段走完整的导出链路，格式、采样率、比特率、标签都跟着当前设置走
- 文件名自动加 `_part` 后缀，和整曲导出不会互相覆盖
- 归一化按片段本身计算，短片段也不会因为整曲的峰值而偏小

</details>

<details>
<summary><b>STABLE 1.37.x</b></summary>

### STABLE 1.37
- 载入 MP3 时自动读取文件自带的 ID3v2 标签，标题、艺术家、专辑、年份、流派直接回填到导出面板
- 支持 ID3v2.2 / v2.3 / v2.4 三代标签，UTF-16、UTF-8、ISO-8859-1 三种文本编码都能解
- 读取后无需重新输入，改完音频直接导出即可保留原有信息
- 文件本身没有标签时不做任何改动，不会清空已经填好的内容

</details>

<details>
<summary><b>STABLE 1.36.x</b></summary>

### STABLE 1.36
- MP3 导出支持 ID3v2.3 标签，可填写标题、艺术家、专辑、年份、流派
- 标签内容会记住，下次导出不用重新输入；标题留空时自动用文件名
- 中文标签按 UTF-16 写入，播放器和系统文件管理器都能正常显示
- 频谱图新增开关，不需要时可以关掉，给波形腾出空间
- 非 MP3 格式时标签输入区自动置灰，避免误以为其他格式也带标签

</details>

<details>
<summary><b>STABLE 1.35.x</b></summary>

### STABLE 1.35
- 新增实时频谱图（Spectrogram）功能
- 在频谱仪下方添加时频分析视图
- 实时显示音频频率随时间变化的热力图
- 颜色从绿色（低能量）到红色（高能量）映射

</details>

<details>
<summary><b>STABLE 1.34.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.34
- 新增自动保存工作状态功能
- 开启 AUTO-SAVE 后，所有效果器参数自动保存到本地
- 下次打开页面时自动恢复上次的参数设置
- 无需手动保存，关闭页面后重新打开即可继续上次工作

</details>

<details>
<summary><b>STABLE 1.33.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.33
- 新增节拍器功能
- 双击 METRO 按钮开始/停止节拍器
- 支持 40-240 BPM 调节，拍号可选 2/4、3/4、4/4、6/8
- 重拍与弱拍音色不同，录音练习时提供节奏参考

</details>

<details>
<summary><b>STABLE 1.32.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.32
- 新增预设导出/导入功能
- 可将所有本地预设导出为 JSON 文件备份或分享
- 支持从 JSON 文件批量导入预设，合并到现有预设列表
- 方便在不同设备间迁移预设配置

</details>

<details>
<summary><b>STABLE 1.31.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.31
- 新增导出文件名自定义功能
- 在导出选项面板新增文件名输入框，可自定义导出文件名
- 留空则自动使用原文件名，方便批量导出和文件管理

</details>

<details>
<summary><b>STABLE 1.30.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.30
- 新增音频信息面板（INFO）
- 显示当前加载音频的详细信息：文件名、时长、采样率、声道数、文件大小、峰值电平
- 在 demo-bar 新增 INFO 按钮，点击展开信息面板
- 专业音频工具标配功能，快速查看音频参数

</details>

<details>
<summary><b>STABLE 1.29.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.29
- 新增人声消除（Vocal Remove）功能
- 基于 Mid-Side 矩阵去除居中声道，保留两侧乐器
- 在 CHANNEL 控制面板新增 VOCAL RM 按钮
- 适用于 KTV 伴奏制作：消除居中人声，保留鼓点和和声
- 实时处理无延迟，导出时同步应用

</details>

<details>
<summary><b>STABLE 1.28.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.28
- 新增实时峰值电平表（Peak Meter）
- 在 CLIP 指示灯旁显示输出电平，范围 -60dB 到 0dB
- 绿色为正常电平，黄色接近削波，红色超过 -1dB
- 白色竖线为峰值保持标记，缓慢衰减
- 与削波指示灯联动，实时监控输出电平

</details>

<details>
<summary><b>STABLE 1.27.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.27
- 新增声道交换（Swap L/R）按钮：一键交换左右声道
- 新增左声道反相（Invert L）按钮：将左声道波形取反
- 新增右声道反相（Invert R）按钮：将右声道波形取反
- 录音时左右声道接反可一键修复
- 反相功能可用于相位校正或特殊效果制作
- 实时处理无延迟，导出时同步应用

</details>

<details>
<summary><b>STABLE 1.26.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.26
- 新增立体声宽度调节（Stereo Width）
- 0% = 单声道（Mono），100% = 原始立体声，200% = 超宽立体声
- 基于 Mid-Side 矩阵处理，实时调节无延迟
- 导出时同步应用宽度设置
- 位于 PAN 声像滑块旁，与声像调节配合使用

</details>

<details>
<summary><b>STABLE 1.25.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.25
- 新增效果器预设系统（FX Presets）
- 压缩器预设：VOCAL / DRUM / MASTER / OFF
- 混响预设：ROOM / HALL / PLATE / OFF
- 延迟预设：SLAP / PING / TAPE / OFF（含延迟时间自动匹配）
- 手动调节滑块时自动清除预设高亮
- 与 EQ 预设风格统一，紧凑排列不占额外空间

</details>

<details>
<summary><b>STABLE 1.24.1 (Bugfix)</b> — 最新版本（点击展开）</summary>

### STABLE 1.24.1 (Bugfix)
- 修复 VT323 字体损坏导致的加载失败（OTS parsing error）
- 移除重复的 Cubic11 字体定义
- 修复工作区按钮拥挤问题（demo-bar 添加 flex-wrap 自动换行）
- 缩小按钮间距（gap 12px → 8px），窄屏幕自动换行不挤

</details>

<details>
<summary><b>STABLE 1.24.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.24
- 新增直流偏移校正功能（DC Offset Correction）
- 支持检测音频中的直流偏移量（以 dB 显示）
- 一键校正直流偏移，自动减去平均值
- 分块计算支持大音频文件
- 校正后自动更新波形显示和峰值缓存

</details>

<details>
<summary><b>STABLE 1.23.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.23
- 新增频谱导出为图片功能（Spectrum Export）
- 支持将当前频谱实时快照导出为 1920x400 高清 PNG 图片
- 导出图片包含频率标签、频谱样式、峰值保持状态
- 图片包含文件名和频谱样式信息
- 与波形导出图片功能形成配套

</details>

<details>
<summary><b>STABLE 1.22.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.22
- 新增标记点导出/导入功能（Marker Import/Export）
- 支持将标记点导出为 CSV 文件（时间、名称）
- 支持从 CSV 文件导入标记点
- 一键清除全部标记点
- 显示当前标记点数量
- 双击波形添加标记，右键删除，点击跳转

</details>

<details>
<summary><b>STABLE 1.21.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.21
- 新增波形导出为图片功能（Waveform Export）
- 支持将当前波形导出为 1920x400 高清 PNG 图片
- 导出图片包含静音区域标记、节拍标记、标记点
- 图片包含文件名、音频参数、BPM 等信息
- 一键导出，自动下载

</details>

<details>
<summary><b>STABLE 1.20.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.20.1 (Bugfix)
- 修复节拍标记在音频内容改变后未重置的问题（文件上传、URL加载、示例音乐、噪声生成器、播放列表切换、去除静音、声道处理、裁剪等10处）
- 清理 detectBeats() 中未使用的变量

### STABLE 1.20
- 新增音频节拍检测功能（Beat Detection）
- 自动检测 BPM（每分钟节拍数）
- 波形上用品红色垂直线标记节拍位置
- 显示检测到的 BPM 和节拍数量
- 可清除节拍标记

</details>

<details>
<summary><b>STABLE 1.19.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.19.1 (Bugfix)
- 修复 NOISE/SILENCE/CHANNEL 按钮在主屏幕错误显示的问题
- 修复下拉菜单重叠问题（点击一个按钮时自动关闭其他菜单）
- 修复噪声生成器使用未初始化 audioCtx 导致崩溃的问题

### STABLE 1.19
- 新增音频声道处理功能（Channel Processing）
- 支持左右声道交换（L/R Swap）
- 支持合并为单声道（Mono Mix）
- 支持仅左声道/仅右声道输出
- 支持相位反转（Phase Invert）
- 可一键恢复原始声道

</details>

<details>
<summary><b>STABLE 1.18.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.18
- 新增静音检测与去除功能（Silence Detection & Removal）
- 自动检测音频中的静音片段，阈值可调（-60dB ~ -20dB）
- 最小时长可调（100ms ~ 2000ms），避免误判短暂停顿
- 波形上用橙色半透明区域标记静音位置
- 一键去除静音，自动拼接非静音片段
- 显示静音统计：数量、总时长、占比

</details>

<details>
<summary><b>STABLE 1.17.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.17
- 新增输入增益调节功能（Gain/Trim）
- 支持 -12dB ~ +12dB 范围调节，步长 0.5dB
- 实时播放和离线导出均应用增益
- 位于 OPTIONS 面板，紧凑布局不占额外空间

</details>

<details>
<summary><b>STABLE 1.16.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.16.1 (Bugfix)
- 修复淡入淡出曲线选择功能中淡出曲线公式错误的问题
- exp/log 淡出曲线方向反转（原公式从 0→1，修正为 1→0）
- S 曲线淡出终点值错误（原 t=1 时为 0.5，修正为 0）

### STABLE 1.16
- 新增淡入淡出曲线选择功能
- 支持 4 种曲线：线性(LIN)、指数(EXP)、对数(LOG)、S曲线(S)
- 淡入和淡出可分别选择不同曲线
- 实时播放和导出均应用所选曲线

</details>

<details>
<summary><b>STABLE 1.15.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.16
- 新增淡入淡出曲线选择功能
- 支持 4 种曲线：线性(LIN)、指数(EXP)、对数(LOG)、S曲线(S)
- 淡入和淡出可分别选择不同曲线
- 实时播放和导出均应用所选曲线

</details>

<details>
<summary><b>STABLE 1.15.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.15
- 新增均衡器预设功能（EQ Presets）
- 7 种预设：平坦、流行、摇滚、古典、人声、低音、高音
- 一键应用预设，自动调整三段 EQ
- 手动调节时自动清除预设高亮

</details>

<details>
<summary><b>STABLE 1.14.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.14
- 新增频谱峰值保持功能（Peak Hold）
- 品红色峰值线显示各频段最大电平
- 峰值缓慢衰减，便于观察音频动态范围
- 可一键开关，自动保存设置

</details>

<details>
<summary><b>STABLE 1.13.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.13
- 新增播放列表随机播放模式
- 新增重复模式：列表循环 / 单曲循环 / 不循环
- 随机播放和重复模式自动保存
- 播放结束自动切换下一曲（支持随机和循环逻辑）

</details>

<details>
<summary><b>STABLE 1.12.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.12
- 新增噪声生成器：白噪声 / 粉噪声 / 棕色噪声
- 支持 10s / 30s / 60s 多种时长
- 生成后自动加载到工作区，可继续处理和导出
- Paul Kellet 粉噪声算法，棕色噪声积分算法

</details>

<details>
<summary><b>STABLE 1.11.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.11
- 新增主题切换功能：5 种配色方案（经典绿 / 品红粉 / 电蓝 / 琥珀橙 / 紫电）
- 主题选择自动保存，下次打开恢复
- 全局 CSS 变量驱动，所有界面元素同步变色

</details>

<details>
<summary><b>STABLE 1.10.x</b> — 最新版本（点击展开）</summary>

### STABLE 1.10
- 新增导出采样率选择：8000 / 16000 / 22050 / 32000 / 44100 / 48000 Hz
- 采样率选择自动保存，下次打开恢复
- OfflineAudioContext 重采样，导出音质与实时播放一致

</details>

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
