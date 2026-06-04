---
name: firebase-cli
description: 使用 Firebase CLI 部署與管理 Firebase 服務。說「部署到 Firebase」「firebase deploy」「firebase 設定」「開 emulator」時載入。
---

# Firebase CLI

版本：`firebase@15.19.0`（via nvm）

## 安裝

```bash
npm install -g firebase-tools
firebase --version
```

登入：
```bash
firebase login   # 瀏覽器 OAuth
```

## 常用指令

### 登入與專案
```bash
firebase login           # 瀏覽器 OAuth 登入
firebase login --reauth  # 重新登入
firebase projects:list   # 列出所有專案
firebase use [project-id]       # 切換預設專案
firebase use --add       # 新增專案別名（如 staging / prod）
```

### 部署
```bash
firebase deploy                        # 部署所有服務
firebase deploy --only hosting         # 只部署 Hosting
firebase deploy --only functions       # 只部署 Functions
firebase deploy --only firestore:rules # 只部署 Firestore 規則
firebase deploy --only storage:rules   # 只部署 Storage 規則
firebase deploy --project prod         # 指定專案部署
```

### Emulator（本地開發）
```bash
firebase emulators:start               # 啟動所有 emulator
firebase emulators:start --only hosting,functions  # 指定服務
firebase emulators:exec "npm test"     # 在 emulator 環境執行測試
```

### Functions
```bash
firebase functions:log               # 查看 Functions 日誌
firebase functions:shell             # 互動式測試 Functions
firebase functions:delete [name]     # 刪除指定 Function
```

### Hosting
```bash
firebase hosting:channel:create preview  # 建立預覽 channel
firebase hosting:channel:deploy preview  # 部署到預覽 channel
firebase hosting:channel:list            # 列出所有 channel
```

## 慣例

- 本地開發先用 `emulators:start`，不動正式資料庫
- 多環境用 `.firebaserc` 的 alias 管理（`staging` / `prod`）
- 部署正式環境前確認 `firebase use` 指向正確專案
- Functions 環境變數用 `firebase functions:config:set`，不寫進 repo
- Firestore / Storage rules 改動後要加上對應的測試
