
# 即時文字雲遊戲（張學友形容詞）

此專案為可直接部署的單頁網站：玩家輸入形容詞，立即生成文字雲，並透過 Firebase Realtime Database 即時同步多人輸入。

## 部署到 GitHub Pages
1. 建立 **Public** 的 GitHub Repository（例如 `jacky-wordcloud`）。
2. 上傳/提交 `index.html` 與 `README.md` 到 `main` 分支。
3. 進入 **Settings → Pages**：
   - Build and deployment → Source：選 **Deploy from a branch**
   - Branch：選 `main`；資料夾選 `/root`
4. 儲存後等約 1 分鐘，即可取得公開網址。

## Firebase 設定
本頁已整合你的 Firebase v12 Web 設定，並透過 Realtime Database 在路徑 `rooms/${ROOM_ID}/words` 讀寫資料。
- 你可在 `index.html` 中改動 `ROOM_ID`（預設為 `jacky-cheung-adjectives`）以分活動。
- 建議在活動結束後，更新 Realtime Database 安全規則以避免濫用。

## 使用方式
- 直接打開頁面，輸入形容詞（可一次輸入多個，支援空格、逗號、分號、頓號分隔），按「確定」，即時更新文字雲與排行榜。
- 多位玩家同時打開同一頁面（同一 `ROOM_ID`），即會即時同步。

## 技術
- d3.js + d3-cloud 生成中文友好的文字雲。
- Firebase v12 模組版（Analytics、Realtime Database）。
