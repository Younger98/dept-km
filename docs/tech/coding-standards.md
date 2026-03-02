# 程式碼規範

> 統一的程式碼撰寫規範，確保團隊協作的一致性

## 命名慣例

| 類型 | 規則 | 範例 |
|------|------|------|
| 變數 | camelCase | `userName`, `totalCount` |
| 常數 | UPPER_SNAKE_CASE | `MAX_RETRY`, `API_BASE_URL` |
| 函式 | camelCase | `getUserById()`, `calculateTotal()` |
| 類別 | PascalCase | `UserService`, `PaymentController` |
| 檔案 | kebab-case | `user-service.ts`, `api-client.js` |

## 程式碼格式

### JavaScript/TypeScript
```javascript
// 好
const user = {
  name: 'John',
  age: 30,
};

// 不好
const user = {name:'John',age:30};
```

### Python
```python
# 好
def calculate_total(items):
    return sum(item.price for item in items)

# 不好
def calculate_total(items):
    return sum(item.price for item in items)
```

## 註解規範

- 公共 API 必須有 JSDoc/Docstring
- 複雜邏輯需要說明
- 過長的函式應該拆分

## 參考資源

- [Google Style Guides](https://google.github.io/styleguide/)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
