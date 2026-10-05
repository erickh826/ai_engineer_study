# 12 週 Roadmap

週次為相對安排；開始日期及每週時間尚未設定。按能力驗證前進，必要時延長。Production 元件由第一階段小實驗開始，後續深化。

## M01 · Week 1–2 · Backend 與分布式基礎

[階段 Issue #1](https://github.com/erickh826/ai_engineer_study/issues/1)

學習：HTTP request/response、async/concurrency、SSE、斷線取消、兩實例 session、Redis shared state；初步 timeout/retry、限流、熔斷及 logs。

交付與驗證：最小 /chat → SSE → 斷線實驗 → 兩實例 session 實驗；解釋每次故障的原因。

## M02 · Week 3–4 · RAG 檢索

[階段 Issue #2](https://github.com/erickh826/ai_engineer_study/issues/2)

學習：解析 PDF/Markdown、chunk、embedding、向量索引、BM25、RRF、rerank、長文檔與 context。

交付與驗證：同一組問題比較純向量、混合、混合+rerank；保留資料、配置、命中率和延遲。

## M03 · Week 5 · RAG 評測

[階段 Issue #3](https://github.com/erickh826/ai_engineer_study/issues/3)

學習：檢索與生成分層評測、無答案、多跳、LLM judge 校準、bad case 回歸、表格與圖片。

交付與驗證：先建 20 條 golden set 再擴至 200；診斷 retrieval miss vs generation failure；人工抽檢 judge。

## M04 · Week 6 · ML 與 Python 性能

[階段 Issue #4](https://github.com/erickh826/ai_engineer_study/issues/4)

學習：Precision/Recall/F1、PR/ROC、閾值與業務成本、overfit、skew、drift、少量標註、profiling、批處理。

交付與驗證：欺詐分類實驗含資料切分及成本；CSV 慢版→profile→優化，記錄環境、規模、時間、記憶體與結果一致性。

## M05 · Week 7–8 · Agent 與工具

[階段 Issue #5](https://github.com/erickh826/ai_engineer_study/issues/5)

學習：先理解 state/transition/tool/recovery，再用 LangGraph；checkpoint、schema、loop detection、MCP、SQL/CRM 權限。

交付與驗證：研究 Agent 與 mock MCP 工具；注入非法參數、timeout、重複 tool call；多實例檢驗共享防護狀態。

## M06 · Week 9 · 可靠性

[階段 Issue #6](https://github.com/erickh826/ai_engineer_study/issues/6)

學習：timeout、有限重試+backoff/jitter、熔斷、bulkhead、model failover、取消與重連策略。

交付與驗證：注入延遲、429、5xx 和 provider outage；驗證重試上限、資源釋放及降級；解釋取消與持續背景生成的取捨。

## M07 · Week 10 · Scale 與成本

[階段 Issue #7](https://github.com/erickh826/ai_engineer_study/issues/7)

學習：限流、queue/backpressure、精確/語義 cache、token budget、租戶配額、長對話、向量庫併發。

交付與驗證：在明確硬件和負載下測量吞吐、P50/P99、錯誤及成本；分析 bottleneck，不宣稱未驗證的 100k 併發。

## M08 · Week 11 · Observability 與安全

[階段 Issue #8](https://github.com/erickh826/ai_engineer_study/issues/8)

學習：logs/metrics/traces、request ID、ACL、PII、prompt injection、工具 least privilege、審計。

交付與驗證：一次 trace 定位故障；跨租戶 ACL 負向測試；驗證檢索及 cache 權限隔離；安全測試保留限制。

## M09 · Week 12 · 系統設計與模擬面試

[階段 Issue #9](https://github.com/erickh826/ai_engineer_study/issues/9)

學習：requirements→request flow→failure→方案→trade-off；知識庫助手與 Agent 平台兩張圖。

交付與驗證：獨立畫圖及說明三個取捨；5 分鐘項目介紹使用實測數據；面試答案≤300 字；2–3 次 mock 與追問。

## 共同完成門檻

自己解釋→親手實作→正常/故障驗證→追問與取捨→交接記錄。核心 L3，重要系統設計 L4。架構隨實驗演進，不預先複製完整 production 架構。

## 追蹤方式

M01–M09 使用階段 Issues，並非 GitHub 原生 Milestones。T 任務作為小實驗逐步拆分；目前只建立 T001，避免預先堆滿未理解的工作。學習完成率按驗證任務計算；建立文件不算完成課程。
