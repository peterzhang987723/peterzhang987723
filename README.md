# Hi there, I'm Shoufa Zhang 👋

**AI Infrastructure & Autonomous Agent Systems Engineer / Researcher**  
[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--5314--6968-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0000-5314-6968)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.23839673-blue)](https://doi.org/10.5281/zenodo.23839673)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-AgentDojo%20Audit-yellow)](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit)

I focus on **DeepSeek Architecture & Heterogeneous Acceleration (MLA, MoE, MTP, Speculative Decoding)**, **Enterprise Multi-Agent Orchestration & Multi-Tenant RAG (AgentScope)**, and **Rigorous Formal Evaluation of Agentic Benchmarks**.

---

## 🏆 Highlight: Core Contributions to DeepSeek & AgentScope Ecosystems

### 🐳 1. DeepSeek (DSK) Ecosystem: Full-Stack From Inference Infra to Autonomous Brain

| Tier | Project / Target | Contribution & Real-World Impact | Status |
| :--- | :--- | :--- | :---: |
| **Infra / Inference** | **`vllm-project/vllm`** (⭐ 96k)<br>*(DeepSeek-V4 Heterogeneous Acceleration)* | **[`#65647`](https://github.com/vllm-project/vllm/pull/65647)** — **Register `packed_modules_mapping` & layer bounds for DSpark DeepSeek-V4/V4.1 across AMD ROCm, NVIDIA CUDA, and Intel XPU** (`Fixes #65618`)<br>• Solved kernel mapping failure on non-standard accelerators; restored speculative acceptance length from **`1.00` to `2.88–3.20`** with **99% GSM8K accuracy**.<br>• Hardware-verified by AMD ROCm team on **8× Instinct MI308X (`gfx942`, TP8+EP8)**. | 🟢 **All 4 Review Comments Resolved; Pending Merge** |
| **Infra / MTP** | **`vllm-project/vllm`** (⭐ 96k) | **[`#66282`](https://github.com/vllm-project/vllm/pull/66282)** — **DeepSeek-V4 Multi-Token Prediction (MTP) quantization alignment & packed mapping** across NVIDIA/XPU. | 🟢 **Open (Active Review)** |
| **Infra / Spec-Dec** | **`vllm-project/vllm`** (⭐ 96k) | **[`#66283`](https://github.com/vllm-project/vllm/pull/66283)** — **KV-only RoPE insert for DeepSeek-V4/V4.1 DSpark context KV cache** to eliminate attention memory overhead. | 🟢 **Open (11 Reviewers Routed)** |
| **Agent / Brain** | **`deepseek-ai/dsh-superagent-prototype`**<br>*(DeepSeek Autonomous SuperAgent)* | **[`Core Kernel Hardening @ peterzhang987723`](https://github.com/peterzhang987723/dsh-superagent-prototype/commit/6a243fe)** — **DeepSeek Autonomous SuperAgent Task Graph & Policy Hardening**<br>• Enforced state-machine `refuseInputs` boundary checks across task graph tools.<br>• Fixed missing `@agent` mention routing in title-matched proactive decisions.<br>• Implemented resilient bracket-skipping JSON extraction for chain-of-thought models.<br>• **512/512 unit tests passing across all 24 Vitest suites (100% pass rate)**. | 🟢 **Verified & Publicly Maintained** |

---

### 🌐 2. AgentScope Ecosystem (⭐ 35.5k+ Alibaba/ModelScope Flagship Multi-Agent Platform)

| Component | Target Issue / PR | Architectural Impact & Technical Depth | Status |
| :--- | :--- | :--- | :---: |
| **RAG / Isolation** | **[`#3852`](https://github.com/agentscope-ai/agentscope/pull/3852)**<br>(**`Fixes #3475`**) | **Isolate Scoped `KnowledgeBase` Record IDs Across Shared Collections**<br>• **Critical Vulnerability**: When multiple tenants share a vector collection, identical `document_id` values silently overwrite and destroy other tenants' knowledge chunks via `upsert`.<br>• **Kernel Fix**: Designed collision-free deterministic ID derivation `_record_identity_key` using canonical JSON scoping, preserving 100% backward compatibility.<br>• **Cross-Database Hardening**: Implemented & tested across **Qdrant, MilvusLite, Elasticsearch, and MongoDB**. | 🟢 **Open (Under Review)** |
| **Long-Term Memory** | **[`#3850`](https://github.com/agentscope-ai/agentscope/pull/3850)**<br>(**`Fixes #3811`**) | **Fix ReMe Long-Term Memory Middleware Crash on Modern `reme-ai`**<br>• Removed deprecated `dream_topics_step` from embedded ReMe pipeline configuration, eliminating startup fatal exceptions for `reme-ai >= 0.4.1.12`. | 🟢 **Open (Under Review)** |

---

## 🔬 3. Academic Research & Benchmark Audits

- 📄 **When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study**
  - **Top-Tier Journal Submissions (CCF-A / Flagship)**:
    - *Artificial Intelligence* (`ARTINT-D-26-01965`, CCF-A) — 🟢 **`With Editor`**
    - *IEEE TPAMI* (`TPAMI-2026-11-4662`, IF 20.8) — 🟢 **`Under Review`**
    - *IEEE TSE* (`TSE-2026-11-1219`, Top SE Journal) — 🟢 **`Under Review`**
  - **Upstream Ground-Truth Correction on ETH Zurich's AgentDojo**: Reported and formally diagnosed ground-truth specification violations in [`ethz-spylab/agentdojo#244`](https://github.com/ethz-spylab/agentdojo/issues/244), directly driving the upstream fix across all 7 benchmark suite versions ([`ethz-spylab/agentdojo#247`](https://github.com/ethz-spylab/agentdojo/pull/247)).
  - **Open Science Artifacts**:
    - **CERN Zenodo (OpenAIRE Indexed, Immutable DOI)**: [`10.5281/zenodo.23839673`](https://doi.org/10.5281/zenodo.23839673)
    - **Hugging Face Dataset & Audit Suite**: [`zhangshoufa/AgentDojo-Reference-Solution-Audit`](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit) (**171+ downloads**)
    - **ModelScope (魔搭社区)**: [`shoufanzhang/AgentDojo-Reference-Solution-Audit`](https://modelscope.cn/datasets/shoufanzhang/AgentDojo-Reference-Solution-Audit)

---

## 🚀 4. Other Upstream Open-Source Contributions

- **RAGFlow (`infiniflow/ragflow` ⭐ 75k+)**: **[`#21997`](https://github.com/infiniflow/ragflow/pull/21997)** — *Decouple macOS `pdfium-static` dependency verification from Linux-only bundled `libc++.a`* (`Fixes #21975`)
- **SWE-bench (`swe-bench/SWE-bench` ⭐ 6.1k+)**: **[`#712`](https://github.com/SWE-bench/SWE-bench/pull/712)** — *Prevent printed `PASSED` stdout lines from overwriting `pytest` `FAILED` status in harness log parsers* (`Fixes #708`)
- **OpenHands (`OpenHands/software-agent-sdk`)**: **[`#6463`](https://github.com/OpenHands/software-agent-sdk/pull/6463)** — *Surface corrupt `hooks.json` diagnostics with structured traceback logging in `agent-server`* (`Fixes #6376`)
- **Qwen-Agent (`QwenLM/Qwen-Agent` ⭐ 17.3k+)**: **[`#1031`](https://github.com/QwenLM/Qwen-Agent/pull/1031)** — *Assign unique `tool_call` IDs for parallel tool calls in OpenAI-compatible format* (`Fixes #1029`)
- **NousResearch Hermes-Agent (`NousResearch/hermes-agent` ⭐ 26.5w)**:
  - **[`#148791`](https://github.com/NousResearch/hermes-agent/pull/148791)** — *Expose `terminal.ssh_sync_files` & `TERMINAL_SSH_SYNC_FILES` to opt out of remote skill/credential uploads* (`Fixes #148726`)
  - **[`#148809`](https://github.com/NousResearch/hermes-agent/pull/148809)** — *Support per-request `skip_background_review` and `skip_title` opt-outs in API server* (`Fixes #148702`)
  - **[`#148811`](https://github.com/NousResearch/hermes-agent/pull/148811)** — *Preserve non-corrupt telemetry rows on partial JSONL sidecar corruption*
- **Volcengine OpenViking (`volcengine/OpenViking` ⭐ 4.1w)**:
  - **[`#6997`](https://github.com/volcengine/OpenViking/pull/6997)** — *Reject unadvertised tool calls in memory extraction loop and forward `prefetch_search_topn` limit* (`Fixes #6922, #6923`)
  - **[`#7000`](https://github.com/volcengine/OpenViking/pull/7000)** — *Preserve frontmatter metadata and space-delimited `allowed-tools` during session skill evolution*

---

## 🛠️ 5. Featured Autonomous Systems & Engines

- **[`SeekMorph`](https://github.com/peterzhang987723/SeekMorph)** — *Hybrid AI Search, Recommendation & Proactive SuperAgent Memory/Ticket Governance Engine*
  - Query intent routing (`exact_lookup` / `semantic_qa` / `exploratory_rec`), pre-retrieval RBAC/ACL tenant filtering, thread-safe incremental inverted index, multi-objective personalized reranking, and `ProactiveTicketRuntime` state machine.
- **[`DocMorph`](https://github.com/peterzhang987723/DocMorph)** — *Structure-Aware Multi-Format Document Parser & Table-Header-Preserving Chunker*
  - DOM/AST parsing across `.md`, `.html`, `.csv`, `.tsv`, `.json`, and `.txt` with cross-chunk table-header preservation, hierarchical breadcrumb injection, and Reciprocal Rank Fusion (RRF) hybrid retrieval.
