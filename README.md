<div align="center">

# Shoufa Zhang (张守法)

### **AI Systems Architect & Autonomous Agent Researcher**
*Building high-throughput LLM inference engines, production-grade multi-agent kernels, and verifiable agentic benchmarks.*

[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--5314--6968-A6CE39?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/0009-0000-5314-6968)
[![Zenodo DOI](https://img.shields.io/badge/CERN%20Zenodo-10.5281%2Fzenodo.23839673-00549F?style=for-the-badge&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.23839673)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-171%2B%20Downloads-FFD21E?style=for-the-badge)](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit)
[![vLLM Contributor](https://img.shields.io/badge/vLLM%20(%E2%AD%9096k)-4%20DeepSeek--V4%20%26%20Multimodal%20PRs-76B900?style=for-the-badge)](https://github.com/vllm-project/vllm/pulls?q=author%3Apeterzhang987723)
[![AgentScope Contributor](https://img.shields.io/badge/AgentScope%20(%E2%AD%9035.5k)-Multi--Tenant%20RAG%20%26%20Memory%20PRs-FF6A00?style=for-the-badge)](https://github.com/agentscope-ai/agentscope/pulls?q=author%3Apeterzhang987723)

</div>

---

## ⚡ Executive Highlights (Why My Work Stands Out)

> - **🏎️ 3.2× Speculative Decoding Speedup for DeepSeek-V4 on 8× AMD MI308X (`vLLM` ⭐ 96k+)**: Diagnosed and fixed silent Eagle/MTP draft-weight loading failures for **DSpark DeepSeek-V4/V4.1** across AMD ROCm, NVIDIA CUDA, and Intel XPU ([`vllm#65647`](https://github.com/vllm-project/vllm/pull/65647), [`#66282`](https://github.com/vllm-project/vllm/pull/66282), [`#66283`](https://github.com/vllm-project/vllm/pull/66283)), restoring speculative acceptance length from **`1.00` (0% accepted) to `2.88–3.20`** with **99% GSM8K accuracy** (*hardware-verified by the AMD ROCm team: "LGTM from the ROCm side!"*).
> - **🛡️ Eliminated Cross-Tenant RAG Data Destruction in Alibaba's `AgentScope` (⭐ 35.5k+)**: Discovered and fixed a critical multi-tenant data corruption bug where scoped `KnowledgeBase` instances sharing a collection silently overwrite another tenant's chunks when `document_id` overlaps ([`agentscope#3852`](https://github.com/agentscope-ai/agentscope/pull/3852), `Fixes #3475`), engineering a collision-free identity scheme across **Qdrant, MilvusLite, Elasticsearch, and MongoDB**, alongside fixing embedded **ReMe** long-term memory startup crashes ([`agentscope#3850`](https://github.com/agentscope-ai/agentscope/pull/3850), `Fixes #3811`).
> - **🧠 Hardened DeepSeek's Proactive Autonomous SuperAgent Kernel (`dsh-superagent-prototype`)**: Fixed phantom `delivered: true` state corruption on refused waiting ticket inputs, excluded human-stopped tickets from thread follow-up admission, and enabled `@agent` mention routing in issue titles ([`commit 6a243fe`](https://github.com/peterzhang987723/dsh-superagent-prototype/commit/6a243fe), **512/512 Vitest unit tests passing** across all 24 suites).
> - **📄 Sole-Author CCF-A Journal Research Driving Upstream Benchmark Fixes**: Sole author of *"When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study"* (**`With Editor` at *Artificial Intelligence (AIJ, CCF-A)***; **`Under Review` at *IEEE TPAMI* & *IEEE TSE***). My diagnostic report ([`ethz-spylab/agentdojo#244`](https://github.com/ethz-spylab/agentdojo/issues/244)) directly drove ETH Zurich's upstream ground-truth fix across all 7 benchmark versions ([`agentdojo#247`](https://github.com/ethz-spylab/agentdojo/pull/247)).
> - **🌍 16 Active Upstream PRs Across 500k+ ⭐ AI Infrastructure**: Spanning **vLLM** (⭐ 96k), **RAGFlow** (⭐ 75k), **AgentScope** (⭐ 35.5k), **Hermes-Agent** (⭐ 26.5w), **Volcengine OpenViking** (⭐ 4.1w), **Qwen-Agent** (⭐ 17.3k), **SWE-bench** (⭐ 6.1k), and **OpenHands SDK**.

---

## 🏆 1. DeepSeek (DSK) & AgentScope Flagship Contributions

### 🐳 DeepSeek Ecosystem: From Heterogeneous Inference Kernels (`vLLM`) to Autonomous SuperAgent Brain

| Layer | Repository & PR / Commit | Technical Breakthrough & Verification | Status |
| :--- | :--- | :--- | :---: |
| **Inference / Spec-Dec** | **`vllm-project/vllm`** (⭐ 96k)<br>**[`PR #65647`](https://github.com/vllm-project/vllm/pull/65647)** (`Fixes #65618`) | **Register `packed_modules_mapping` & layer bounds for DSpark DeepSeek-V4/V4.1 across AMD ROCm, NVIDIA CUDA, and Intel XPU**<br>• Fixed silent weight-loading fallback that crippled Eagle speculative decoding.<br>• Restored acceptance length from **`1.00` → `2.88–3.20`** (**99% GSM8K accuracy**), verified on **8× AMD Instinct MI308X (`gfx942`, TP8+EP8)**. | 🟢 **All 4 Maintainer Reviews Resolved; Pending Merge** |
| **Inference / KV Cache** | **`vllm-project/vllm`** (⭐ 96k)<br>**[`PR #66283`](https://github.com/vllm-project/vllm/pull/66283)** | **Use KV-only RoPE insert for DeepSeek-V4/V4.1 DSpark context KV cache**<br>• Eliminated redundant query/key buffer materialization on the speculative decoding context path. | 🟢 **Open (11 Core Reviewers Routed)** |
| **Inference / MTP Quant** | **`vllm-project/vllm`** (⭐ 96k)<br>**[`PR #66282`](https://github.com/vllm-project/vllm/pull/66282)** | **Align DeepSeek-V4 Multi-Token Prediction (MTP) quantization & `packed_modules_mapping` across NVIDIA/XPU**<br>• Prevented quantized weight loader crashes on fused `qkv_proj` / `gate_up_proj` MTP layers. | 🟢 **Open (Active Review)** |
| **Autonomous SuperAgent** | **`deepseek-ai/dsh-superagent-prototype`**<br>**[`Commit 6a243fe`](https://github.com/peterzhang987723/dsh-superagent-prototype/commit/6a243fe)** ([Compare PR Diff](https://github.com/deepseek-ai/dsh-superagent-prototype/compare/main...peterzhang987723:dsh-superagent-prototype:fix/refuse-inputs-and-title-mentions)) | **Proactive Ticket Lifecycle, Thread Admission Policy & Trigger Hardening**<br>• `src/core/tickets.ts`: Purged refused waiting inputs in `Tickets.refuse()` so ended tickets never record phantom `delivered: true` inputs.<br>• `src/policy.ts`: Excluded human-stopped tickets (`ended.by === 'human'`) from `participating()` so stopped threads cannot re-admit unaddressed guest traffic.<br>• `src/sources/github-trigger.ts`: Checked `${issue.title}\n${body}` in `issueTrigger()` to detect title-only `@agent` mentions (**512/512 Vitest tests passing**). | 🟢 **Verified & Publicly Maintained** |

### 🌐 AgentScope Ecosystem (⭐ 35.5k+ Alibaba / ModelScope Flagship Multi-Agent Framework)

| Subsystem | Upstream PR | Architectural Problem Solved & Engineering Depth | Status |
| :--- | :--- | :--- | :---: |
| **Multi-Tenant RAG Isolation** | **`agentscope-ai/agentscope`**<br>**[`PR #3852`](https://github.com/agentscope-ai/agentscope/pull/3852)** (`Fixes #3475`) | **Isolate Scoped `KnowledgeBase` Record IDs Across Shared Collections**<br>• **Root Cause**: Built-in vector stores derived deterministic IDs solely from `(document_id, chunk_index)`, causing Tenant B's `upsert` to silently overwrite and destroy Tenant A's chunks when sharing a collection.<br>• **Solution**: Engineered `_record_identity_key()` with NUL-delimited canonical JSON scope hashing while keeping unscoped IDs 100% unchanged across **Qdrant, MilvusLite, Elasticsearch, and MongoDB**. | 🟢 **Open (Under Review)** |
| **Long-Term Memory (`ReMe`)** | **`agentscope-ai/agentscope`**<br>**[`PR #3850`](https://github.com/agentscope-ai/agentscope/pull/3850)** (`Fixes #3811`) | **Drop Removed `dream_topics_step` From Embedded ReMe Config**<br>• Fixed immediate startup crash (`Unregistered backend 'dream_topics_step'`) with `reme-ai >= 0.4.1.12` and added full lifecycle smoke test coverage. | 🟢 **Open (Under Review)** |

---

## 🔬 2. First-Author / Sole-Author Research & Benchmark Audits

- 📄 **When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study**
  - **Journal Submissions (CCF-A / Top-1% Flagship)**:
    - ***Artificial Intelligence* (`AIJ`, CCF-A, Elsevier)** — Manuscript `ARTINT-D-26-01965` (🟢 **`With Editor`**)
    - ***IEEE Transactions on Pattern Analysis and Machine Intelligence* (`IEEE TPAMI`, IF 20.8)** — Manuscript `TPAMI-2026-11-4662` (🟢 **`Under Review`**)
    - ***IEEE Transactions on Software Engineering* (`IEEE TSE`, CCF-A)** — Manuscript `TSE-2026-11-1219` (🟢 **`Under Review`**)
  - **Real-World Impact on ETH Zurich's Official Benchmark**:
    - Diagnosed a source-bound reference-evaluator blind spot in `ethz-spylab/agentdojo` (`UserTask4` requests a `2024-04-25` calendar event, the author reference creates it in `2023-04-25`, and the native evaluator passes it by discarding the year).
    - Filed upstream issue **[`ethz-spylab/agentdojo#244`](https://github.com/ethz-spylab/agentdojo/issues/244)**, directly triggering the upstream fix across all 7 suite versions (**[`ethz-spylab/agentdojo#247`](https://github.com/ethz-spylab/agentdojo/pull/247)**).
  - **Open Science Reproducibility Suite (825 Native Tool Calls / 3,840 Verified Assertions)**:
    - **CERN Zenodo (OpenAIRE Indexed)**: [`10.5281/zenodo.23839673`](https://doi.org/10.5281/zenodo.23839673)
    - **Hugging Face Dataset**: [`zhangshoufa/AgentDojo-Reference-Solution-Audit`](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit) (**171+ downloads**)
    - **ModelScope (魔搭社区)**: [`shoufanzhang/AgentDojo-Reference-Solution-Audit`](https://modelscope.cn/datasets/shoufanzhang/AgentDojo-Reference-Solution-Audit)

---

## 🚀 3. Broader Open-Source Infrastructure Contributions (16 Active PRs)

- **vLLM Multimodal (`vllm-project/vllm` ⭐ 96k+)**: **[`#66279`](https://github.com/vllm-project/vllm/pull/66279)** — *Prefill `DiffusionGemma` image tokens bidirectionally across attention backends*
- **RAGFlow (`infiniflow/ragflow` ⭐ 75k+)**: **[`#21997`](https://github.com/infiniflow/ragflow/pull/21997)** — *Decouple macOS `pdfium-static` dependency verification from Linux-only bundled `libc++.a`* (`Fixes #21975`, CodeRabbit 5/5 passed)
- **SWE-bench (`swe-bench/SWE-bench` ⭐ 6.1k+)**: **[`#712`](https://github.com/SWE-bench/SWE-bench/pull/712)** — *Prevent printed `PASSED` stdout lines from overwriting `pytest` `FAILED` status in harness log parsers* (`Fixes #708`)
- **OpenHands (`OpenHands/software-agent-sdk`)**: **[`#6463`](https://github.com/OpenHands/software-agent-sdk/pull/6463)** — *Surface corrupt `hooks.json` diagnostics with structured traceback logging and strict mode in `agent-server`* (`Fixes #6376`)
- **Qwen-Agent (`QwenLM/Qwen-Agent` ⭐ 17.3k+)**: **[`#1031`](https://github.com/QwenLM/Qwen-Agent/pull/1031)** — *Assign unique `tool_call` IDs for parallel tool calls in OpenAI-compatible format* (`Fixes #1029`)
- **NousResearch Hermes-Agent (`NousResearch/hermes-agent` ⭐ 26.5w)**:
  - **[`#148791`](https://github.com/NousResearch/hermes-agent/pull/148791)** — *Expose `terminal.ssh_sync_files` & `TERMINAL_SSH_SYNC_FILES` to opt out of remote skill/credential uploads* (`Fixes #148726`)
  - **[`#148809`](https://github.com/NousResearch/hermes-agent/pull/148809)** — *Support per-request `skip_background_review` and `skip_title` opt-outs in API server* (`Fixes #148702`)
  - **[`#148811`](https://github.com/NousResearch/hermes-agent/pull/148811)** — *Preserve non-corrupt telemetry rows on partial JSONL sidecar corruption*
- **Volcengine OpenViking (`volcengine/OpenViking` ⭐ 4.1w)**:
  - **[`#6997`](https://github.com/volcengine/OpenViking/pull/6997)** — *Reject unadvertised tool calls in memory extraction loop and forward `prefetch_search_topn` limit* (`Fixes #6922, #6923`)
  - **[`#7000`](https://github.com/volcengine/OpenViking/pull/7000)** — *Preserve frontmatter metadata and space-delimited `allowed-tools` during session skill evolution*

---

## 🛠️ 4. Original Systems & Open-Source Engines

- **[`SeekMorph`](https://github.com/peterzhang987723/SeekMorph)** — *Hybrid AI Search, Recommendation & Proactive SuperAgent Memory/Ticket Governance Engine*
  - Query intent routing (`exact_lookup` / `semantic_qa` / `exploratory_rec`), pre-retrieval RBAC/ACL tenant filtering, thread-safe incremental inverted index, multi-objective personalized reranking, and `ProactiveTicketRuntime` state machine.
- **[`DocMorph`](https://github.com/peterzhang987723/DocMorph)** — *Structure-Aware Multi-Format Document Parser & Table-Header-Preserving Chunker*
  - DOM/AST parsing across `.md`, `.html`, `.csv`, `.tsv`, `.json`, and `.txt` with cross-chunk table-header preservation, hierarchical breadcrumb injection, and Reciprocal Rank Fusion (RRF) hybrid retrieval.
