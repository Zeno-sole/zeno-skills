---
name: debian-pkg-query
description: Debian 软件包查询工具 - 查询 packages.debian.org 和 tracker.debian.org 的软件包信息、CVE、版本历史等
version: 1.0.0
license: MIT
author: zeno
homepage: https://github.com/openclaw/skills/debian-pkg-query
metadata:
  openclaw:
    emoji: "📦"
    requires:
      bins: [curl, python3]
    os: [linux, darwin]
---

# Debian Package Query Skill

查询 Debian 软件包信息，支持 packages.debian.org 和 tracker.debian.org。

## 功能

- 查询软件包基本信息（版本、描述、依赖等）
- 查询 CVE 安全漏洞
- 查询版本历史
- 生成软件包评估报告

## 使用方式

```python
# Python API
from debian_pkg_query import DebianPackageQuery

query = DebianPackageQuery()
info = query.get_package_info("bzip2")
cves = query.get_cve_list("bzip2")
versions = query.get_version_history("bzip2")
```

```bash
# CLI
python3 debian-pkg-query.py info bzip2
python3 debian-pkg-query.py cve bzip2
python3 debian-pkg-query.py versions bzip2
python3 debian-pkg-query.py report bzip2
```

## API 说明

| 方法 | 说明 |
|------|------|
| `get_package_info(pkg)` | 获取软件包基本信息 |
| `get_cve_list(pkg)` | 获取 CVE 列表 |
| `get_version_history(pkg)` | 获取版本历史 |
| `generate_report(pkg)` | 生成完整评估报告 |
