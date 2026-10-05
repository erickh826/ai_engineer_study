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
