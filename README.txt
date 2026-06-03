Happy English Adventure 測試版 (v13)

使用方式：
1. 開啟資料夾。
2. 雙擊 index.html 開啟遊戲（無需伺服器，離線即可執行）。

注意：v13 已將單一檔案拆分為多個檔案，請確保 index.html 與
style.css、data.js、app.js、jszip.min.js 在同一目錄下。

v13 更新內容（2026-06-03）：
1. 【BUG 修正】修復 v12 拆分時的三個問題：
   - 移除 data.js 開頭的 BOM（Byte Order Mark），避免瀏覽器解析錯誤。
   - 修正 AVATAR_MAP 結尾無分號時誤將 function avatarImg 一併擷取的問題。
   - 修正 TOPICS 的 .map() 鏈式呼叫被截斷，遺失 method chain 的問題。
2. 【功能改善】首次啟動時若無卡片，自動呼叫 replaceCards() 存入 IndexedDB。

v12 更新內容（2026-06-03）：
1. 【架構重構】將原本 19MB 的單一 index.html 拆分為五個檔案：
   index.html（骨架）、style.css（樣式）、data.js（圖卡資料庫）、
   app.js（遊戲邏輯）、jszip.min.js（ZIP 匯入函式庫）。
   好處：各檔案可獨立快取、平行載入、方便維護。
2. 【效能優化】150 張內建圖卡僅在首次開啟時自動存入 IndexedDB，
   之後直接從瀏覽器資料庫讀取，無需每次載入 16MB 的 Base64 資料，
   大幅縮短啟動時間。
3. 【檔案尺寸】index.html 由 19MB 降至 0.4KB；data.js（11.8MB）
   與 app.js（4.3MB）可分開快取，修改邏輯時不需重載圖卡資料。
4. 【向後相容】進版／恢復內建教材等既有功能完全保留，操作不變。

v11 更新內容（2026-06-03）：
1. 重新命名為「測試版 (v11)」，作為後續迭代基底。
2. 移除 loading 載入畫面，開場直達首頁，減少等待感。
3. 三個功能鍵統一使用自訂圖示（Home、喇叭開/關），以 CSS 標準化
   大小（32×32）並加白色背景遮罩去背瑕疵。
4. 移除已無用的 IMG_HERO（跳轉圖）常量，節省約 2.1 MB。
5. 圖片集中管理為 JS 變數，避免重複內嵌，檔案體積縮小約 4MB。

v10 更新內容（略，請參閱 v11 版本 README）
