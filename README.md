# Zeno Skills 集合

本仓库收集整理了 OpenClaw/Claude Code 使用的所有 Agent Skills，包含实际的 Skill 文件和文档。

## 📊 Skills 统计

| 来源 | 数量 | 路径 | 说明 |
|------|------|------|------|
| 全局 npm 安装 | 52 | `skills/npm/` | OpenClaw 官方 Skills |
| 本地 Workspace | 16 | `skills/local/` | 自定义/第三方 Skills |
| 用户本地 | 3 | `skills/user/` | 用户本地 Skills |
| **总计** | **71** | - | - |

---

## 📂 仓库结构

```
zeno-skills/
├── README.md                 # 本文件
├── INDEX.md                  # 完整索引（按字母排序）
├── GUIDE.md                  # 使用指南
├── .gitignore               # Git 忽略规则
├── npm-skills/              # npm Skills 文档
├── local-skills/            # 本地 Skills 文档
├── skills-docs/             # 额外 Skill 文档
└── skills/                  # ⭐ 实际的 Skill 文件
    ├── npm/                 # 52 个 npm 安装的 skills
    ├── local/               # 16 个本地 workspace skills
    └── user/                # 3 个用户本地 skills
```

---

## 🚀 快速使用

### 安装 Skill

将本仓库的 skill 复制到你的 OpenClaw skills 目录：

```bash
# 克隆仓库
git clone https://github.com/Zeno-sole/zeno-skills.git

# 复制特定 skill
cp -r zeno-skills/skills/npm/weather ~/.openclaw/skills/
cp -r zeno-skills/skills/local/jenkins-crp-to-xlsx ~/.openclaw/skills/

# 或者复制所有 user skills
cp -r zeno-skills/skills/user/* ~/.openclaw/skills/
```

### 通过 ClawHub 安装

```bash
# 搜索 Skills
npx skills find jenkins

# 安装 Skill
npx skills add owner/skill@variant
```

---

## 📂 Skills 目录详解

### `skills/npm/` - 全局 npm Skills (52个)

通过 npm 全局安装的 OpenClaw 官方 Skills。

**安装路径**: `~/.npm-global/lib/node_modules/openclaw/skills/`

**主要分类**:
- 📱 苹果生态: apple-notes, apple-reminders, bear-notes, imsg, things-mac
- 💬 通讯协作: discord, slack, bluebubbles, wacli, voice-call
- 🎵 媒体娱乐: spotify-player, sonoscli, songsee, gifgrep, video-frames
- 🤖 AI/ML: gemini, openai-image-gen, openai-whisper, sag, summarize
- 🛠️ 开发工具: github, gh-issues, coding-agent, skill-creator, mcporter
- ☁️ 云与笔记: notion, obsidian, oracle, himalaya, trello
- 🏠 智能家居: openhue, blucli, camsnap, peekaboo, eightctl
- 🔒 安全: 1password, healthcheck
- 🌐 其他: weather, xurl, goplaces, blogwatcher

### `skills/local/` - 本地 Workspace Skills (16个)

自定义开发和第三方 Skills。

**安装路径**: `~/clawd/skills/`

**主要 Skills**:
- 📄 文档处理: docx, excel-xlsx, office
- 🔍 搜索: multi-search-engine, baidu-search
- 🛡️ 安全审计: agent-bom, cve-patching, cve-scan, deepin-cve-fixer, dependency-auditor
- 🐧 Deepin 专用: deepin-os-version-update, debian-pkg-query
- 🤖 智能代理: proactive-agent, agent-team-kit
- 🆕 自定义: jenkins-crp-to-xlsx

### `skills/user/` - 用户本地 Skills (3个)

用户个人安装的 Skills。

**安装路径**: `~/.openclaw/skills/`

| Skill | 说明 |
|-------|------|
| find-skills | Skill 发现与安装 |
| jenkins-crp-to-xlsx | Jenkins CRP 转 Excel |
| self-improving-agent | 自我改进代理 |

---

## 📋 分类速查

### 文档处理
```bash
claude -s docx "创建 Word 文档"
claude -s excel-xlsx "创建 Excel 表格"
claude -s office "Office 综合操作"
```

### 搜索
```bash
claude -s multi-search-engine "搜索关键词"
claude -s baidu-search "百度搜索"
```

### 安全审计
```bash
claude -s agent-bom "生成 SBOM"
claude -s cve-scan "扫描 CVE"
claude -s dependency-auditor "审计依赖"
```

### Jenkins 操作
```bash
python3 ~/.openclaw/skills/jenkins-crp-to-xlsx/jenkins_crp_to_xlsx.py \
  v25-repo-iso-work/v25-crp_info_collect 173
```

### GitHub
```bash
claude -s github "查看 PR"
claude -s gh-issues "修复 Issue"
```

### 天气
```bash
claude -s weather "北京今天天气"
```

---

## 🛠️ 创建新 Skill

参考 [skill-creator](./skills/npm/skill-creator/) 创建自己的 Skill：

```bash
python3 skills/npm/skill-creator/scripts/init_skill.py my-skill --path ./skills/user
```

---

## 📝 文档索引

| 文档 | 说明 |
|------|------|
| [INDEX.md](./INDEX.md) | 按字母排序的完整 Skills 索引 |
| [GUIDE.md](./GUIDE.md) | Skills 使用指南和故障排除 |
| [npm-skills/README.md](./npm-skills/README.md) | npm Skills 详解 |
| [local-skills/README.md](./local-skills/README.md) | 本地 Skills 详解 |

---

## 📄 许可证

各 Skill 遵循其原始许可证。详见各 Skill 目录中的 LICENSE 文件。

---

## 🤝 贡献

欢迎贡献新的 Skills 或改进文档！

1. Fork 本仓库
2. 添加你的 Skill 到 `skills/user/`
3. 更新相关文档
4. 提交 PR

---

*最后更新: 2026-03-08*
