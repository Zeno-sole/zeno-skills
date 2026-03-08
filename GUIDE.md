# Skills 使用指南

快速参考：如何使用各种 Skills。

## 🚀 常用 Skills 速查

### 文档处理
```bash
# Word 文档
claude -s docx "创建一份项目报告，包含标题和表格"

# Excel 表格
claude -s excel-xlsx "生成销售数据表，包含公式计算"

# Office 综合
claude -s office "将这份数据转换成 PPT"
```

### 搜索
```bash
# 多引擎搜索
claude -s multi-search-engine "搜索 Linux 6.13 新特性"

# 百度搜索
claude -s baidu-search "搜索 Rust 教程"
```

### Jenkins 操作
```bash
# CRP 信息转 Excel
python3 ~/.openclaw/skills/jenkins-crp-to-xlsx/jenkins_crp_to_xlsx.py \
  v25-repo-iso-work/v25-crp_info_collect 173
```

### GitHub
```bash
# 查看 PR
claude -s github "查看 PR #123"

# 检查 CI 状态
claude -s github "检查最近的 CI 运行"

# 创建 Issue
claude -s github "创建 Issue：发现 Bug"
```

### 安全扫描
```bash
# CVE 扫描
claude -s cve-scan "扫描当前目录的 CVE"

# 依赖审计
claude -s dependency-auditor "检查 package.json 依赖"

# Agent BOM
claude -s agent-bom "生成 SBOM"
```

### 天气查询
```bash
claude -s weather "北京今天天气如何？"
claude -s weather "上海明天会下雨吗？"
```

---

## 📦 安装新 Skills

### 方法 1: 通过 ClawHub
```bash
# 搜索 Skills
npx skills find jenkins

# 安装 Skill
npx skills add owner/skill@variant

# 检查更新
npx skills check

# 更新所有
npx skills update
```

### 方法 2: 手动安装
```bash
# 下载 skill 压缩包
unzip skill-name.zip -d ~/.openclaw/skills/skill-name

# 确保包含 SKILL.md
ls ~/.openclaw/skills/skill-name/SKILL.md
```

---

## 🛠️ 创建自定义 Skill

### 快速开始
```bash
# 使用 skill-creator
python3 ~/.npm-global/lib/node_modules/openclaw/skills/skill-creator/scripts/init_skill.py \
  my-skill --path ~/.openclaw/skills
```

### Skill 结构
```
my-skill/
├── SKILL.md          # 必需：Skill 说明
├── scripts/          # 可选：脚本文件
├── references/       # 可选：参考文档
└── assets/           # 可选：资源文件
```

### SKILL.md 模板
```markdown
---
name: my-skill
description: 简要描述 Skill 的作用和使用场景
---

# My Skill

## 使用方式

### 命令 1
说明...

### 命令 2
说明...

## 示例

```bash
claude -s my-skill "执行操作"
```
```

---

## 🔧 故障排除

### Skill 无法识别
```bash
# 检查 Skill 路径
echo $OPENCLAW_SKILLS_PATH

# 检查 SKILL.md 是否存在
ls ~/.openclaw/skills/my-skill/SKILL.md
```

### 权限问题
```bash
# 修复权限
chmod +x ~/.openclaw/skills/my-skill/scripts/*.py
```

### 依赖缺失
```bash
# Python 依赖
pip3 install -r ~/.openclaw/skills/my-skill/requirements.txt

# Node 依赖
cd ~/.openclaw/skills/my-skill && npm install
```

---

## 📍 Skills 路径

| 类型 | 路径 |
|------|------|
| 全局 npm | `~/.npm-global/lib/node_modules/openclaw/skills/` |
| Workspace | `~/clawd/skills/` |
| 用户本地 | `~/.openclaw/skills/` |

---

## 📝 最佳实践

1. **命名规范**: 使用小写字母和连字符，如 `my-skill`
2. **描述清晰**: SKILL.md 的描述要准确反映 Skill 的作用
3. **示例丰富**: 提供多个使用示例
4. **错误处理**: 脚本要有完善的错误提示
5. **版本控制**: 使用 Git 管理 Skill 代码

---

## 🔗 相关资源

- [OpenClaw 文档](https://docs.openclaw.ai)
- [ClawHub](https://clawhub.com)
- [Skill Creator 指南](./npm-skills/README.md#skill-creator)

---

*最后更新: 2026-03-08*
