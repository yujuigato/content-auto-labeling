# 內容自動標籤系統 — AI Content Auto-Labeling

結合 **Gemini LLM 語意判斷**與**關鍵字精確比對**，對中文文章自動打上場景、議題、產品三層標籤，並透過 FastAPI 提供即時分類服務。

## 🔍 專案概述

內容團隊大量產出文章，若沒有標籤就無法讓業務依場景快速找到對應的知識內容。手動標籤速度慢且標準不一。本系統採混合式引擎：LLM 負責語意理解（場景、議題），關鍵字字典負責精確比對（產品），確保標籤 100% 合法且即時可用。

## 🏷️ 三層標籤結構

| 層 | 範例 | 判斷方式 |
|---|---|---|
| 場景標籤 | 數位轉型、製造業自動化 | Gemini LLM 語意 |
| 議題標籤 | 降本增效、系統整合 | Gemini LLM 語意 |
| 產品標籤 | ERP、WMS | 關鍵字 + 同義詞字典 |

## 🛠 技術棧

Python · Gemini 2.0/2.5 Flash · Vertex AI · FastAPI · BeautifulSoup · MySQL · SQL Server

## 🌐 作品集頁面

詳細說明請見：**[https://yujuigato.github.io/content-auto-labeling/](https://yujuigato.github.io/content-auto-labeling/)**

---

> 原始碼因含企業內部資料連線設定，不公開於此 repo。
