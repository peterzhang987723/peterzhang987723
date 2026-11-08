# Hi there, I'm Shoufa Zhang 👋

**AI Infrastructure & Autonomous Agent Systems Engineer / Researcher**  
[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--5314--6968-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0000-5314-6968)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.23839673-blue)](https://doi.org/10.5281/zenodo.23839673)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-AgentDojo%20Audit-yellow)](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit)

I focus on **LLM Inference Acceleration (Speculative Decoding, Quantization, Multi-Backend Kernels)**, **Autonomous Software Engineering Agents**, and **Rigorous Evaluation of Agentic Benchmarks**.

---

## 🔬 1. Research & Benchmark Impact

- 📄 **When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study**
  - **Under Review at Top-Tier Journals (CCF-A)**: *IEEE TPAMI* (`TPAMI-2026-11-4662`), *IEEE TSE* (`TSE-2026-11-1219`), and *Artificial Intelligence* (`ARTINT-D-26-01965`).
  - **Upstream Impact on ETH Zurich's AgentDojo**: Reported and diagnosed ground-truth specification violations in [`ethz-spylab/agentdojo#244`](https://github.com/ethz-spylab/agentdojo/issues/244), directly driving the upstream fix across all 7 benchmark suite versions ([`ethz-spylab/agentdojo#247`](https://github.com/ethz-spylab/agentdojo/pull/247)).
  - **Open Artifacts**:
    - **CERN Zenodo (OpenAIRE Indexed)**: [`10.5281/zenodo.23839673`](https://doi.org/10.5281/zenodo.23839673)
    - **Hugging Face Dataset & Audit Suite**: [`zhangshoufa/AgentDojo-Reference-Solution-Audit`](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit) (**147+ downloads**)
    - **ModelScope**: [`shoufanzhang/AgentDojo-Reference-Solution-Audit`](https://modelscope.cn/datasets/shoufanzhang/AgentDojo-Reference-Solution-Audit)

---

## 🚀 2. Selected Upstream Open-Source Contributions

### ⚡ LLM Inference Engines (`vllm-project/vllm` ⭐ 96k+)
- **[`vllm#65647`](https://github.com/vllm-project/vllm/pull/65647)** — *Register `packed_modules_mapping` & layer bounds for DSpark DeepSeek-V4/V4.1 across AMD ROCm, NVIDIA CUDA, and Intel XPU* (`Fixes #65618`)
  - Restored speculative decoding acceptance length from **`1.00` (0% accepted) to `2.88–3.20`** with **99% GSM8K accuracy**, hardware-verified by the AMD ROCm team on **8× Instinct MI308X (`gfx942`, TP8+EP8)** (*"LGTM from the ROCm side!"*).
- **[`vllm#66283`](https://github.com/vllm-project/vllm/pull/66283)** — *Use KV-only RoPE insert for DeepSeek-V4/V4.1 DSpark context KV cache*
- **[`vllm#66282`](https://github.com/vllm-project/vllm/pull/66282)** — *Add `packed_modules_mapping` and MTP quantization alignment to DeepSeek-V4 NVIDIA/XPU Multi-Token Prediction*
- **[`vllm#66279`](https://github.com/vllm-project/vllm/pull/66279)** — *Prefill `DiffusionGemma` image tokens bidirectionally across attention backends*

### 🤖 Autonomous Agent Frameworks, RAG & Benchmarks
- **OpenHands (`OpenHands/software-agent-sdk`)**: **[`#6463`](https://github.com/OpenHands/software-agent-sdk/pull/6463)** — *Surface corrupt `hooks.json` diagnostics with structured traceback logging in `agent-server`* (`Fixes #6376`)
- **SWE-bench (`swe-bench/SWE-bench` ⭐ 6.1k+)**: **[`#712`](https://github.com/SWE-bench/SWE-bench/pull/712)** — *Prevent printed `PASSED` stdout lines from overwriting `pytest` `FAILED` status in harness log parsers* (`Fixes #708`)
- **RAGFlow (`infiniflow/ragflow` ⭐ 75k+)**: **[`#21997`](https://github.com/infiniflow/ragflow/pull/21997)** — *Decouple macOS `pdfium-static` dependency verification from Linux-only bundled `libc++.a`* (`Fixes #21975`)
- **Qwen-Agent (`QwenLM/Qwen-Agent` ⭐ 17.3k+)**: **[`#1031`](https://github.com/QwenLM/Qwen-Agent/pull/1031)** — *Assign unique `tool_call` IDs for parallel tool calls in OpenAI-compatible format* (`Fixes #1029`)
- **NousResearch Hermes-Agent (`NousResearch/hermes-agent` ⭐ 26.5w)**:
  - **[`#148791`](https://github.com/NousResearch/hermes-agent/pull/148791)** — *Expose `terminal.ssh_sync_files` & `TERMINAL_SSH_SYNC_FILES` to opt out of remote skill/credential uploads* (`Fixes #148726`)
  - **[`#148809`](https://github.com/NousResearch/hermes-agent/pull/148809)** — *Support per-request `skip_background_review` and `skip_title` opt-outs in API server* (`Fixes #148702`)
  - **[`#148811`](https://github.com/NousResearch/hermes-agent/pull/148811)** — *Preserve non-corrupt telemetry rows on partial JSONL sidecar corruption*
- **Volcengine OpenViking (`volcengine/OpenViking` ⭐ 4.1w)**:
  - **[`#6997`](https://github.com/volcengine/OpenViking/pull/6997)** — *Reject unadvertised tool calls in memory extraction loop and forward `prefetch_search_topn` limit* (`Fixes #6922, #6923`)
  - **[`#7000`](https://github.com/volcengine/OpenViking/pull/7000)** — *Preserve frontmatter metadata and space-delimited `allowed-tools` during session skill evolution*

---

## 🛠️ 3. Featured Open-Source Projects

- **[`SeekMorph`](https://github.com/peterzhang987723/SeekMorph)** — *Hybrid AI Search, Recommendation & Proactive SuperAgent Memory/Ticket Governance Engine*
  - Query intent routing (`exact_lookup` / `semantic_qa` / `exploratory_rec`), pre-retrieval RBAC/ACL tenant filtering, thread-safe incremental inverted index, multi-objective personalized reranking, and `ProactiveTicketRuntime` state machine.
- **[`DocMorph`](https://github.com/peterzhang987723/DocMorph)** — *Structure-Aware Multi-Format Document Parser & Table-Header-Preserving Chunker*
  - DOM/AST parsing across `.md`, `.html`, `.csv`, `.tsv`, `.json`, and `.txt` with cross-chunk table-header preservation, hierarchical breadcrumb injection, and Reciprocal Rank Fusion (RRF) hybrid retrieval.
- **[`dsh-superagent-prototype`](https://github.com/peterzhang987723/dsh-superagent-prototype)** — *Proactive Ticket State-Machine & GitHub Trigger Enhancements*
  - Fixed phantom `delivered: true` states on refused ticket inputs and added title-level `@agent` mention detection across issue/PR triggers (`184/184` `vitest` suite passing).
