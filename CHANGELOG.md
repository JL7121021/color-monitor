# Changelog

This repo contains only the latest version, v2.9.5. Older versions are not included.

## v2.9.5 — 2026-11-25

### Added
- Day / Night switch in the Looks panel; it works for all 8 styles, is remembered with saved looks, and restores before first paint.

### Changed
- Rebuilt Neumorphism from the reference designs: light-grey raised surfaces on a white page, transparent rims, paired light/dark shadows, recessed inputs and inset pressed feedback. Night uses a dark page with slate surfaces and softened shadows.
- Terminal is now a true phosphor CRT look with square corners, scanlines, a blinking cursor and prompt prefixes. A pale phosphor Day variant is included.

### Fixed
- Neumorphism page and surface colors are no longer identical, so the right/bottom shadow reads correctly instead of looking flat or uneven.

## v2.9.4 — 2026-11-25

### Added
- Three-step coach mark (start → place probe → live/alarm) with live bilingual text and a dismiss button.

### Changed
- Reduced the style kit from 10 to 8 looks; Glass and Liquid Glass were removed and saved looks using them fall back to Original.

### Fixed
- First sample now waits for two fresh decoded video frames and rebuilds the baseline from that settled frame, fixing incorrect initial colors.
- Handled the case where video metadata is already ready before the handler is attached, so the stage size is correct on the first sample.
- Neumorphism: restored visible boundaries on cards, inputs, health status, separators, alarm banner and buttons, replacing leftover hard geometric borders/shadows with soft tokens.

## v2.9.3 — 2026-11-25

### Added
- 自我測試（螢幕擷取 API、像素取樣、色差、靈敏度門檻、警報流程），結果不觸發警報並隨語言切換更新。
- 長跑健康監控：最後取樣相對時間、停頓 watchdog、每 10 分鐘 `[HEALTH]` 心跳、分頁回到前景立即重新取樣。
- App 內版本歷史；點標題列版本標籤可開啟並捲至歷史區。
- 外觀面板 CSS anchor positioning，舊瀏覽器提供 JS 視窗邊界 clamp fallback。
- 精準取樣探針加大透明抓取範圍，拖曳時快取舞台座標以避免 forced reflow。

### Changed
- 「單點模式」改名為「精準取樣」／“Precision point”。
- 十字中央改為真正透明：線段中段挖空，取樣像素不被遮蓋。
- 拖曳或停留於探針時隱藏系統游標，由 reticle 本身對準。

### Fixed
- 中央「開始分享監控畫面」按鈕被影片層覆蓋而無法點擊。
- 切換檢測模式時未重設基準值造成的誤警報；加入 `[MODE]` 紀錄與重設寬限期。
- 精準取樣改用獨立 `zone.point` 座標，可精確到畫面四角；舊設定自動從框中心遷移。

## 先前版本

v2.9.2 與更早版本的變更摘要仍保留在 App 內的版本歷史對話框中。
