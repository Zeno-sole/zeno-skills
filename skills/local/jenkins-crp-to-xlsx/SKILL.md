---
name: jenkins-crp-to-xlsx
description: Convert Jenkins v25-crp_info_collect job output to Excel (.xlsx) format. Use when the user needs to extract theme information from Jenkins CRP (Code Review Platform) info collection jobs and convert it to a structured Excel file with columns for 主题名称, 主题地址, 仓库, 源码名及版本, 责任人. Works with job URLs like https://jenkinswh.uniontech.com/view/ISO-Builder/job/v25-repo-iso-work/view/repo/job/v25-crp_info_collect/
---

# Jenkins CRP to Excel Converter

This skill converts Jenkins v25-crp_info_collect job output into a structured Excel file containing CRP (Code Review Platform) theme information.

## Output Format

The generated Excel file contains the following columns:

| Column | Description |
|--------|-------------|
| **主题名称** | Theme name/title from CRP |
| **主题地址** | CRP detail and workflow URLs |
| **仓库** | Aptly repository addresses (main/commercial) |
| **源码名及版本** | Source package names and versions |
| **责任人** | Theme owners/responsible persons |

## Usage

### Using the Script

Run the conversion script with a Jenkins job path:

```bash
python3 scripts/jenkins_crp_to_xlsx.py <job-path> [build-number] [output-path]
```

**Parameters:**
- `job-path`: Jenkins job path (e.g., `v25-repo-iso-work/v25-crp_info_collect`)
- `build-number`: Build number (optional, defaults to latest)
- `output-path`: Output Excel file path (optional, auto-generated)

**Examples:**

```bash
# Convert latest build
python3 scripts/jenkins_crp_to_xlsx.py v25-repo-iso-work/v25-crp_info_collect

# Convert specific build
python3 scripts/jenkins_crp_to_xlsx.py v25-repo-iso-work/v25-crp_info_collect 173

# Specify output path
python3 scripts/jenkins_crp_to_xlsx.py v25-repo-iso-work/v25-crp_info_collect 173 /path/to/output.xlsx
```

### Manual Mode (with raw text)

If you have the Jenkins log output as text, you can parse it manually:

```python
from scripts.jenkins_crp_to_xlsx import parse_jenkins_output, create_excel

# Parse the Jenkins output text
themes = parse_jenkins_output(jenkins_log_text)

# Create Excel file
create_excel(themes, "output.xlsx")
```

## Prerequisites

1. **Jenkins CLI (jk)**: Must be installed and authenticated
   - Binary location: `/tmp/jk` (configurable)
   - Must have valid credentials for `https://jenkinswh.uniontech.com`

2. **Python Dependencies**:
   ```bash
   pip3 install openpyxl
   ```

## Theme Information Extracted

For each theme in the Jenkins output, the following information is extracted:

- **主题ID**: Theme ID from CRP
- **主题名称**: Theme name/title
- **主题地址**: CRP detail and workflow URLs
- **仓库地址**: One or more aptly repository URLs
- **仓库源码**: Source package names and versions (multiple packages supported)
- **责任人**: Comma-separated list of responsible persons
- **构建状态**: Build status (not included in Excel)
- **分支**: Branch name (not included in Excel)
- **状态**: Theme status (not included in Excel)

## Excel Formatting

The output Excel file includes:
- **Header row**: Blue background with white bold text
- **Auto-wrap**: All cells have text wrapping enabled
- **Column widths**: Optimized for readability
  - 主题名称: 50 characters
  - 主题地址: 60 characters
  - 仓库: 80 characters
  - 源码名及版本: 60 characters
  - 责任人: 40 characters
- **Row heights**: 120 points for multi-line content

## Error Handling

Common issues and solutions:

| Issue | Solution |
|-------|----------|
| "jk command not found" | Ensure `/tmp/jk` exists or specify alternative path |
| "Failed to fetch Jenkins log" | Check Jenkins authentication and network connectivity |
| "No themes found" | Verify the Jenkins output contains valid theme information |
| Import errors | Install required Python packages: `pip3 install openpyxl` |

## Example Output

For a Jenkins job with 10 themes, the Excel file will contain:
- 1 header row
- 10 data rows
- Each row represents one CRP theme with all relevant information

Example theme summary:
```json
{
  "total_themes": 10,
  "output_file": "/path/to/v25-crp_info_collect-173.xlsx",
  "themes": [
    {
      "name": "【UOS V25】玲珑1.11.3提测",
      "owner": "dengbo",
      "source_count": 1
    },
    {
      "name": "DDE-V25-20260227",
      "owner": "lvpeilong,zhangkun2,...",
      "source_count": 28
    }
  ]
}
```
