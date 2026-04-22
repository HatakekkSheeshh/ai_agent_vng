# Subtasks & Time Estimates

> Dựa trên `entire_task.md`. Đơn vị: 1 day = 8 working hours.
> Tổng estimate: **~24 days** (~5 tuần part-time hoặc 5 tuần full-time có buffer).

---

## Phase 1 — Nền tảng Agent & Tool Use (~4 days)

### Task 1.1 — Nghiên cứu khái niệm AI Agent — **0.5 day (4h)**
- [ ] 1h — Đọc Anthropic "Building effective agents" + OpenAI agent guide
- [ ] 1h — So sánh Agent vs RAG vs Chatbot vs Workflow (bảng)
- [ ] 1h — Note 4 thành phần: LLM / Memory / Tools / Planning
- [ ] 1h — Khi nào nên / không nên dùng agent

### Task 1.2 — Tool Use / Function Calling — **0.5 day (4h)**
- [ ] 1.5h — Đọc Anthropic tool use docs + OpenAI function calling
- [ ] 1h — Hiểu JSON schema, tool description best practices
- [ ] 1h — Lab: test cách LLM chọn tool (3–5 prompt khác nhau)
- [ ] 0.5h — Note về token cost / cache của tool definitions

### Task 1.3 — Agent đầu tiên, single tool — **1 day (8h)**
- [ ] 1h — Setup project (venv, API key, repo structure)
- [ ] 2h — Implement 1 tool (calculator hoặc weather)
- [ ] 3h — Vòng lặp call → tool_use → tool_result → final answer
- [ ] 1h — Handle edge case: no tool needed, tool error
- [ ] 1h — Viết README + demo script

### Task 1.4 — ReAct Agent multi-tool — **2 days (16h)**
- [ ] 2h — Đọc ReAct paper (bản tóm tắt) + deeplearning.ai LangGraph from scratch
- [ ] 2h — Design 3–4 tools (web search, calculator, file read, …)
- [ ] 6h — Implement Reason → Act → Observe loop (không framework)
- [ ] 2h — Max iteration, stop condition, trace log
- [ ] 2h — Test 5–10 prompt đa dạng
- [ ] 2h — Viết note: failure modes quan sát được

---

## Phase 2 — Frameworks & RAG Agent (~6.5 days)

### Task 2.1 — So sánh orchestration frameworks — **1 day (8h)**
- [ ] 3h — LangGraph: node, edge, state, checkpoint
- [ ] 2h — Anthropic Agent SDK: features, pricing, lock-in
- [ ] 1h — CrewAI + 1 framework khác (AutoGen / LlamaIndex Agents)
- [ ] 2h — **Output**: bảng so sánh + đề xuất framework cho team

### Task 2.2 — Rebuild ReAct bằng framework — **1 day (8h)**
- [ ] 4h — Port Task 1.4 sang LangGraph
- [ ] 2h — Add streaming + checkpointing
- [ ] 2h — **Output**: doc so sánh (LOC, debug, flexibility, learning curve)

### Task 2.3 — Agentic RAG — **3 days (24h)**
- [ ] 2h — Chọn dataset + baseline RAG cũ làm mốc so sánh
- [ ] 6h — Agent quyết định: search / rewrite / multi-hop / stop
- [ ] 4h — Query rewriting node
- [ ] 4h — Self-reflection khi answer không đủ thông tin
- [ ] 4h — Eval harness: accuracy / latency / cost
- [ ] 4h — **Output**: code + evaluation report vs RAG truyền thống

### Task 2.4 — Memory cho Agent — **1.5 days (12h)**
- [ ] 3h — Short-term: conversation history + token-window management
- [ ] 4h — Long-term: extract fact → vector DB (Chroma/Qdrant)
- [ ] 3h — Retrieve memory theo relevance khi bắt đầu turn mới
- [ ] 2h — **Output**: demo 5–10 turn nhớ fact cũ

---

## Phase 3 — Advanced Patterns & Evaluation (~6 days)

### Task 3.1 — Planning Agent — **2 days (16h)**
- [ ] 2h — Đọc Plan-and-Execute pattern + LangGraph example
- [ ] 6h — Planner node tạo plan → Executor chạy từng step
- [ ] 4h — Re-plan khi step fail / observation bất ngờ
- [ ] 2h — Chạy cùng test set với ReAct
- [ ] 2h — **Output**: doc trade-off (latency, cost, success rate)

### Task 3.2 — Multi-Agent System — **2 days (16h)**
- [ ] 2h — Đọc supervisor / sequential / hierarchical patterns
- [ ] 6h — Build researcher + writer + reviewer
- [ ] 4h — Handoff, shared state, loop guard
- [ ] 2h — Diagram kiến trúc (mermaid)
- [ ] 2h — **Output**: demo end-to-end + 1 failure case phân tích

### Task 3.3 — Evaluation & Observability — **2 days (16h)**
- [ ] 2h — Setup LangSmith hoặc Langfuse
- [ ] 2h — Instrument tất cả agent đã build (tracing, tags)
- [ ] 3h — Define metrics: task success, tool-call accuracy, cost, latency, hallucination
- [ ] 4h — Tạo 20–30 test cases (golden dataset)
- [ ] 3h — Chạy eval + phân tích regression
- [ ] 2h — **Output**: dashboard screenshot + evaluation report

---

## Phase 4 — Production & Capstone (~7 days)

### Task 4.1 — Production concerns — **2 days (16h)**
- [ ] 3h — Error handling / retry / timeout / circuit breaker
- [ ] 2h — Cost tracking per request + budget alert
- [ ] 3h — Prompt injection: đọc attack patterns + thêm guardrails
- [ ] 2h — Prompt caching (Anthropic) — đo cost saving
- [ ] 3h — Đọc về source leak của Claude Code (system prompt leak, tool leak)
- [ ] 3h — Harness engineering: tool wrapper, permission, sandbox

### Task 4.2 — Capstone Project — **5 days (40h)**
- [ ] 0.5 day — Chọn bài toán thực tế của team + define success metric
- [ ] 0.5 day — Design: tools, memory, agent topology
- [ ] 2 days — Implement v1
- [ ] 1 day — Eval + fix top failures
- [ ] 0.5 day — Guardrails + cost/latency hardening
- [ ] 0.5 day — Demo + writeup

---

## Suggested weekly cadence

| Week | Focus | Tasks |
|------|-------|-------|
| 1 | Fundamentals | 1.1 → 1.4 |
| 2 | Frameworks | 2.1 → 2.2, start 2.3 |
| 3 | RAG + Memory | finish 2.3, 2.4 |
| 4 | Advanced + Eval | 3.1 → 3.3 |
| 5 | Production + Capstone kickoff | 4.1, start 4.2 |
| 6 | Capstone | finish 4.2 |
