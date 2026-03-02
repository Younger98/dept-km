# API 總覽

> 內部 API 文件索引

## API 設計原則

- RESTful 風格
- 使用 JSON 格式
- JWT Token 認證
- 版本控制 (v1, v2...)

## 通用端點

### 認證
```
POST /api/v1/auth/login
POST /api/v1/auth/refresh
```

### 健康檢查
```
GET /api/v1/health
```

## 部門 API

| 部門 | API 前綴 | 說明 |
|------|----------|------|
| MLH100 | /api/v1/mlh100 | 核心交易 API |
| MLH200 | /api/v1/mlh200 | 營運 API |
| MLH300 | /api/v1/mlh300 | 數據 API |
| MLH500 | /api/v1/mlh500 | 前端 API |
| MLH600 | /api/v1/mlh600 | 基礎設施 API |
| MLH700 | /api/v1/mlh700 | 安全 API |
| MLH800 | /api/v1/mlh800 | 行動 API |
| MLH900 | /api/v1/mlh900 | 測試 API |

## 錯誤碼

| 狀態碼 | 說明 |
|--------|------|
| 200 | 成功 |
| 400 | 請求錯誤 |
| 401 | 未授權 |
| 404 | 資源不存在 |
| 500 | 伺服器錯誤 |

## 相關文件

- [認證文件](../api/authentication.md)
- [錯誤處理](../api/errors.md)
