# 內容自動標籤系統 — AI Content Auto-Labeling

結合 **Gemini LLM 語意判斷**、**關鍵字精確比對**與**純規則推導**，對中文文章自動打上場景、議題、產品、產業、職能、階段六大維度標籤，並透過 FastAPI 提供即時分類服務。

## 🔍 專案概述

內容團隊大量產出文章，若沒有標籤就無法讓業務依場景快速找到對應的知識內容。手動標籤速度慢且標準不一。本系統依標籤特性採不同判斷策略：語意理解交給 LLM（場景、議題、職能），精確比對交給關鍵字字典（產品），產業標籤關鍵字優先、無命中才交給 LLM 判斷，階段標籤則完全由其他標籤結果用規則推導，不額外呼叫 LLM 或知識庫，確保標籤 100% 合法且即時可用。

## 🏷️ 六大維度標籤結構

| 維度 | 範例 | 判斷方式 |
|---|---|---|
| 場景標籤 | 數位轉型、製造業自動化 | Gemini LLM 語意 |
| 議題標籤 | 降本增效、系統整合 | Gemini LLM 語意（+關鍵字驗證） |
| 產品標籤 | ERP、WMS | 關鍵字 + 同義詞字典 |
| 產業標籤 | 製造業 | 關鍵字優先，無命中才用 LLM |
| 職能標籤 | IT／資訊部門 | 純 LLM 判斷（無關鍵字可驗證） |
| 階段標籤 | 已進入產品評估階段 | 純規則推導，依場景/議題/產品結果決定，零額外成本 |

同一套分類核心支援三種呼叫方式：即時 **FastAPI** 服務、離線**批次來源 Adapter**（不需啟動服務）、以及 **Google ADK** 獨立 agent 型態（六個維度各自對應一支 agent）。

## 🛠 技術棧

Python · Gemini 2.0/2.5 Flash · Vertex AI · FastAPI · Google ADK · BeautifulSoup · MySQL · SQL Server

## 🌐 作品集頁面

詳細說明請見：**[https://yujuigato.github.io/content-auto-labeling/](https://yujuigato.github.io/content-auto-labeling/)**

---

> 原始碼因含企業內部資料連線設定，不公開於此 repo。
