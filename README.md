# 🤖 LINE to Google Drive 自動化備份機器人 (n8n)

這是一個基於 **n8n** 開發的自動化工作流，旨在解決 LINE 通訊軟體檔案保存期限過短的問題。透過此工具，機器人會自動將 LINE 接收到的檔案、圖片即時轉存至指定的 **Google Drive** 資料夾。

---

## 🌟 功能特點
* **自動轉存**：自動識別 LINE 訊息中的文件 (File) 與圖片 (Image) 並下載。
* **雲端備份**：即時上傳至 Google Drive 並自動開啟「知道連結即可檢視」的分享權限。
* **智能查詢**：在 LINE 輸入「檔案清單」即可透過 JavaScript 邏輯列出雲端硬碟中最新的 10 筆檔案及下載連結。
* **延時處理**：內建 Wait 節點，確保 LINE 伺服器檔案準備就緒，提高下載成功率。

---

## 🛠 使用技術
* **n8n**: 低代碼自動化平台 (Self-hosted / Cloud)。
* **LINE Messaging API**: 接收與回覆訊息。
* **Google Drive API**: 雲端儲存與權限控管。
* **JavaScript**: 處理 JSON 資料與自定義日期格式轉換。

---

## 🚀 如何快速部署

1. **環境準備**：確保你有一個可運行的 n8n 實例。
2. **匯入 JSON**：下載本專案的 `LINE_Drive_Bot.json`，在 n8n 介面點擊 **Import from File**。
3. **設定憑證 (Credentials)**：
    * **LINE API**：建立 `Header Auth`，Key 為 `Authorization`，Value 為 `Bearer {你的 Channel Access Token}`。
    * **Google Drive**：使用 OAuth2 完成授權。
4. **替換關鍵 ID**：
    * 進入 `Upload file` 與 `Search files` 節點，重新選擇你自己的 Google Drive 目標資料夾。
    * 在 LINE Developers Console 將 Webhook URL 設定為 n8n Webhook 節點產生的路徑。

---

## 📂 檔案結構說明
* `LINE_Drive_Bot.json`: 完整的工作流定義檔（已移除私密 ID）。
* `README.md`: 專案說明文件。

---

### 💡 後續優化方向
* [ ] 整合 Google Sheets 記錄所有上傳日誌。
* [ ] 加入 AI 影像辨識，自動分類圖片內容。

---
**如果你喜歡這個專案，歡迎給個 ⭐ Star！**
