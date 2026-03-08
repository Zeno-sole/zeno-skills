# npm 全局 Skills 详解

本目录包含通过 npm 全局安装的 OpenClaw 官方 Skills。

## 📱 苹果生态

### apple-notes
- **作用**: 操作 Apple Notes 笔记应用
- **使用场景**: 创建、读取、搜索 Mac/iOS 备忘录
- **命令示例**:
  ```bash
  claude -s apple-notes "列出所有笔记"
  claude -s apple-notes "创建新笔记：会议纪要"
  ```

### apple-reminders
- **作用**: Apple 提醒事项管理
- **使用场景**: 创建待办事项、设置提醒
- **命令示例**:
  ```bash
  claude -s apple-reminders "今天有什么待办？"
  claude -s apple-reminders "添加提醒：下午3点开会"
  ```

### bear-notes
- **作用**: Bear 笔记应用操作
- **使用场景**: Markdown 笔记管理
- **官网**: https://bear.app

### imsg
- **作用**: iMessage 消息发送
- **使用场景**: 通过 iMessage 发送消息
- **注意**: 需要 macOS 系统

### things-mac
- **作用**: Things 任务管理
- **使用场景**: GTD 任务管理
- **官网**: https://culturedcode.com/things/

---

## 💬 通讯协作

### discord
- **作用**: Discord 机器人操作
- **使用场景**: 发送消息、管理频道
- **命令示例**:
  ```bash
  claude -s discord "发送消息到 #general"
  ```

### slack
- **作用**: Slack 集成
- **使用场景**: 发送 Slack 消息、查询频道
- **命令示例**:
  ```bash
  claude -s slack "发送消息到 #dev-channel"
  ```

### wacli
- **作用**: WhatsApp CLI 工具
- **使用场景**: WhatsApp 消息操作

---

## 🎵 媒体娱乐

### spotify-player
- **作用**: Spotify 播放器控制
- **使用场景**: 播放、暂停、搜索音乐
- **命令示例**:
  ```bash
  claude -s spotify-player "播放周杰伦的歌"
  ```

### video-frames
- **作用**: 视频帧提取
- **使用场景**: 从视频提取图片帧
- **命令示例**:
  ```bash
  claude -s video-frames "提取视频前10秒帧"
  ```

---

## 🤖 AI/ML

### gemini
- **作用**: Google Gemini AI 集成
- **使用场景**: 调用 Gemini API

### openai-image-gen
- **作用**: OpenAI DALL-E 图像生成
- **使用场景**: 根据描述生成图片
- **命令示例**:
  ```bash
  claude -s openai-image-gen "生成一只猫的图片"
  ```

### openai-whisper
- **作用**: 本地 Whisper 语音识别
- **使用场景**: 本地语音转文字

### summarize
- **作用**: 文本摘要
- **使用场景**: 长文本摘要
- **命令示例**:
  ```bash
  claude -s summarize "总结这篇文章"
  ```

---

## 🛠️ 开发工具

### github
- **作用**: GitHub CLI 操作
- **使用场景**: PR、Issue、CI 管理
- **命令示例**:
  ```bash
  claude -s github "查看 PR #123"
  claude -s github "列出最近的 CI 运行"
  ```

### gh-issues
- **作用**: GitHub Issue 自动修复
- **使用场景**: 自动分析并修复 GitHub Issue

### coding-agent
- **作用**: 编码代理
- **使用场景**: 代码审查、代码生成

### clawhub
- **作用**: ClawHub 技能商店
- **使用场景**: 搜索、安装、更新 Skills
- **命令示例**:
  ```bash
  npx skills find jenkins
  npx skills add owner/skill@variant
  ```

### skill-creator
- **作用**: Skill 创建工具
- **使用场景**: 创建自定义 Skills
- **命令示例**:
  ```bash
  python3 ~/.npm-global/lib/node_modules/openclaw/skills/skill-creator/scripts/init_skill.py my-skill --path ./skills
  ```

### mcporter
- **作用**: MCP 服务器管理
- **使用场景**: 管理 Model Context Protocol 服务器

### tmux
- **作用**: tmux 会话远程控制
- **使用场景**: 远程管理 tmux 会话

---

## 🔒 安全

### 1password
- **作用**: 1Password 密码管理
- **使用场景**: 安全地获取密码

### healthcheck
- **作用**: 主机安全加固检查
- **使用场景**: 系统安全审计

---

## 🌐 其他

### weather
- **作用**: 天气查询
- **使用场景**: 获取当前天气和预报
- **命令示例**:
  ```bash
  claude -s weather "北京今天天气如何？"
  ```

### goplaces
- **作用**: 位置管理
- **使用场景**: 管理常用地点

### blogwatcher
- **作用**: 博客监控
- **使用场景**: 监控博客更新

---

## 📍 安装路径

```
~/.npm-global/lib/node_modules/openclaw/skills/
```

查看所有 npm skills:
```bash
ls ~/.npm-global/lib/node_modules/openclaw/skills/
```
