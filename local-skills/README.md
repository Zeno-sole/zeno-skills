# 本地 Workspace Skills 详解

本目录包含 `~/clawd/skills/` 下的自定义和第三方 Skills。

## 📄 文档处理

### docx
- **路径**: `~/clawd/skills/docx/`
- **作用**: Word 文档 (.docx) 创建和编辑
- **功能**:
  - 创建格式化的 Word 文档
  - 支持表格、页眉页脚、目录
  - 插入图片
- **使用示例**:
  ```bash
  claude -s docx "创建一份项目报告"
  ```

### excel-xlsx
- **路径**: `~/clawd/skills/excel-xlsx/`
- **作用**: Excel 文件 (.xlsx) 处理
- **功能**:
  - 创建 Excel 表格
  - 支持公式、图表、格式化
- **使用示例**:
  ```bash
  claude -s excel-xlsx "生成销售数据表"
  ```

### office
- **路径**: `~/clawd/skills/office/`
- **作用**: Office 套件集成 (Excel/Word/PPT)
- **功能**:
  - 统一的 Office 文档操作
  - 跨平台兼容

---

## 🔍 搜索

### multi-search-engine
- **路径**: `~/clawd/skills/multi-search-engine/`
- **作用**: 17 个搜索引擎集成 (8 CN + 9 Global)
- **功能**:
  - 百度搜索、Google、Bing 等
  - 支持高级搜索语法
  - 隐私搜索引擎支持
- **使用示例**:
  ```bash
  claude -s multi-search-engine "搜索 OpenAI 最新新闻"
  ```

### baidu-search
- **路径**: `~/clawd/skills/baidu-search/`
- **作用**: 百度搜索专用
- **功能**: 百度网页、图片、新闻搜索

---

## 🛡️ 安全审计

### agent-bom
- **路径**: `~/clawd/skills/agent-bom/`
- **作用**: AI 供应链安全扫描
- **功能**:
  - 检查包 CVE
  - MCP 服务器威胁注册表查询
  - SBOM 生成
  - 合规性检查 (OWASP, MITRE ATLAS, EU AI Act)
- **使用场景**: 依赖安全、漏洞扫描

### cve-patching
- **路径**: `~/clawd/skills/cve-patching/`
- **作用**: Debian CVE 漏洞修补工作流
- **功能**:
  - CVE 补丁下载
  - 补丁验证
  - 自动构建测试

### cve-scan
- **路径**: `~/clawd/skills/cve-scan/`
- **作用**: CVE 扫描工具
- **功能**: 扫描项目 CVE 漏洞

### deepin-cve-fixer
- **路径**: `~/clawd/skills/deepin-cve-fixer/`
- **作用**: Deepin CVE 漏洞自动修复
- **功能**:
  - 搜索 CVE 数据库
  - 生成补丁
  - Quilt 验证
  - Gerrit/GitHub 提交

### dependency-auditor
- **路径**: `~/clawd/skills/dependency-auditor/`
- **作用**: 依赖审计
- **功能**: 检查项目依赖安全性

---

## 🐧 Deepin/Linux 专用

### deepin-os-version-update
- **路径**: `~/clawd/skills/deepin-os-version-update/`
- **作用**: Deepin OS 版本更新
- **功能**:
  - 更新版本号
  - 支持多架构 (amd/arm/loong/riscv)
  - 自动创建 PR

### debian-pkg-query
- **路径**: `~/clawd/skills/debian-pkg-query/`
- **作用**: Debian 包查询
- **功能**: 查询 Debian 软件包信息

---

## 🤖 智能代理

### proactive-agent
- **路径**: `~/clawd/skills/proactive-agent/`
- **作用**: 主动型代理框架
- **功能**:
  - WAL Protocol
  - Working Buffer
  - Autonomous Crons
  - 主动任务调度

### agent-team-kit
- **路径**: `~/clawd/skills/agent-team-kit/`
- **作用**: 代理团队协作工具包
- **功能**: 多代理协作、任务分配

### self-improving-agent
- **路径**: `~/.openclaw/skills/self-improving-agent/`
- **作用**: 自我改进代理
- **功能**: 捕获学习经验、持续改进

---

## 🆕 自定义 Skills

### jenkins-crp-to-xlsx ⭐
- **路径**: `~/.openclaw/skills/jenkins-crp-to-xlsx/`
- **作用**: Jenkins CRP 信息转 Excel
- **功能**:
  - 自动获取 Jenkins 构建日志
  - 解析 CRP 主题信息
  - 生成格式化的 Excel 文件
- **使用方式**:
  ```bash
  python3 ~/.openclaw/skills/jenkins-crp-to-xlsx/jenkins_crp_to_xlsx.py \
    v25-repo-iso-work/v25-crp_info_collect 173
  ```
- **输出字段**:
  - 主题名称
  - 主题地址
  - 仓库
  - 源码名及版本
  - 责任人

### find-skills
- **路径**: `~/.openclaw/skills/find-skills/`
- **作用**: Skill 发现与安装
- **功能**:
  - 搜索 Skills
  - 安装 Skills
  - 检查更新
- **使用方式**:
  ```bash
  npx skills find jenkins
  npx skills add owner/skill@variant
  ```

---

## 🛠️ 开发工具

### github
- **路径**: `~/clawd/skills/github/`
- **作用**: GitHub CLI 操作 (本地版本)
- **功能**: Issue、PR、CI 管理

---

## 📍 路径说明

| 类型 | 路径 |
|------|------|
| Workspace Skills | `~/clawd/skills/` |
| 用户本地 Skills | `~/.openclaw/skills/` |

---

## ➕ 添加新 Skill

1. 创建 Skill 目录
2. 编写 `SKILL.md`
3. 可选：添加 `scripts/`, `references/`, `assets/`
4. 参考 [skill-creator](https://github.com/openclaw/skill-creator) 规范
