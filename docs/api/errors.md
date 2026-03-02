# 錯誤處理

## 錯誤回應格式

```json
{
  "error": {
    "code": "ERR_CODE",
    "message": "錯誤訊息",
    "details": {}
  }
}
```

## 錯誤碼列表

| 錯誤碼 | 狀態碼 | 說明 |
|--------|--------|------|
| INVALID_REQUEST | 400 | 請求格式錯誤 |
| UNAUTHORIZED | 401 | 未授權 |
| FORBIDDEN | 403 | 權限不足 |
| NOT_FOUND | 404 | 資源不存在 |
| RATE_LIMITED | 429 | 請求過多 |
| INTERNAL_ERROR | 500 | 伺服器錯誤 |
