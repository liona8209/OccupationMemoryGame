# 🧠 職業病記憶配對遊戲

一個以純 HTML / CSS / JavaScript 打造的 3×4 記憶翻牌配對小遊戲，主題為常見職業病知識宣導。無需安裝、無需伺服器、開啟瀏覽器即可遊玩。

## 🎮 線上遊玩

透過 GitHub Pages 部署後，直接開啟以下網址即可遊玩（部署步驟見下方）：

```
https://<你的GitHub帳號>.github.io/<repo名稱>/
```

## 📁 專案結構

```
.
├── index.html        # 遊戲主檔案（結構 / 樣式 / 邏輯皆在此）
├── images/           # 遊戲使用的卡片圖片（已壓縮為 WebP）
└── Image/            # 原始高解析度素材（已於 .gitignore 排除，不會上傳）
```

## 🕹️ 遊戲規則

- 12 張卡片（6 種職業病圖示，各 2 張）以 3 欄 × 4 排排列。
- 點擊卡片翻面，翻開兩張後系統自動比對：
  - **相符**：卡片保持翻開，邊框呈現螢光綠發光效果，配對數 +1。
  - **不符**：卡片顯示 1 秒後自動翻回背面。
- 每翻開兩張卡片，步數 +1。
- 6 對全部配對成功即通關，顯示恭喜訊息與總步數。
- 可隨時點擊「重新開始」重新洗牌挑戰。

## 🚀 部署到 GitHub Pages

1. 在 GitHub 建立一個新的 repository（例如 `memory-match-game`）。
2. 將本專案推送上去：

   ```bash
   git init
   git add .
   git commit -m "Init: 職業病記憶配對遊戲"
   git branch -M main
   git remote add origin https://github.com/<你的帳號>/<repo名稱>.git
   git push -u origin main
   ```

3. 到 GitHub repository 的 **Settings → Pages**，Source 選擇 `main` 分支、目錄選 `/ (root)`，儲存。
4. 稍待片刻後，即可透過 `https://<你的帳號>.github.io/<repo名稱>/` 開啟遊戲。

## 🛠️ 技術重點

- **HTML5**：語意化結構與卡片 DOM 佈局。
- **CSS3**：Grid / Flexbox 排版、`transform-style: preserve-3d` + `rotateY` 3D 翻牌動畫、發光配對特效、RWD 響應式設計（支援手機／平板／桌機）。
- **Vanilla JavaScript (ES6+)**：Fisher-Yates 洗牌演算法、遊戲狀態管理、防重複點擊鎖定機制。

## 🖼️ 圖片素材

原始素材位於 `Image/` 資料夾（未納入版控，因檔案較大）；`images/` 資料夾內為遊戲實際使用、已壓縮為 WebP 格式的版本（單張約 30～60 KB），確保網頁載入快速。
