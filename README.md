# YouTube 跟讀播放器（GitHub Pages 版）

這是一個單檔 `index.html` 的 YouTube 跟讀工具，目標是「免伺服器、可直接放 GitHub Pages、手機可用」。

## 目前功能

- 深色模式介面（Tailwind CSS）。
- 貼上 YouTube 網址後自動載入影片。
- 透過免金鑰字幕 API 嘗試抓字幕（先 Supadata，再備援來源）。
- 列出所有字幕行。
- 點擊任一字幕行可跳到該句開始時間。
- 每行都有 `🔁 循環` 按鈕，可單句重複播放。
- 手機友善：按鈕高度加大、間距加大，方便點擊。

## 檔案結構

- `index.html`：全部前端邏輯（UI、YouTube 播放器、字幕抓取、跳轉與循環）。
- `README.md`：專案說明與維護紀錄。

## 如何在本機使用

1. 直接用瀏覽器開啟 `index.html`。
2. 貼上 YouTube 網址（例如 `https://www.youtube.com/watch?v=...`）。
3. 按「載入影片與字幕」。
4. 看到字幕列表後：
   - 點「跳到這句」可跳轉播放。
   - 點 `🔁 循環` 可重播該句，點「停止循環」可解除。

## 如何免費部署到 GitHub Pages（手機可直接連）

1. 在 GitHub 建立新 repository（例如 `youtube-shadowing-player`）。
2. 把目前專案檔案上傳（至少 `index.html`、`README.md`）。
3. 到 repository 的 **Settings** → **Pages**。
4. **Build and deployment** 選：
   - Source: `Deploy from a branch`
   - Branch: `main`（或你的分支）/ root
5. 儲存後等待 1~3 分鐘，會出現網址：
   - `https://<你的帳號>.github.io/<repo名稱>/`
6. 用手機開啟該網址即可使用。

## 注意事項（重要）

- 由於字幕 API 是第三方服務，可能受限於：
  - CORS 規則
  - 配額限制
  - 回傳格式變動
- 如果某天無法抓字幕，不代表網頁壞掉，可能是 API 服務策略改變。可替換 `index.html` 內 `providers` 陣列中的來源。

## 維護規則（每次修改都要更新）

之後每一次功能修改，請同步更新本檔：

- `目前功能`：反映實際功能狀態。
- `檔案結構`：若新增檔案要補上。
- `注意事項`：記錄新的相依風險或限制。
- `更新紀錄`：新增一筆變更說明。

## 更新紀錄

- 2026-02-22
  - 建立首版：單檔 `index.html` 的跟讀播放器。
  - 完成字幕抓取、點擊跳句、單句循環、手機友善按鈕。
  - 補上 GitHub Pages 上線教學與維護規則。

