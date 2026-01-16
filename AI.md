flowchart LR
  T[老師] --> A1[教材準備<br/>PPT / PDF / Word / 影片 / 題庫 / 參考資料]
  A1 --> P[內容處理管線<br/>切段/去噪/標註/版本控管]
  P --> G[「生成」工具<br/>腳本生成/旁白/字幕/影片合成]
  G --> V[(課程影片庫/LMS)]
  P --> KB[(課程知識庫<br/>向量索引+原文檔)]
  KB --> TA[「助教」工具<br/>RAG問答/引用來源/多輪對話]
  TA --> Q[出題引擎<br/>題型生成/難度/章節對應]
  Q --> EX[(測驗與作答紀錄庫)]
  TA --> LOG[(問答互動紀錄庫)]
  V --> S[學生]
  TA --> S
  Q --> S
  S --> LOG
  S --> EX
  LOG --> D[Dashboard<br/>常見問題/迷思概念/命中率/章節熱區]
  EX --> D
  D --> T
  T --> F2F[必要時/固定節奏<br/>面對面討論與解惑]
  F2F --> A1

  subgraph Governance[治理/資安/品質]
    SEC[權限/隱私/保存政策<br/>匿名化/水印/防提示注入]
    QA[品質控管<br/>正確性抽測/可追溯引用/版本差異]
  end
  Governance --- P
  Governance --- TA
  Governance --- D
