# Git 工作流程

> 團隊協作時的 Git 使用規範

## 分支命名

| 類型 | 格式 | 範例 |
|------|------|------|
| 功能 | feature/功能名稱 | feature/user-login |
| 修復 | bugfix/問題描述 | bugfix/fix-login-error |
| 熱修復 | hotfix/緊急修復 | hotfix/security-patch |
| 發布 | release/版本號 | release/v1.0.0 |

## Commit Message 規範

```
<類型>(<範圍>): <標題>

<正文>

<結尾>
```

### 類型
- `feat`: 新功能
- `fix`: Bug 修復
- `docs`: 文件更新
- `style`: 格式調整
- `refactor`: 重構
- `test`: 測試
- `chore`: 維護

### 範例
```
feat(auth): 新增 Google 登入功能

- 新增 Google OAuth2 整合
- 更新用戶資料表結構

Closes #123
```

## 常用指令

```bash
# 建立功能分支
git checkout -b feature/new-feature

# 提交變更
git add .
git commit -m "feat: add new feature"

# 合併到主分支
git checkout main
git merge feature/new-feature
```

## Pull Request 流程

1. 從 `main` 建立分支
2. 開發並提交
3. 發起 PR
4. 經過 code review
5. 合併到 `main`
