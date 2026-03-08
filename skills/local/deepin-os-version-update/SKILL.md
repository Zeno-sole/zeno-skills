---
name: deepin-os-version-update
description: Update Deepin OS version files and create PR for deepin-desktop-base repository. Updates version numbers across all architectures (amd/arm/loong/riscv), updates debian/changelog, and creates a pull request. Use when user asks to update os-version for Deepin desktop base.
---

# Deepin OS Version Update

## Quick Start

To update the OS version to a new version (e.g., 25.0.13):

1. Clone the repository to a temporary location
2. Update version numbers in all architecture files
3. Update debian/changelog with new package version
4. Commit and push to a new branch
5. Create a PR

## Default Maintainer

- Name: `lichenggang`
- Email: `lichenggang@deepin.org`

## Architecture Files

These files need to be updated with the new version:
- `files/os-version-amd` - AMD64 architecture
- `files/os-version-arm` - ARM architecture
- `files/os-version-loong` - LoongArch architecture
- `files/os-version-riscv` - RISC-V architecture

Each file has:
- `MinorVersion=25.0.X` - Update the version number
- `OsBuild=XXXXX.YYY.ZZZ` - Update build number (different per architecture)

## Version File Formats

### AMD64 (os-version-amd)
```
MinorVersion=25.0.X
OsBuild=21138.YYY.ZZZ
```

### ARM (os-version-arm)
```
MinorVersion=25.0.X
OsBuild=21134.YYY.ZZZ
```

### LoongArch (os-version-loong)
```
MinorVersion=25.0.X
OsBuild=21133.YYY.ZZZ
```

### RISC-V (os-version-riscv)
```
MinorVersion=25.0.X
OsBuild=21135.YYY.ZZZ
```

## Debian Changelog Format

```markdown
deepin-desktop-base (YYYY.MM.DD) unstable; urgency=medium

  * update 25.0.X.

 -- lichenggang <lichenggang@deepin.org>  Day, DD Mon YYYY HH:MM:SS +0800
```

- Package version: Increment the package version (e.g., 2026.01.26 -> 2026.01.27)
- Date format: Use `LC_ALL=C date +"%a, %d %b %Y %H:%M:%S %z"`

## Workflow

```bash
# Clone or update the repo
gh repo clone linuxdeepin/deepin-desktop-base /tmp/deepin-desktop-base || \
  (cd /tmp/deepin-desktop-base && git fetch origin && git pull origin beige-25)

# Switch to the correct branch
cd /tmp/deepin-desktop-base
git checkout beige-25
git pull origin beige-25

# Create a new feature branch
git checkout -b feat/os-version-25.0.X

# Update version files (replace X with the new version)
sed -i 's/MinorVersion=25.0.[0-9]*/MinorVersion=25.0.X/' files/os-version-*
# Update OsBuild (provide correct values for each architecture)
sed -i 's/OsBuild=21138\...\.100/OsBuild=21138.YYY.ZZZ/' files/os-version-amd
sed -i 's/OsBuild=21134\...\.100/OsBuild=21134.YYY.ZZZ/' files/os-version-arm
sed -i 's/OsBuild=21133\...\.100/OsBuild=21133.YYY.ZZZ/' files/os-version-loong
sed -i 's/OsBuild=21135\...\.100/OsBuild=21135.YYY.ZZZ/' files/os-version-riscv

# Update debian/changelog
VERSION_DATE=$(LC_ALL=C date +"%a, %d %b %Y %H:%M:%S %z")
PACKAGE_VERSION=$(head -1 debian/changelog | grep -oP '(\d+\.\d+\.\d+)' | awk -F. '{printf "%d.%02d.%d", $1, $2+1, $3}')
cat > debian/changelog.new << EOF
deepin-desktop-base ($PACKAGE_VERSION) unstable; urgency=medium

  * update 25.0.X.

 -- lichenggang <lichenggang@deepin.org>  $VERSION_DATE

EOF
cat debian/changelog >> debian/changelog.new
mv debian/changelog.new debian/changelog

# Commit and push
git add -A
git commit -m "feat: update os-version 25.0.X"
git push -u origin feat/os-version-25.0.X

# Create PR
gh pr create --base beige-25 --title "feat: update os-version 25.0.X" \
  --body "Bump the recorded OS version to 25.0.X across Debian packaging metadata and per-architecture version files."
```

## Branch Selection

- Default base branch: `beige-25`
- Feature branch naming: `feat/os-version-25.0.X`

## Example Update

To update from 25.0.12 to 25.0.13 with OsBuild `.108.100`:

```
os-version-amd:  OsBuild=21138.108.100
os-version-arm:  OsBuild=21134.108.100
os-version-loong: OsBuild=21133.108.100
os-version-riscv: OsBuild=21135.108.100
```

## Fixing Mistakes

If a mistake is made in a commit (wrong version number, wrong maintainer):

```bash
git amend commit
git push -f origin feat/os-version-25.0.X
```

This will force-push the corrected commit to the existing PR.
