# 周易原始碼｜八字排盤、五行與 JavaScript 網頁資料

[简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.en.md) · [产品页面](https://niubideren111.github.io/I-Ching-Divination-System/zh-tw/)

以八字排盤網頁為進入點的周易開發資料，包含 JavaScript 公共函數、時區處理和截圖導出文件。專案还展示大六壬、流年、七政四余等頁面截圖，便於了解排盘類產品的介面組織。

**周易原始碼 · 八字排盤原始碼 · 易经原始碼 · JavaScript排盘**

## 專案重點

### 八字排盤網頁

根目錄 index.html 是原有排盘頁面；新增產品展示頁獨立放在 docs，保留原功能文件。

### 網頁辅助文件

common.js、utils.js、timezone.js 與 canvas2image.js 提供可閱讀的網頁配套資料。

### 排盘與五行設計資料

五行表格、說明文件和不同排盘介面截圖支援產品設計參考。

## 資料閱讀與核對方式

1. **先確認產品形態**：依序檢視截圖與圖說，確認產品類型和可見功能流程。
2. **再核對檔案證據**：直接開啟下方列出的原始碼或文件，不只依賴功能描述。
3. **檢查可建置範圍**：確認欲執行的部分是否具備相依套件、資源、設定與啟動腳本。
4. **確認授權**：閱讀儲存庫授權；商業素材及完整工程交付應另行取得書面授權。

## 產品截圖

![周易八字排盤與干支資訊頁面](docs/assets/seo/i-ching-divination-system-01.jpg)

![大六壬排盘表格頁面](docs/assets/seo/i-ching-divination-system-02.jpg)

![流年資訊與排盘資料列表](docs/assets/seo/i-ching-divination-system-03.jpg)

![八字排盤資訊彙總頁面](docs/assets/seo/i-ching-divination-system-04.jpg)

## 公開原始碼與資料

| 文件 | 说明 |
|---|---|
| [index.html](index.html) | 原有八字排盤網頁 |
| [common.js](common.js) | 公共 JavaScript 文件 |
| [timezone.js](timezone.js) | 時區處理資料 |
| [canvas2image.js](canvas2image.js) | 畫布圖片導出文件 |
| [五行数值328.xlsx](%E4%BA%94%E8%A1%8C%E6%95%B0%E5%80%BC328.xlsx) | 五行數值表 |
| [docs/algorithm_api.md](docs/algorithm_api.md) | 已有算法介面文件 |

## 開始閱讀

```bash
git clone https://github.com/niubideren111/I-Ching-Divination-System.git
cd I-Ching-Divination-System
```

## 常見問題

### 新增展示頁會覆盖原排盘功能吗？

不會。產品展示頁位於 docs/index.html，根目錄的排盘 index.html 保留。

### 截圖中的所有排盘算法都已公開吗？

當前公開進入點以八字排盤頁面和配套 JavaScript 為主；其他截圖用於介绍產品介面範圍。

## 後續資料完善方向

為每种已公開算法补輸入、輸出和測試样例；標明歷法、時區和换日規則。不要用文化產品頁面承诺預測效果。 後續更新還應加入版本化相依清單、經過驗證的建置或匯入步驟、簡明架構／產品流程圖，以及能對應真實檔案變更的版本記錄。大型授權資源可放入 GitHub Releases 並提供校驗值，不能提交密鑰、生產位址或使用者資料。

## 相關專案

- [Chess-and-Card-Game-Product-Design-Copy](https://github.com/niubideren111/Chess-and-Card-Game-Product-Design-Copy)

## 資料範圍與授權

公開儲存庫包含八字排盤 index.html、JavaScript 文件、設計資料和多類排盘截圖。截圖展示範圍不等於所有算法模組均已公開。 公開內容以實際檔案、相依套件與授權為準，不承諾搜尋排名、直接上線或固定效能結果。

- Telegram: [@fox_lovemyself](https://t.me/fox_lovemyself)
- GitHub: [I-Ching-Divination-System](https://github.com/niubideren111/I-Ching-Divination-System)
