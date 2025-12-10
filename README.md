# 這是專案的說明文件，包含了完整的配置指南。

# ⚡ ECH Tunnel + Cloudflare Argo Quick Tunnel Docker 專案

這個專案將 **ech-server**、**Opera Proxy**（可選）和 **Cloudflare Argo Quick Tunnel** 整合到一個輕量級的 Docker 容器中，用於快速建立一個臨時的 WSS/ECH 連線通道。

---

## 🚀 快速開始

### 1. 構建 Docker 映像檔

請確保您已安裝 Docker。在專案根目錄執行以下命令：

```bash
docker build -t ech-tunnel-argo .

### 2.透過設定環境變數 (-e) 來客製化服務的運行方式。

環境變數	預設值	說明	可選值
OPERA	   0	是否啟用 Opera 前置代理。	1 (啟用) / 0 (禁用)
COUNTRY	 AM	Opera 代理的國家/地區代碼 (僅在 OPERA=1 時有效)。	AM (北美) / AS (亞太) / EU (歐洲)
WSPORT	 隨機	ECH 服務在容器內部監聽的端口。	任何未使用的端口號 (例如 10000)
IPS	     4	Cloudflared 連接模式。	4 (IPv4) / 6 (IPv6)
TOKEN	   "" (空)	ECH Tunnel 的身份令牌。	任何字串

ARGO_DOMAIN 固定隧道名
ARGO_AUTH 隧道的TOKEN
