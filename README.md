# ⚡ 閃電小偵探：反應力大挑戰

給 3–8 歲兒童的視覺辨識與反應力訓練小遊戲。在限時內從一堆雜物中找出指定目標。

## 玩法

1. 選擇難度（10 秒 / 5 秒倒數）
2. 看右側面板的目標物品
3. 在左邊地圖上點擊它
4. 共 10 關，難度逐步上升

## 特色

- 10 關遞進難度，覆蓋率從 50% → 60% → 80% → 90% 四階段
- 每關隨機場景（兒童房／公園／沙灘／廚房）
- 物件自動從 sprite sheet 切出、去背
- 關卡內物件保證不重複、不重疊
- 結算顯示完成總秒數

## 本地執行

因瀏覽器 `file://` 安全限制，需用 local server：

```bash
python -m http.server 8000
# 或
npx http-server -p 8000
```

然後打開 http://localhost:8000/

## 技術

- 單一 `index.html`（HTML + CSS + JS 全內嵌）
- 無框架、無 build step、無依賴
- 執行時用 Canvas 動態切圖：自動偵測 sprite sheet 背景色、連通區塊標記
- 物件放置用 jittered grid 演算法保證無重疊

## 素材

- `sprites.png` — 100 個物件的 10×10 sprite sheet，AI 生成
- `backgrounds.png` — 4 張場景背景，AI 生成
- `items.json` — 物件中文名稱對照表（可手動填入）

## 部署

純靜態網站，支援任何靜態 host：Vercel / Netlify / GitHub Pages 等。
