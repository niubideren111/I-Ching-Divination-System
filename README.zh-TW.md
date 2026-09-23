# 周易排盤源碼｜八字、五行、紫微斗數與奇門遁甲資料

[簡體中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.en.md) · [產品頁面](https://niubideren111.github.io/I-Ching-Divination-System/zh-tw/)

以八字排盤網頁為入口的周易開發資料，包含 JavaScript 公共函數、時區處理和截圖匯出檔案。專案也展示大六壬、流年、七政四餘等頁面截圖，便於了解排盤類產品的介面組織。

**周易源碼 · 易經源碼 · 八字源碼 · 八字排盤 · 紫微斗數 · 奇門遁甲 · 七政四餘**

## 簡介

這是一個以瀏覽器端八字排盤頁面為公開執行入口的周易開發資料庫。根目錄 `index.html` 提供出生日期、時間、性別等輸入，顯示四柱干支、十神、藏干、大運、流年和換運相關資訊；`common.js`、`utils.js`、`timezone.js` 與 `canvas2image.js` 提供公共邏輯、時區處理和結果圖片匯出支援。

儲存庫文件也整理紫微斗數、奇門遁甲、大六壬、七政四餘等排盤介面結構和產品頁面參考。目前公開檔案中，這些擴充術數以介面文件或截圖資料為主；是否具備完整演算法實作，應以實際原始碼檔案為準。

## 功能特性

| 功能 | 公開實作或資料範圍 |
|---|---|
| 四柱八字排盤 | 年柱、月柱、日柱、時柱的網頁展示入口 |
| 十神與藏干 | 四柱對應的十神、藏干資訊區域 |
| 大運與流年 | 大運、流年及換運時間相關介面和資料展示 |
| 出生資訊輸入 | 日期、時間、性別等排盤參數入口 |
| 時區處理 | `timezone.js` 提供時區輔助資料 |
| 排盤結果匯出 | `canvas2image.js` 提供 Canvas 圖片匯出支援 |
| 五行資料 | 五行數值表、說明文件和干支序 PDF |
| 紫微斗數資料 | `docs/algorithm_api.md` 中的介面與資料結構說明 |
| 奇門遁甲資料 | 文件中的時盤、局數和方位介面示例 |
| 七政四餘資料 | 文件中的星曜排盤資料結構及產品截圖參考 |
| 大六壬資料 | 產品介面截圖及演算法文件中的擴充模組說明 |
| 靜態網頁部署 | HTML + JavaScript，可依部署文件使用靜態網站託管 |

## 技術組成與公開範圍

| 層級 | 內容 |
|---|---|
| 頁面層 | HTML、CSS、原生 JavaScript 八字排盤頁面 |
| 工具層 | 公共函數、日期／時區輔助和 Canvas 圖片匯出 |
| 資料內容 | 五行數值、干支序和相關說明檔案 |
| 介面文件 | 八字、紫微斗數、奇門遁甲、七政四餘等資料結構示例 |
| 展示資料 | 八字、大六壬、流年及其他排盤介面截圖 |

本專案適合作為傳統文化排盤頁面、資料結構和介面設計的學習參考。排盤規則涉及曆法、時區、真太陽時、換日和流派差異，正式使用前需要以權威曆書及測試樣例複核，不應將展示結果視為現實決策依據。

## 專案重點

### 八字排盤網頁

根目錄 index.html 是原有排盤頁面；新增產品展示頁獨立放在 docs，保留原功能檔案。

### 網頁輔助檔案

common.js、utils.js、timezone.js 與 canvas2image.js 提供可閱讀的網頁配套資料。

### 排盤與五行設計資料

五行表格、說明文件和不同排盤介面截圖支援產品設計參考。

## 資料閱讀與核對方式

1. **先確認產品形態**：依序檢視截圖與圖說，確認產品類型和可見功能流程。
2. **再核對檔案證據**：直接開啟下方列出的原始碼或文件，不只依賴功能描述。
3. **檢查可建置範圍**：確認欲執行的部分是否具備相依套件、資源、設定與啟動腳本。
4. **確認授權**：閱讀儲存庫授權；商業素材及完整工程交付應另行取得書面授權。

## 產品截圖

![周易八字排盤與干支資訊頁面](docs/assets/seo/i-ching-divination-system-01.jpg)

![大六壬排盤表格頁面](docs/assets/seo/i-ching-divination-system-02.jpg)

![流年資訊與排盤資料列表](docs/assets/seo/i-ching-divination-system-03.jpg)

![八字排盤資訊彙總頁面](docs/assets/seo/i-ching-divination-system-04.jpg)

## 公開原始碼與資料

| 檔案 | 說明 |
|---|---|
| [index.html](index.html) | 原有八字排盤網頁 |
| [common.js](common.js) | 公共 JavaScript 檔案 |
| [timezone.js](timezone.js) | 時區處理資料 |
| [canvas2image.js](canvas2image.js) | 畫布圖片匯出檔案 |
| [五行数值328.xlsx](%E4%BA%94%E8%A1%8C%E6%95%B0%E5%80%BC328.xlsx) | 五行數值表 |
| [docs/algorithm_api.md](docs/algorithm_api.md) | 已有演算法介面文件 |

## 開始閱讀

```bash
git clone https://github.com/niubideren111/I-Ching-Divination-System.git
cd I-Ching-Divination-System
```

## 常見問題

### 新增展示頁會覆蓋原排盤功能嗎？

不會。產品展示頁位於 docs/index.html，根目錄的排盤 index.html 保留。

### 截圖中的所有排盤演算法都已公開嗎？

目前公開入口以八字排盤頁面和配套 JavaScript 為主；其他截圖用於介紹產品介面範圍。

## 後續資料完善方向

為每種已公開演算法補充輸入、輸出和測試樣例；標明曆法、時區和換日規則。不要用文化產品頁面承諾預測效果。後續更新還應加入版本化相依清單、經過驗證的建置或匯入步驟、簡明架構／產品流程圖，以及能對應真實檔案變更的版本記錄。大型授權資源可放入 GitHub Releases 並提供校驗值，不能提交密鑰、生產位址或使用者資料。

## 相關專案

- [Chess-and-Card-Game-Product-Design-Copy](https://github.com/niubideren111/Chess-and-Card-Game-Product-Design-Copy)

## 資料範圍與授權

公開儲存庫包含八字排盤 index.html、JavaScript 檔案、設計資料和多類排盤截圖。截圖展示範圍不等於所有演算法模組均已公開。公開內容以實際檔案、相依套件與授權為準，不承諾搜尋排名、直接上線或固定效能結果。

- Telegram: [@fox_lovemyself](https://t.me/fox_lovemyself)
- GitHub: [I-Ching-Divination-System](https://github.com/niubideren111/I-Ching-Divination-System)
