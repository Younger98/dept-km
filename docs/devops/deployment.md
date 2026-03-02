# 部署指南

> DevOps 部署流程說明

## 部署環境

| 環境 | URL | 用途 |
|------|-----|------|
| Dev | dev.example.com | 開發測試 |
| Stage | stage.example.com | 正式上線前測試 |
| Prod | example.com | 正式環境 |

## 部署流程

### 1. 準備

```bash
git pull origin main
docker build -t app:latest .
```

### 2. 測試

```bash
docker-compose up -d
npm test
```

### 3. 部署

```bash
kubectl apply -f deployment.yaml
```

## 相關文件

- [監控](./monitoring.md)
- [安全規範](../security/overview.md)
