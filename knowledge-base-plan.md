# 📚 部門共用知識庫建置計畫

> 8個部門開發團隊共用知識庫 - End-to-End 流程規劃

---

## 📋 專案概述

- **工具**: MkDocs (靜態網站產生器)
- **目標**: 8個部門開發團隊共用知識庫
- **托管**: 可部署至 GitHub Pages / GitLab Pages / 內部伺服器

---

## 🏗️ 組織結構

**應用系統管理處 - 8個部門**
- MLH100
- MLH200
- MLH300
- MLH500
- MLH600
- MLH700
- MLH800
- MLH900

```
knowledge-base/
├── docs/
│   ├── index.md                    # 首頁
│   ├── getting-started/            # 新手上路
│   ├── architecture/               # 系統架構
│   ├── api/                        # API 文件
│   ├── devops/                     # DevOps 手冊
│   ├── security/                   # 安全規範
│   ├── departments/                # 各部門專區
│   │   ├── mlh100/
│   │   ├── mlh200/
│   │   ├── mlh300/
│   │   ├── mlh500/
│   │   ├── mlh600/
│   │   ├── mlh700/
│   │   ├── mlh800/
│   │   └── mlh900/
│   └── templates/                  # 文件範本
├── mkdocs.yml                     # MkDocs 配置
└── requirements.txt               # Python 依賴
```

---

## 🔄 End-to-End 流程

### 1️⃣ 知識庫規劃階段
| 項目 | 負責人 | 產出 |
|------|--------|------|
| 確認8個部門名稱與需求 | 阿格蝦 | 部門清單 |
| 決定文件結構與分類 | 全體討論 | docs/目錄結構 |
| 制定文件規範 | Coder + QA | style-guide.md |

### 2️⃣ 文件撰寫階段
| 流程 | 說明 |
|------|------|
| 2.1 | 各部門指定文件負責人 (Document Owner) |
| 2.2 | 負責人建立草稿 (Markdown) |
| 2.3 | 提交 Pull Request 到 develop 分支 |
| 2.4 | CI 自動檢查 (連結、語法、格式) |

### 3️⃣ 審核階段
| 流程 | 說明 |
|------|------|
| 3.1 | 部門內部審核 (至少1人) |
| 3.2 | 跨部門審核 (Tech Lead) |
| 3.3 | 技術正確性審核 (Coder) |
| 3.4 | 格式一致性審核 (QA) |
| 3.5 | 核准後 Merge 到 main 分支 |

### 4️⃣ 發布階段
| 流程 | 說明 |
|------|------|
| 4.1 | Merge 觸發自動化部署 |
| 4.2 | MkDocs 編譯 HTML |
| 4.3 | 部署到預覽環境 |
| 4.4 | 正式上線 |

### 5️⃣ 維護階段
| 項目 | 頻率 |
|------|------|
| 文件更新 | 隨需 |
| 連結檢查 | 每週自動化 |
| 內容審閱 | 每月 |
| 版本快照 | 每季 |

---

## 👥 角色與權責

| 角色 | 權責 |
|------|------|
| Document Owner | 撰寫、維護該部門文件 |
| Reviewer | 審核文件內容正確性 |
| Approver | 核准發布 (Tech Lead) |
| DevOps | 維護部署流程與自動化 |

---

## 🛠️ 自動化工具

- **CI/CD**: GitHub Actions / GitLab CI
- **語法檢查**: markdownlint, textlint
- **連結檢查**: lychee
- **搜尋**: MkDocs 內建 + Algolia (可選)

---

## 📅 初步時程

| 階段 | 工期 | 說明 |
|------|------|------|
| 規劃 | 1週 | 確認需求與結構 |
| 建置基礎設施 | 1週 | MkDocs 搭建 + CI |
| 部門文件上線 | 2-4週 | 各部門開始撰寫 |
| 試營運 | 1週 | 內部測試 |
| 正式上線 | - | 持續維護 |

---

## 📝 文件範本

### 1. 部門首頁範本 (index.md)

```markdown
# {部門名稱} {MLHXXX}

> 部門簡介（1-2句話說明部門職責）

## 👥 團隊成員

| 角色 | 姓名 | 聯絡方式 |
|------|------|----------|
| 部門主管 | XXX | xxx@company.com |
| 技術負責人 | XXX | xxx@company.com |
| 文件維護人 | XXX | xxx@company.com |

## 🖥️ 負責系統

| 系統名稱 | 說明 | 環境 |
|----------|------|------|
| 系統A | 核心交易系統 | Prod/Stage/Dev |
| 系統B | 資料同步服務 | Prod/Stage |

## 📞 聯絡方式

- 部門 Slack: #mlhxxx
- 緊急聯絡: xxx@company.com

## 📚 相關文件

- [技術架構](./architecture/)
- [API 文件](./api/)
- [操作手冊](./operations/)
```

### 2. 技術架構文件範本

```markdown
# {系統名稱} - 技術架構

## 📋 系統概述

簡要說明系統的目的、主要功能、目標用戶

## 🏗️ 架構圖

（在此插入架構圖，使用 Mermaid 或圖片）

## 💻 技術堆疊

| 層級 | 技術 | 版本 |
|------|------|------|
| 前端 | React | 18.x |
| 後端 | Node.js | 20.x |
| 資料庫 | PostgreSQL | 15.x |
| 快取 | Redis | 7.x |
| 部署 | Kubernetes | 1.28 |

## 🔄 數據流程

1. 使用者請求 → API Gateway
2. 認證驗證 → JWT Token
3. 業務處理 → Service Layer
4. 資料存取 → Repository Layer
5. 回應結果

## 🔌 外部依賴

| 服務 | 用途 | SLA |
|------|------|-----|
| 外部API A | 訂單查詢 | 99.9% |
| 訊息佇列 | 异步處理 | 99.5% |

## 📝 相關文件

- [API 文件](../api/)
- [部署流程](../operations/deployment.md)
```

### 3. API 文件範本

```markdown
# {系統名稱} API

## 🔧 認證方式

此 API 使用 JWT Token 認證，請在 Header 中加入：
```
Authorization: Bearer <token>
```

## 📡 端點列表

### GET /api/v1/{resource}

取得資源列表

**請求參數**
| 名稱 | 類型 | 必填 | 說明 |
|------|------|------|------|
| page | int | 否 | 頁碼，預設 1 |
| limit | int | 否 | 每頁數量，預設 20 |

**回應範例**
```json
{
  "success": true,
  "data": [
    {
      "id": "123",
      "name": "Example",
      "createdAt": "2026-01-01T00:00:00Z"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 100
  }
}
```

**錯誤碼**
| 狀態碼 | 說明 |
|--------|------|
| 401 | 未授權 |
| 404 | 資源不存在 |
| 500 | 伺服器錯誤 |

---

### POST /api/v1/{resource}

建立新資源

**請求 body**
```json
{
  "name": "新名稱",
  "description": "描述"
}
```

**回應** (201 Created)
```json
{
  "success": true,
  "data": {
    "id": "124",
    "name": "新名稱"
  }
}
```

## 🔄 版本歷史

| 版本 | 日期 | 變更 |
|------|------|------|
| v1.0 | 2026-01-01 | 初始版本 |
```

### 4. 操作手冊範本

```markdown
# {系統名稱} - 操作手冊

## 🚀 部署流程

### 前置需求
- Docker 20.x+
- Kubernetes 1.28+
- Helm 3.x

### 部署步驟

1. 拉取最新映像檔
```bash
docker pull registry.company.com/app:v1.2.3
```

2. 更新 Helm
```bash
helm upgrade --install app ./chart -n production -f values-prod.yaml
```

3. 驗證部署
```bash
kubectl rollout status deployment/app -n production
```

## 📊 監控項目

| 指標 | 警報閾值 | 說明 |
|------|----------|------|
| CPU 使用率 | > 80% | 持續 5 分鐘 |
| 記憶體 | > 85% | 持續 5 分鐘 |
| 錯誤率 | > 1% | 持續 1 分鐘 |
| 回應時間 | P99 > 2s | 持續 5 分鐘 |

### 查看監控儀表板
- Grafana: https://grafana.company.com/d/app-{id}
- Dashboard Name: {系統名稱} Overview

## 🔧 故障排除

### 常見問題

**Q: 服務無法啟動**
A: 檢查環境變數是否正確設定，查看 logs:
```bash
kubectl logs -n production deploy/app --previous
```

**Q: API 回應緩慢**
A: 
1. 檢查資料庫連線池
2. 檢查 Redis 快取命中率
3. 查看是否有慢查詢

## 📋 緊急聯絡

| 狀況 | 聯絡人 | 電話 |
|------|--------|------|
| 系統故障 | On-Call Engineer | xxx-xxxx |
| 資料問題 | DBA Team | xxx-xxxx |
```

### 5. 文件撰寫風格指南

```markdown
# 📖 文件風格指南

## ✍️ 語法規範

### 標題層級
```
# H1 - 頁面標題
## H2 - 主要章節
### H3 - 子章節
#### H4 - 小節
```

### 程式碼區塊
- 使用三個反引號標記
- 指定語言以獲得語法高亮
- 避免過長的行

```yaml
# 好的範例
```yaml
name: example
version: 1.0.0
```

### 表格
- 使用 Markdown 表格格式
- 確保對齊
- 必要的欄位用粗體標示

### 圖片
- 放在 `docs/assets/images/` 目錄
- 使用相對路徑引用
- 建議尺寸: 最大寬度 800px

## 📏 命名規範

| 類型 | 規則 | 範例 |
|------|------|------|
| 檔案名稱 | kebab-case | `getting-started.md` |
| 標題 | Title Case | "Getting Started Guide" |
| API 端點 | RESTful | `/api/v1/users` |
| 變數 | camelCase | `userName` |

## 🔍 內容檢查清單

- [ ] 語法正確，無錯字
- [ ] 連結有效
- [ ] 圖片顯示正常
- [ ] 程式碼可執行
- [ ] 表格對齊
- [ ] 有目錄導航
```

---

_Last updated: 2026-03-01_

