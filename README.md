# LINE 電子名片產生器

填表單、上傳照片、下載打包檔，做出一張可以在 LINE 裡傳送的電子名片。不用寫程式。

**使用網址：** https://chenyungchu.github.io/card/

## 這個工具做什麼

產出三個檔案：

| 檔案 | 用途 |
|---|---|
| `index.html` | 自我介紹網站，照片已內嵌，單一檔案就能跑 |
| `card.png` | 1040×1040，給 LINE 官方帳號的「圖文訊息」 |
| `card-flex.jpg` | 給在聊天室分享名片時顯示的圖 |

搭配起來的效果：別人在 LINE 收到一張名片圖，點下去開啟你的自我介紹網站。

## 使用流程

1. 開 https://chenyungchu.github.io/card/
2. 填六格表單、拖一張照片進去，右邊即時預覽
3. 按「下載名片包」拿到 ZIP
4. 解壓縮，把**整個資料夾**拖到 https://app.netlify.com/drop
5. **立刻按 Claim 綁定帳號**（Google 或 GitHub 一鍵登入，免費）
   — 沒綁定的話網站一小時後會自動消失
6. 拿到網址，照 ZIP 裡的「說明.txt」設定 LINE 官方帳號

## 隱私

純前端，沒有後端。你填的資料和上傳的照片**只存在你自己的瀏覽器裡**，
不會上傳到任何伺服器，也不會進到這個 repo。關掉分頁資料還在（存在瀏覽器本機），
換一台電腦就沒了。

## 技術

單一 HTML 檔，無建置流程。只用到一個外部套件 [JSZip](https://stuk.github.io/jszip/)（打包用）。
名片圖以原生 Canvas 繪製。

要改網站樣板改 `const TPL`；要改名片圖改 `drawFull()`（滿版）或 `drawFrame()`（框式）。
