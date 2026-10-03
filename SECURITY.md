# Security Policy

## Supported Versions

目前以下版本持续接收安全更新：

| Version | Supported          |
| ------- | ------------------ |
| STABLE 1.3.x | :white_check_mark: |
| STABLE 1.2.x | :white_check_mark: |
| STABLE 1.1.x | :x: |
| STABLE 1.0.x | :x: |
| BETA 版本 | :warning: 测试版，仅接收关键安全修复 |

> 注：建议始终使用最新 STABLE 版本以获得完整的安全更新和功能修复。

## Reporting a Vulnerability

如果你发现了安全漏洞，请**不要**公开创建 Issue，而是通过以下方式私下报告：

### 报告方式

1. **GitHub Security Advisories**（推荐）：
   - 前往 [Security → Advisories](https://github.com/114514gph/BIT-AUDIO-WORKSTATION/security/advisories)
   - 点击 "New draft security advisory" 提交漏洞详情

2. **邮件联系**：
   - 发送邮件至项目维护者（请在 GitHub 个人主页查看联系方式）

### 报告内容请包含

- 漏洞描述和影响范围
- 复现步骤（如适用）
- 受影响的版本
- 可能的修复建议（如有）
- 是否为公开已知漏洞（CVE 编号等）

### 响应时间

- **初步确认**：收到报告后 72 小时内回复
- **评估进度**：每周更新一次处理状态
- **修复发布**：根据漏洞严重程度，关键漏洞将在 7 天内发布修复版本

### 处理流程

1. 收到报告后，我们会在 72 小时内确认并开始评估
2. 评估漏洞严重程度（Critical / High / Medium / Low）
3. 如确认有效，将在私有分支中开发修复
4. 修复完成后发布安全更新版本，并在 Release Notes 中说明
5. 漏洞公开披露前会提前通知报告者

### 安全范围

本项目为纯前端 H5 应用，主要关注以下安全领域：

- **XSS / 注入漏洞**：用户输入处理、URL 加载、文件解析
- **第三方库安全**：lamejs、libflacjs 等内联编码库的已知漏洞
- **内存安全**：AudioWorklet、WebAssembly 相关的内存问题
- **数据隐私**：所有音频处理均在本地完成，不上传服务器

### 不在安全范围内

- 浏览器本身的安全漏洞
- 用户自行修改代码导致的问题
- 预期内的功能行为（如音频处理导致的性能问题）

---

感谢你帮助保护 BIT AUDIO WORKSTATION 的安全。负责任的漏洞披露对开源社区至关重要。
