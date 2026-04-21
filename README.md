# 🎓 Course Advisor RAG System

## 大學課程智慧推薦系統

本專案是一個基於 **Retrieval-Augmented Generation（RAG）** 的課程推薦系統，
透過語意理解與檢索技術，協助學生進行更合理的修課規劃與學習路徑設計。

---

## 📌 System Goal

解決傳統選課系統的問題：

- 僅支援關鍵字搜尋，缺乏語意理解
- 無法根據個人能力與目標推薦課程
- 課程資訊分散且難以比較
- 缺乏修課順序與學習路徑建議

---

## 🧠 Core Features

使用者可以輸入：

- 科系背景
- 興趣方向（AI / 資料分析 / 程式設計）
- 能力程度（數學 / 程式基礎）
- 修課目標（畢業 / 考研 / 就業）

系統會輸出：

- 📚 推薦課程清單
- 🧭 修課順序建議
- 🔗 先修課程分析
- 📊 課程難度評估
- 👨‍🏫 教師資訊
- 💡 推薦理由（LLM 生成）

---

## 🏗️ System Architecture

Course Data (PDF / Web / Database)
↓
ETL (Data Cleaning & Normalization)
↓
Chunking (Markdown + Token-based)
↓
Embedding (BGE-M3)
↓
Vector Database (ChromaDB)
↓
Hybrid Retrieval (Dense + Keyword Search)
↓
Reranking (BGE Reranker)
↓
LLM Generation (GPT / Llama)
↓
Final Recommendation Output

---

## 🧩 Tech Stack

### 🔹 Embedding Model
- BGE-M3

### 🔹 Vector Database
- ChromaDB

### 🔹 Retrieval Strategy
- Dense Retrieval (semantic similarity)
- Sparse Retrieval (keyword matching)
- Hybrid Search

### 🔹 Reranking
- BGE Reranker

### 🔹 LLM
- GPT / LLaMA

---

## 📊 Data Processing Pipeline

1. 資料收集（課程大綱 / 教學網站 / 課程資料庫）
2. ETL 清洗（去除雜訊、標準化格式）
3. Chunking
   - Markdown Header Split
   - Token-based Split（500 tokens / overlap 100）
4. Embedding 轉換
5. 向量儲存與檢索

---

## ⚙️ Key Design Decisions

### Why RAG?
避免 LLM hallucination，確保回答基於真實課程資料。

### Why BGE-M3?
- 優秀中文語意理解能力
- 支援 hybrid embedding
- 適合教育領域資料

### Why ChromaDB?
- 輕量化向量資料庫
- 易於本地部署
- 適合快速開發與實驗

---

## 📈 Evaluation Metrics

使用 RAGAS 評估系統品質：

- Faithfulness ≥ 0.90
- Answer Relevancy ≥ 0.85
- Context Precision
- Context Recall

---

## 🎯 System Strengths

- 強語意理解（非 keyword search）
- 可解釋推薦（提供理由與來源）
- 支援個人化推薦
- 降低錯誤生成（hallucination control）

---

## 🚀 Future Work

- 加入使用者學習歷程推薦
- UI Web 系統（React / Streamlit）
- 課程難度自動標註模型
- 即時課程資料更新系統

---

## 🏁 Conclusion

本系統展示 RAG 技術在教育領域的應用，
透過「檢索 + 生成」架構提升課程推薦品質，
使學生能以更直覺方式規劃學習路徑。
