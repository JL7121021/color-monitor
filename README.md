# 多區域色彩監控器 / Multi-Zone Color Monitor

以瀏覽器螢幕分享即時監控 1–3 個區域的顏色變化；可設定靈敏度門檻、警報音、排程與外觀風格。純前端單一 HTML，沒有後端、沒有外部套件。

> 本 repo 只包含最新版 **v2.9.3**；舊版本未包含在這份上傳內容中。

## 功能 / Features

- 三區域獨立監控，可個別暫停
- **精準取樣**：單點取 1px，可達畫面四角；中央十字留空，方便對準
- **區域平均色**：取區塊平均 RGB
- 靈敏度門檻（1–50%）與即時色差百分比
- 警報音與警示橫幅（須手動按「解除警報」清除）
- 排程開始／停止；因瀏覽器限制，排程到點仍需手動按一次開始
- 繁中／英文即時切換
- 10 種外觀風格（含 Liquid Glass）、配色與背景印花，支援命名儲存／匯出／匯入 JSON
- 自我測試：5 項檢查，不會觸發警報
- 長跑健康狀態：最後取樣時間、停頓偵測、每 10 分鐘心跳紀錄、分頁回到前景自動重新取樣
- App 內建版本歷史（點標題列的版本標籤）

## 使用方式 / Usage

1. 開啟 GitHub Pages 網站（或本機 `http://localhost` 環境）。
2. 按「開始分享監控畫面」／“Start screen share”。
3. 在瀏覽器選單選擇要監控的分頁、視窗或整個畫面。
4. 拖曳虛線探針或檢測框到目標位置；精準取樣模式可點一下直接放置。
5. 調整靈敏度與間隔；必要時執行「自我測試」確認功能正常。

### 快捷鍵

| 操作 | 說明 |
| --- | --- |
| 方向鍵 | 微調選取的區域／探針 |
| Shift + 方向鍵 | 大步移動；區域模式下為調整大小 |
| 滾輪 / `+` / `-` | 縮放畫面 |
| 放大後拖曳背景 | 平移畫面 |

## 瀏覽器需求 / Requirements

- 建議使用最新版 Chrome 或 Edge。
- `getDisplayMedia` 需要 **HTTPS 或 localhost**；GitHub Pages 符合此條件。直接用 `file://` 開啟時，部分瀏覽器不允許螢幕分享。
- Safari 已針對 `<dialog closedby>` 做相容 fallback。

## 隱私 / Privacy

所有設定、外觀與區域座標只存在你自己的瀏覽器 LocalStorage（前綴 `job-monitor-v282-`，為相容舊設定保留）。沒有伺服器、沒有資料上傳、沒有分析或追蹤。

## 檔案 / Files

| 檔案 | 說明 |
| --- | --- |
| `index.html` | 完整應用程式，v2.9.3 |
| `CHANGELOG.md` | 版本變更紀錄 |
| `LICENSE` | 授權條款 |
| `.gitignore` | Git 忽略清單 |

## GitHub Pages

若 repo 是 public：進入 **Settings → Pages → Build and deployment**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)`，儲存後即可用 `https://<你的帳號>.github.io/<repo 名稱>/` 開啟。

## License

見 [LICENSE](LICENSE)（MIT）。
