# Current Progress

Updated: 2026-11-05 (Asia/Hong_Kong).

## Status

M01 in progress; T001 hands-on HTTP experiments partly verified by learner reports. No completed learning tasks yet.

- Current phase: [M01 #1](https://github.com/erickh826/ai_engineer_study/issues/1)
- Current task: [T001 #10](https://github.com/erickh826/ai_engineer_study/issues/10)
- Task specification: docs/tasks/T001-http-chat.md
- Completed learning tasks: 0. Completed phases: 0/9.
- Development environment: GitHub Codespaces; learner reports uv-managed Python 3.12.16 venv, FastAPI/Uvicorn installed.
- Learner personally authored a minimal FastAPI POST /chat with Pydantic ChatRequest; reported actual curl results: HTTP 200 valid body, HTTP 422 missing message, HTTP 405 wrong method.
- HTTP 404 curl result **not yet verified**. Application commit/PR, dated session log and evidence capture **not yet verified**.
- Async/concurrency conceptual practice: def thread pool vs async def event loop, blocking sleep, process-local dict vs Redis shared state, ordering/race, atomic update. Further system-design discussions included cache TTL, ACL, tool authorization, queues/idempotency/lease. These discussions **do not count as hands-on completion**.
- Learner specifically requested more practical exercises and a progress check on 2026-11-05.

## Next Session

Prioritize hands-on over new theory. Ask learner to run and paste actual `curl -i http://127.0.0.1:8000/chats` result (expected 404, but not yet verified); then guide a small concurrent-requests timing experiment comparing sync def, async def with time.sleep, and async def with asyncio.sleep, one step/question at a time. Collect reproducible commands, observations and explanation. Ask learner to commit implementation and prepare session log using docs/sessions/TEMPLATE.md; only then close T001 and update task/issue.

## Source Scope

Progress records learner-reported experiments, not independent repo code verification. Roadmap phases are tracked as issues, not GitHub native milestones.
