# API 設計原則

> RESTful API 設計最佳實踐

## URL 設計

### 資源導向
```
# 好
GET    /api/v1/users
GET    /api/v1/users/123
POST   /api/v1/users
PUT    /api/v1/users/123
DELETE /api/v1/users/123

# 不好
GET    /api/v1/getUsers
POST   /api/v1/createUser
```

### 階層結構
```
# 巢狀資源
GET /api/v1/users/123/orders
POST /api/v1/users/123/orders

# 篩選與分頁
GET /api/v1/users?page=1&limit=20&status=active
```

## HTTP 方法對應

| 方法 | 用途 | 範例 |
|------|------|------|
| GET | 取得資源 | GET /users |
| POST | 建立新資源 | POST /users |
| PUT | 完整更新 | PUT /users/123 |
| PATCH | 部分更新 | PATCH /users/123 |
| DELETE | 刪除資源 | DELETE /users/123 |

## 狀態碼

| 狀態碼 | 說明 |
|--------|------|
| 200 | 成功 |
| 201 | 建立成功 |
| 400 | 請求錯誤 |
| 401 | 未授權 |
| 404 | 資源不存在 |
| 500 | 伺服器錯誤 |

## 版本控制

```
/api/v1/users
/api/v2/users
```

## 錯誤回應格式

```json
{
  "error": {
    "code": "USER_NOT_FOUND",
    "message": "用戶不存在",
    "details": {}
  }
}
```
