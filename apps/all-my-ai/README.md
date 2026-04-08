# All My AI - 展示页维护

## 目录结构

```
apps/all-my-ai/
├── index.{lang}.md     # 多语言介绍页 (zh-Hans, zh-Hant, en, ja, es)
├── privacy.{lang}.md   # 隐私政策 (MAS 审核需要)
├── eula.{lang}.md      # 用户协议 (链接到 Apple EULA)
├── assets/icon.png     # App 图标
└── README.md           # 本文件
```

## Updater 文件

`latest.json` 位于根目录 `all-my-ai/latest.json`，不在本目录。

```
alansuhe.github.io/
├── apps/all-my-ai/     # 展示页（本目录）
└── all-my-ai/          # updater 文件目录
    └── latest.json     # updater 元数据
```

## Release 规范

### Tag 命名
```
all-my-ai-v{version}
例: all-my-ai-v1.0.0
```

### 文件命名
```
All My AI_{version}_aarch64.dmg  # 安装包
All My AI_{version}_aarch64.dmg.sig  # updater 签名
latest.json                       # updater 元数据 (git push 更新)
```

## 发布流程

### 1. 构建（all-my-ai repo）
```bash
pnpm tauri:build:direct
# 签名 + notarization
# 生成 signature 文件
```

### 2. 上传 DMG（Pages repo）
```bash
gh release create all-my-ai-v{version} \
  --title "All My AI v{version}" \
  dmg文件 sig文件
```

### 3. 更新 latest.json（Pages repo）
编辑 `all-my-ai/latest.json`，更新 version、date、signature，然后：
```bash
git add all-my-ai/latest.json
git commit -m "Update All My AI to v{version}"
git push
```

Pages 会自动部署，URL：`https://alansuhe.github.io/all-my-ai/latest.json`

## 更新展示页

当新版本发布后，如需更新功能说明：
1. 编辑 `index.{lang}.md` 中的功能列表
2. 提交到 alansuhe.github.io repo
3. 推送后 GitHub Pages 自动更新

## 图标更新

如需更换图标：
1. 从 all-my-ai repo 复制 `src-tauri/icons/icon.png`
2. 替换 `apps/all-my-ai/assets/icon.png`
3. git push 更新