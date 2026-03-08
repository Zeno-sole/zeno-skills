# Zeno Skills 集合

本仓库收集整理了 OpenClaw/Claude Code 使用的所有 Agent Skills，按功能分类管理。

## 📊 Skills 统计

| 来源 | 数量 | 说明 |
|------|------|------|
| 全局 npm 安装 | 51 | OpenClaw 官方提供的 Skills |
| 本地 Workspace | 22 | 自定义/第三方 Skills |
| ~/.openclaw/skills | 3 | 用户本地 Skills |
| **总计** | **76** | - |

---

## 📂 分类目录

### 1. 📱 苹果生态 (Apple Ecosystem)

| Skill | 说明 | 来源 |
|-------|------|------|
| [apple-notes](./apple-notes) | Apple Notes 笔记操作 | npm |
| [apple-reminders](./apple-reminders) | Apple 提醒事项管理 | npm |
| [bear-notes](./bear-notes) | Bear 笔记应用 | npm |
| [imsg](./imsg) | iMessage 消息发送 | npm |
| [things-mac](./things-mac) | Things 任务管理 | npm |

---

### 2. 💬 通讯协作 (Communication)

| Skill | 说明 | 来源 |
|-------|------|------|
| [discord](./discord) | Discord 机器人操作 | npm |
| [slack](./slack) | Slack 集成 | npm |
| [bluebubbles](./bluebubbles) | BlueBubbles 消息 | npm |
| [wacli](./wacli) | WhatsApp CLI | npm |
| [voice-call](./voice-call) | 语音通话 | npm |

---

### 3. 🎵 媒体娱乐 (Media & Entertainment)

| Skill | 说明 | 来源 |
|-------|------|------|
| [spotify-player](./spotify-player) | Spotify 播放器控制 | npm |
| [sonoscli](./sonoscli) | Sonos 音响控制 | npm |
| [songsee](./songsee) | 音乐相关操作 | npm |
| [gifgrep](./gifgrep) | GIF 搜索 | npm |
| [video-frames](./video-frames) | 视频帧提取 | npm |

---

### 4. 🤖 AI/ML 与语音 (AI & Voice)

| Skill | 说明 | 来源 |
|-------|------|------|
| [gemini](./gemini) | Google Gemini AI 集成 | npm |
| [openai-image-gen](./openai-image-gen) | OpenAI 图像生成 | npm |
| [openai-whisper](./openai-whisper) | 本地 Whisper 语音识别 | npm |
| [openai-whisper-api](./openai-whisper-api) | Whisper API | npm |
| [sherpa-onnx-tts](./sherpa-onnx-tts) | TTS 语音合成 | npm |
| [sag](./sag) | ElevenLabs TTS 语音讲述 | npm |
| [summarize](./summarize) | 文本摘要 | npm |

---

### 5. ☁️ 云与笔记 (Cloud & Notes)

| Skill | 说明 | 来源 |
|-------|------|------|
| [notion](./notion) | Notion 文档操作 | npm |
| [obsidian](./obsidian) | Obsidian 笔记管理 | npm |
| [oracle](./oracle) | Oracle 数据库 | npm |
| [himalaya](./himalaya) | Himalaya CLI 邮件 | npm |
| [trello](./trello) | Trello 看板 | npm |

---

### 6. 🏠 智能家居 (Smart Home)

| Skill | 说明 | 来源 |
|-------|------|------|
| [openhue](./openhue) | Philips Hue 灯光控制 | npm |
| [blucli](./blucli) | 蓝牙控制 | npm |
| [camsnap](./camsnap) | 相机快照 | npm |
| [peekaboo](./peekaboo) | 设备预览 | npm |
| [eightctl](./eightctl) | 设备控制 | npm |

---

### 7. 🛠️ 开发工具 (Development Tools)

#### 7.1 代码协作
| Skill | 说明 | 来源 |
|-------|------|------|
| [github](./github) | GitHub 操作 (gh CLI) | npm |
| [gh-issues](./gh-issues) | GitHub Issue 自动修复 | npm |
| [coding-agent](./coding-agent) | 编码代理 | npm |

#### 7.2 开发辅助
| Skill | 说明 | 来源 |
|-------|------|------|
| [clawhub](./clawhub) | ClawHub 技能商店 | npm |
| [skill-creator](./skill-creator) | Skill 创建工具 | npm |
| [mcporter](./mcporter) | MCP 服务器管理 | npm |
| [tmux](./tmux) | tmux 会话远程控制 | npm |
| [canvas](./canvas) | Canvas 操作 | npm |

---

### 8. 🔒 安全工具 (Security)

| Skill | 说明 | 来源 |
|-------|------|------|
| [1password](./1password) | 1Password 密码管理 | npm |
| [healthcheck](./healthcheck) | 主机安全加固检查 | npm |

---

### 9. 🐧 Deepin/Linux 专用

| Skill | 说明 | 来源 |
|-------|------|------|
| [deepin-os-version-update](./deepin-os-version-update) | Deepin OS 版本更新 | local |
| [debian-pkg-query](./debian-pkg-query) | Debian 包查询 | local |
| [cve-patching](./cve-patching) | CVE 漏洞修补工作流 | local |
| [cve-scan](./cve-scan) | CVE 扫描 | local |
| [deepin-cve-fixer](./deepin-cve-fixer) | Deepin CVE 修复 | local |

---

### 10. 🛡️ 安全审计 (Security Audit)

| Skill | 说明 | 来源 |
|-------|------|------|
| [agent-bom](./agent-bom) | AI 供应链安全扫描 | local |
| [dependency-auditor](./dependency-auditor) | 依赖审计 | local |

---

### 11. 📄 文档处理 (Document Processing)

| Skill | 说明 | 来源 |
|-------|------|------|
| [docx](./docx) | Word 文档操作 | local |
| [excel-xlsx](./excel-xlsx) | Excel 文件处理 | local |
| [office](./office) | Office 套件集成 | local |

---

### 12. 🔍 搜索 (Search)

| Skill | 说明 | 来源 |
|-------|------|------|
| [multi-search-engine](./multi-search-engine) | 多引擎搜索 | local |
| [baidu-search](./baidu-search) | 百度搜索 | local |

---

### 13. 🤖 智能代理 (AI Agents)

| Skill | 说明 | 来源 |
|-------|------|------|
| [proactive-agent](./proactive-agent) | 主动型代理框架 | local |
| [agent-team-kit](./agent-team-kit) | 代理团队协作 | local |
| [self-improving-agent](./self-improving-agent) | 自我改进代理 | local |

---

### 14. 🌐 其他工具 (Others)

| Skill | 说明 | 来源 |
|-------|------|------|
| [weather](./weather) | 天气查询 | npm |
| [xurl](./xurl) | URL 工具 | npm |
| [goplaces](./goplaces) | 位置管理 | npm |
| [blogwatcher](./blogwatcher) | 博客监控 | npm |
| [gog](./gog) | GOG 游戏平台 | npm |
| [ordercli](./ordercli) | 订单管理 CLI | npm |
| [nano-pdf](./nano-pdf) | PDF 处理 | npm |
| [nano-banana-pro](./nano-banana-pro) | Banana Pro | npm |
| [model-usage](./model-usage) | 模型使用统计 | npm |
| [session-logs](./session-logs) | 会话日志 | npm |
| [find-skills](./find-skills) | Skill 发现与安装 | local |
| [jenkins-crp-to-xlsx](./jenkins-crp-to-xlsx) | Jenkins CRP 转 Excel | local |

---

## 🚀 快速开始

### 安装 Skill

```bash
# 通过 npx 安装
npx skills add <skill-name>

# 通过 ClawHub 搜索
npx skills find <keyword>
```

### 本地 Skill 路径

| 路径 | 说明 |
|------|------|
| `~/.npm-global/lib/node_modules/openclaw/skills/` | 全局 npm Skills |
| `~/clawd/skills/` | Workspace Skills |
| `~/.openclaw/skills/` | 用户本地 Skills |

---

## 📝 使用示例

### 文档生成
```bash
# Word 文档
claude -s docx "创建一份报告"

# Excel 表格
claude -s excel-xlsx "生成数据表"
```

### Jenkins 操作
```bash
# CRP 信息转 Excel
python3 ~/.openclaw/skills/jenkins-crp-to-xlsx/jenkins_crp_to_xlsx.py \
  v25-repo-iso-work/v25-crp_info_collect 173
```

### 安全扫描
```bash
# CVE 扫描
claude -s cve-scan "扫描仓库 CVE"

# 依赖审计
claude -s dependency-auditor "检查依赖"
```

---

## 📄 许可证

各 Skill 遵循其原始许可证。详见各 Skill 目录中的 LICENSE 文件。

---

## 🤝 贡献

欢迎贡献新的 Skills！参考 [skill-creator](./skill-creator) 了解如何创建 Skill。

---

*最后更新: 2026-03-08*
