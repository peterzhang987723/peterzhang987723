# Shoufa Zhang

**AI Systems & Autonomous Agent Researcher**  
LLM Inference Kernels (`vLLM` / DeepSeek-V4) · Multi-Agent & RAG Systems (`AgentScope` / DeepSeek SuperAgent) · Agentic Benchmark Verification

[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--5314--6968-A6CE39?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0009-0000-5314-6968)
[![Zenodo](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.23839673-00549F?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.23839673)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Dataset-AgentDojo%20Audit%20(171%2B%20dl)-FFD21E?style=flat-square)](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit)
[![vLLM PRs](https://img.shields.io/badge/vLLM%20(%E2%AD%9096k)-4%20Kernel%20%26%20Model%20PRs-76B900?style=flat-square)](https://github.com/vllm-project/vllm/pulls?q=author%3Apeterzhang987723)
[![AgentScope PRs](https://img.shields.io/badge/AgentScope%20(%E2%AD%9035.5k)-2%20Core%20PRs-FF6A00?style=flat-square)](https://github.com/agentscope-ai/agentscope/pulls?q=author%3Apeterzhang987723)

---

### Selected Highlights

- **DeepSeek-V4 Speculative Decoding & MTP Kernels in [`vllm-project/vllm`](https://github.com/vllm-project/vllm) (⭐ 96k)**
  - [**`#65647`**](https://github.com/vllm-project/vllm/pull/65647) (`Fixes #65618`): Registered `packed_modules_mapping` and layer bounds for DSpark DeepSeek-V4/V4.1 Eagle draft models across AMD ROCm, NVIDIA CUDA, and Intel XPU. Restored speculative acceptance length from **`1.00` → `2.88–3.20`** (**99% GSM8K**), verified on **8× AMD Instinct MI308X (`gfx942`, TP8+EP8)**.
  - [**`#66283`**](https://github.com/vllm-project/vllm/pull/66283) · [**`#66282`**](https://github.com/vllm-project/vllm/pull/66282) · [**`#66279`**](https://github.com/vllm-project/vllm/pull/66279): KV-only RoPE context insertion for DSpark MLA, DeepSeek-V4 Multi-Token Prediction (MTP) quantization alignment, and bidirectional image token prefill for `DiffusionGemma`.

- **Multi-Tenant Vector Isolation, Long-Term Memory & SSE Resiliency in [`agentscope-ai/agentscope`](https://github.com/agentscope-ai/agentscope) (⭐ 35.5k)**
  - [**`#3854`**](https://github.com/agentscope-ai/agentscope/pull/3854) (`Fixes #3855`): Propagated message bus subscription failures and eliminated 5-second startup hangs and silent mid-stream truncations in session SSE event streams.
  - [**`#3852`**](https://github.com/agentscope-ai/agentscope/pull/3852) (`Fixes #3475`): Prevented cross-tenant chunk overwrites when scoped `KnowledgeBase` instances share a collection with overlapping `document_id`s; designed collision-free `_record_identity_key` derivation across **Qdrant, MilvusLite, Elasticsearch, and MongoDB**.
  - [**`#3850`**](https://github.com/agentscope-ai/agentscope/pull/3850) (`Fixes #3811`): Fixed embedded **ReMe** long-term memory middleware startup crash on `reme-ai >= 0.4.1.12`.

- **Proactive Ticket State-Machine & Policy Hardening in [`deepseek-ai/dsh-superagent-prototype`](https://github.com/peterzhang987723/dsh-superagent-prototype)**
  - [**`6a243fe`**](https://github.com/peterzhang987723/dsh-superagent-prototype/commit/6a243fe) ([diff](https://github.com/deepseek-ai/dsh-superagent-prototype/compare/main...peterzhang987723:dsh-superagent-prototype:fix/refuse-inputs-and-title-mentions)): Fixed phantom `delivered: true` state on refused waiting inputs in `Tickets.refuse()`, excluded human-stopped tickets from thread follow-up admission in `participating()`, and enabled `@agent` mention detection in GitHub issue titles (**512/512 Vitest tests passing**).

- **Benchmark Evaluation Soundness (`ETH Zurich AgentDojo`) & Journal Research**
  - **Paper**: *"When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study"* — **Sole Author** (**`With Editor` at *Artificial Intelligence (AIJ, CCF-A)*** `ARTINT-D-26-01965`; **`Under Review` at *IEEE TPAMI*** `TPAMI-2026-11-4662` & ***IEEE TSE*** `TSE-2026-11-1219`).
  - **Upstream Fix**: Diagnosed a year-truncation evaluator blind spot in [`ethz-spylab/agentdojo#244`](https://github.com/ethz-spylab/agentdojo/issues/244), directly driving the upstream ground-truth fix across all 7 benchmark versions ([`agentdojo#247`](https://github.com/ethz-spylab/agentdojo/pull/247)).
  - **Artifacts**: [CERN Zenodo (`10.5281/zenodo.23839673`)](https://doi.org/10.5281/zenodo.23839673) · [Hugging Face Dataset (`171+ downloads`)](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit) · [ModelScope](https://modelscope.cn/datasets/shoufanzhang/AgentDojo-Reference-Solution-Audit)

---

### Additional Upstream Contributions

- **[`infiniflow/ragflow`](https://github.com/infiniflow/ragflow)** (⭐ 75k) — [**`#21997`**](https://github.com/infiniflow/ragflow/pull/21997): Decouple macOS `pdfium-static` verification from Linux-only bundled `libc++.a` (`Fixes #21975`).
- **[`swe-bench/SWE-bench`](https://github.com/SWE-bench/SWE-bench)** (⭐ 6.1k) — [**`#712`**](https://github.com/SWE-bench/SWE-bench/pull/712): Prevent printed `PASSED` stdout lines from overwriting `pytest` `FAILED` status in harness log parsers (`Fixes #708`).
- **[`OpenHands/software-agent-sdk`](https://github.com/OpenHands/software-agent-sdk)** — [**`#6463`**](https://github.com/OpenHands/software-agent-sdk/pull/6463): Surface corrupt `hooks.json` diagnostics and strict mode in `agent-server` (`Fixes #6376`).
- **[`QwenLM/Qwen-Agent`](https://github.com/QwenLM/Qwen-Agent)** (⭐ 17.3k) — [**`#1031`**](https://github.com/QwenLM/Qwen-Agent/pull/1031): Assign unique `tool_call` IDs for parallel tool calls in OpenAI format (`Fixes #1029`).
- **[`NousResearch/hermes-agent`](https://github.com/NousResearch/hermes-agent)** (⭐ 26.5w) — [**`#148791`**](https://github.com/NousResearch/hermes-agent/pull/148791) (`Fixes #148726`) · [**`#148809`**](https://github.com/NousResearch/hermes-agent/pull/148809) (`Fixes #148702`) · [**`#148811`**](https://github.com/NousResearch/hermes-agent/pull/148811): Remote SSH sync opt-out, per-request background review/title opt-outs, and fault-tolerant JSONL telemetry parsing.
- **[`volcengine/OpenViking`](https://github.com/volcengine/OpenViking)** (⭐ 4.1w) — [**`#6997`**](https://github.com/volcengine/OpenViking/pull/6997) (`Fixes #6922, #6923`) · [**`#7000`**](https://github.com/volcengine/OpenViking/pull/7000): Reject unadvertised tool calls in memory extraction loop and preserve frontmatter metadata during session skill evolution.

---

### Open-Source Systems

- **[`SeekMorph`](https://github.com/peterzhang987723/SeekMorph)** — Hybrid AI search, personalized reranking, pre-retrieval RBAC/ACL tenant filtering, and `ProactiveTicketRuntime` governance engine.
- **[`DocMorph`](https://github.com/peterzhang987723/DocMorph)** — Structure-aware multi-format document parser (`.md`, `.html`, `.csv`, `.tsv`, `.json`, `.txt`) with cross-chunk table-header preservation and Reciprocal Rank Fusion (RRF).
