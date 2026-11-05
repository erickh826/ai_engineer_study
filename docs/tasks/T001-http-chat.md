# T001：最小 HTTP /chat

階段：M01；狀態：未開始。

## 教學起點

先問學習者：『當你在 browser 按 Send，訊息如何到達 Python 後端，答案又如何回來？用自己的話說，不懂可以用中文。』等回答再補一個缺口。

## 實驗順序

1. 確認本機 Python、terminal 和環境，不假設已安裝。
2. 學習者建立最小 FastAPI POST /chat，接收 message，先用 mock model 回傳固定答案。
3. 用 curl 或 API docs 送 request，觀察 method/path/JSON/status/response。
4. 分別送正常、缺 message、錯 method，記錄實際結果及原因。
5. 學習者解釋 client→server→mock model→response；理解後才換成真 LLM，不要求先買 API。

## 完成條件

- [ ] 學習者說明 method、path、body、status、response
- [ ] 核心程式親手修改並能運行
- [ ] 正常與錯誤 request 可重現，有命令及實際輸出
- [ ] 解釋若 model 等 10 秒，client/server 各在等甚麼
- [ ] 附 commit/PR 和日誌；更新 PROGRESS.md

下一任務再引入 streaming/SSE。AI 不預先交付整個平台。

## 實驗 Checklist（持續更新）

- [x] 選定開發環境：GitHub Codespaces（學習者回報）
- [x] 執行 `python --version`：回報 `Python 3.14.2`（尚未附終端截圖或 commit）
- [x] 確認 FastAPI / Uvicorn 安裝狀態：使用者回報尚未安裝
- [x] 建立並啟用 `.venv`：`pip 25.3` 路徑位於 `/workspaces/ai_engineer_study/.venv/lib/python3.14/site-packages/pip`（使用者回報）
- [x] 使用 uv 建立 Python 3.12.16 `.venv`（使用者回報）
- [x] 安裝 FastAPI 0.162.0 / Uvicorn 0.54.0（使用者提供 package list）
- [x] 親手建立最小 `POST /chat`（mock reply）：使用者貼出 handler 及成功 curl 回應
- [x] 正常 request：`POST /chat`，`{"message":"Hello AI"}` → HTTP 200，`{"reply":"You said: Hello AI"}`（使用者提供 curl 輸出）
- [x] 缺少 `message`：已重現 HTTP 422；`loc=["body","message"]`、`type=missing`（使用者提供 curl 輸出；Handler 是否執行待確認）
- [x] 錯誤 method：`GET /chat` → HTTP 405（使用者回報）；routing 原因仍在鞏固
- [ ] 不存在的 path：重現並解釋 404
- [ ] 解釋 model 延遲 10 秒時 client/server 的行為
- [ ] 提交實作 commit/PR、session log 並更新 PROGRESS.md

> 勾選僅代表已觀察或使用者明確回報；能力級別仍需獨立驗證。最後完成條件以 Issue #10 為準。
