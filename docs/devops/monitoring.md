# 監控

> 系統監控與警報說明

## 監控工具

| 工具 | 用途 |
|------|------|
| Prometheus | 指標收集 |
| Grafana | 儀表板顯示 |
| AlertManager | 警報通知 |
| ELK | 日誌管理 |

## 關鍵指標

| 指標 | 警報閾值 |
|------|----------|
| CPU 使用率 | > 80% |
| 記憶體 | > 85% |
| 錯誤率 | > 1% |
| 回應時間 P99 | > 2s |

## 儀表板

- [Grafana](https://grafana.example.com) - 主要監控儀表板
- [Kibana](https://kibana.example.com) - 日誌查詢

## 警報頻道

- Slack: #alerts
- Email: oncall@example.com
