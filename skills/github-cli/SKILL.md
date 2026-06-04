---
name: github-cli
description: 使用 GitHub CLI (gh) 操作 PR、Issue、Release、Actions。說「建立 PR」「gh pr」「github issue」「查看 CI」時載入。
---

# GitHub CLI (gh)

版本：`gh@2.91.0`

## 安裝

```bash
# Debian / Ubuntu
sudo apt install gh

# macOS
brew install gh

# 或從官方下載：https://cli.github.com
```

登入：
```bash
gh auth login   # 瀏覽器 OAuth，選 GitHub.com → HTTPS → Login with browser
gh auth status  # 確認登入狀態
```

## 常用指令

### Pull Request
```bash
gh pr create             # 建立 PR（互動式）
gh pr create --title "..." --body "..." --base main
gh pr list               # 列出 PR
gh pr view [number]      # 查看 PR 詳情
gh pr checkout [number]  # 切換到 PR branch
gh pr merge [number]     # 合併 PR
gh pr close [number]     # 關閉 PR
gh pr review --approve   # 審核通過
```

### Issue
```bash
gh issue create          # 建立 Issue（互動式）
gh issue list            # 列出 Issue
gh issue view [number]   # 查看 Issue
gh issue close [number]  # 關閉 Issue
gh issue edit [number]   # 編輯 Issue
```

### Actions / CI
```bash
gh run list              # 列出最近的 workflow runs
gh run view [id]         # 查看 run 詳情
gh run watch             # 即時監看當前 run
gh run rerun [id]        # 重新執行失敗的 run
gh workflow list         # 列出所有 workflow
gh workflow run [name]   # 手動觸發 workflow
```

### Release
```bash
gh release create v1.0.0 # 建立 release（互動式）
gh release list          # 列出 release
gh release view v1.0.0   # 查看 release
```

### Repo
```bash
gh repo view             # 在瀏覽器開啟目前 repo
gh repo clone owner/repo # Clone repo
gh repo fork             # Fork repo
gh gist create file.txt  # 建立 Gist
```

## 慣例

- PR title 使用 `type: description` 格式（feat / fix / chore / docs）
- 合併前先確認 CI 通過：`gh run watch`
- 不強制推送（`--force`）到 main/master
- PR body 包含 Summary、Test plan、截圖（UI 變更時）
