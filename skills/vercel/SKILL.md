---
name: vercel-cli
description: 使用 Vercel CLI 部署與管理專案。說「部署到 Vercel」「vercel deploy」「vercel 設定」時載入。
---

# Vercel CLI

版本：`vercel@52.0.0`（via nvm）

## 安裝

```bash
npm install -g vercel
vercel --version
```

登入：
```bash
vercel login    # 瀏覽器 OAuth
```

## 常用指令

### 部署
```bash
vercel                   # 部署到預覽環境（Preview）
vercel --prod            # 部署到正式環境（Production）
vercel deploy --prod     # 同上，明確指定
```

### 環境變數
```bash
vercel env ls            # 列出所有環境變數
vercel env add NAME      # 新增（互動式，可選 production/preview/development）
vercel env rm NAME       # 刪除
vercel env pull .env.local  # 拉到本地 .env.local
```

### 專案與 Domain
```bash
vercel ls                # 列出所有部署
vercel inspect [url]     # 查看部署詳細資訊
vercel alias set [url] [domain]  # 設定自訂 domain
vercel rollback          # 回滾到上一個 production 部署
```

### 日誌與除錯
```bash
vercel logs [url]        # 查看部署日誌
vercel dev               # 本地開發伺服器（模擬 Vercel 環境）
```

## 慣例

- 部署到 `--prod` 前先確認目前 branch 是否正確
- 環境變數不寫進 repo，用 `vercel env pull` 拉到本地
- `.env.local` 加入 `.gitignore`
- 優先用 `vercel dev` 本地測試，再部署預覽，確認後才 `--prod`
