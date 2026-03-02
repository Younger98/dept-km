# 認證方式

所有 API 需要 JWT Token 認證。

## 取得 Token

```bash
curl -X POST https://api.example.com/api/v1/auth/login \
  -H "Content-Type: application/json" \
  -d '{"username": "user", "password": "pass"}'
```

## 回應

```json
{
  "access_token": "eyJhbGc...",
  "refresh_token": "eyJhbGc...",
  "expires_in": 3600
}
```

## 使用 Token

在請求 Header 中加入：

```
Authorization: Bearer <access_token>
```
