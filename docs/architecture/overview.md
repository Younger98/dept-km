# 系統架構總覽

> 應用系統管理處系統架構說明

## 架構原則

- **微服務架構** - 各部門獨立服務
- **雲端原生** - 使用 Kubernetes 部署
- **API First** - 所有服務透過 API 溝通

## 核心元件

| 元件 | 用途 | 技術 |
|------|------|------|
| API Gateway | 統一入口 | Kong / Nginx |
| 認證服務 | 用戶認證 | OAuth2 / JWT |
| 訊息佇列 | 异步處理 | RabbitMQ / Kafka |
| 資料庫 | 資料儲存 | PostgreSQL / MySQL |
| 快取 | 效能優化 | Redis |
| 監控 | 系統監控 | Prometheus / Grafana |

## 部門職責

| 部門 | 主要負責系統 |
|------|-------------|
| MLH100 | 核心交易系統 |
| MLH200 | 營運管理系統 |
| MLH300 | 數據分析平台 |
| MLH500 | 前端框架 |
| MLH600 | 基礎設施 |
| MLH700 | 安全合規 |
| MLH800 | 行動應用 |
| MLH900 | 測試自動化 |

## 相關文件

- [API 文件](../api/overview.md)
- [DevOps 手冊](../devops/deployment.md)
