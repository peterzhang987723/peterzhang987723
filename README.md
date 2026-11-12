# Shoufa Zhang

**AI Systems & Autonomous Agent Researcher**  
LLM Inference Kernels (`vLLM` / DeepSeek-V4) · Multi-Agent & RAG Systems (`AgentScope` / DeepSeek SuperAgent) · Agentic Benchmark Verification

[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--5314--6968-A6CE39?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0009-0000-5314-6968)
[![Zenodo](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.23839673-00549F?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.23839673)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Dataset-AgentDojo%20Audit-FFD21E?style=flat-square)](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit)
[![vLLM PRs](https://img.shields.io/badge/vLLM%20(%E2%AD%9096k)-5%20Kernel%20%26%20Model%20PRs-76B900?style=flat-square)](https://github.com/vllm-project/vllm/pulls?q=author%3Apeterzhang987723)
[![AgentScope PRs](https://img.shields.io/badge/AgentScope%20(%E2%AD%9035.5k)-Upstream%20PRs-FF6A00?style=flat-square)](https://github.com/agentscope-ai/agentscope/pulls?q=author%3Apeterzhang987723)

---

### Selected Highlights

- **DeepSeek-V4 Speculative Decoding, MLA Workspace & MTP Kernels in [`vllm-project/vllm`](https://github.com/vllm-project/vllm) (⭐ 96k)**
  - Open [**`#65647`**](https://github.com/vllm-project/vllm/pull/65647) (`Fixes #65618`): Add packed-module mappings for DSpark DeepSeek-V4/V4.1 draft models across AMD ROCm, NVIDIA CUDA, and Intel XPU. [Independent validation](https://github.com/vllm-project/vllm/pull/65647#issuecomment-6631700911) on **8× AMD Instinct MI308X (`gfx942`, TP8+EP8)** reported mean acceptance length **`1.00` → `2.88`** on the short prompt and **99% GSM8K** on 100 samples. After incorporating [upstream fix #66994](https://github.com/vllm-project/vllm/pull/66994), the NVIDIA H200 Unlimited-OCR-2 job and all three ARM CPU test shards passed on `69fe7f61`. GitHub reports 109 successful checks and one skipped. The PR remains open pending review. [Current CI](https://buildkite.com/vllm/ci/builds/101786)
  - [**`#66431`**](https://github.com/vllm-project/vllm/pull/66431) · [**`#66283`**](https://github.com/vllm-project/vllm/pull/66283) · [**`#66282`**](https://github.com/vllm-project/vllm/pull/66282) · [**`#66279`**](https://github.com/vllm-project/vllm/pull/66279): SWA decode gather workspace reservation for `Dots3Note` MLA, KV-only RoPE context insertion for DSpark MLA, DeepSeek-V4 Multi-Token Prediction (MTP) quantization alignment, and bidirectional image token prefill for `DiffusionGemma`. The November 11, 2026 revision of #66279 passed DCO and documentation checks and is awaiting the upstream CI gate.

- **Gemma 4 Diffusion Quantization in [`sgl-project/sglang`](https://github.com/sgl-project/sglang)**
  - Open [**`#49211`**](https://github.com/sgl-project/sglang/pull/49211): Independent Linux CPU verification at `fddafe37c188` passed all 24 diffusion and renoise tests. [Test log](https://github.com/peterzhang987723/sglang/actions/runs/42994380420/job/130434682995)

- **Multi-Tenant Vector Isolation, Long-Term Memory & SSE Resiliency in [`agentscope-ai/agentscope`](https://github.com/agentscope-ai/agentscope) (⭐ 35.5k)**
  - [**`#3854`**](https://github.com/agentscope-ai/agentscope/pull/3854) (`Fixes #3855`): Propagated message bus subscription failures and eliminated 5-second startup hangs and silent mid-stream truncations in session SSE event streams.
  - [**`#3852`**](https://github.com/agentscope-ai/agentscope/pull/3852) (`Fixes #3475`): Prevented cross-tenant chunk overwrites when scoped `KnowledgeBase` instances share a collection with overlapping `document_id`s; designed collision-free `_record_identity_key` derivation across **Qdrant, MilvusLite, Elasticsearch, and MongoDB**.
  - [**`#3850`**](https://github.com/agentscope-ai/agentscope/pull/3850): Submitted a fix for a **ReMe** startup crash on `reme-ai >= 0.4.1.12`. The PR was closed as a duplicate and the prior claimant's [**`#3851`**](https://github.com/agentscope-ai/agentscope/pull/3851) was merged.

- **Proactive Ticket State-Machine & Policy Hardening in [`deepseek-ai/dsh-superagent-prototype`](https://github.com/peterzhang987723/dsh-superagent-prototype)**
  - [**`6a243fe`**](https://github.com/peterzhang987723/dsh-superagent-prototype/commit/6a243fe) ([diff](https://github.com/deepseek-ai/dsh-superagent-prototype/compare/main...peterzhang987723:dsh-superagent-prototype:fix/refuse-inputs-and-title-mentions)): Fixed phantom `delivered: true` state on refused waiting inputs in `Tickets.refuse()`, excluded human-stopped tickets from thread follow-up admission in `participating()`, and enabled `@agent` mention detection in GitHub issue titles (**512/512 Vitest tests passing**).

- **Benchmark Evaluation Soundness (`ETH Zurich AgentDojo`) & Journal Research**
  - **Paper**: *"When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study"* — **Sole Author**. IEEE TPAMI (`TPAMI-2026-11-4662`) and IEEE TSE (`TSE-2026-11-1219`) submission records, with IEEE Computer Society–formatted revision files prepared.
  - **Upstream**: Reported the year-truncation evaluator blind spot in [`ethz-spylab/agentdojo#244`](https://github.com/ethz-spylab/agentdojo/issues/244). An upstream contributor proposed a related reference-year fix and regression coverage across seven suite versions in [open PR `#247`](https://github.com/ethz-spylab/agentdojo/pull/247).
  - **Artifacts**: [CERN Zenodo (`10.5281/zenodo.23839673`)](https://doi.org/10.5281/zenodo.23839673) (**20** unique downloads) · [Hugging Face Dataset](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit) (**191** downloads) · [ModelScope](https://modelscope.cn/datasets/shoufanzhang/AgentDojo-Reference-Solution-Audit) (**20** downloads). Counts as of November 12, 2026.
  - **ScienceDB**: The [AgentDojo research dataset V1](https://doi.org/10.57760/sciencedb.0189k) was published on November 12, 2026 under CC BY 4.0. DOI: `10.57760/sciencedb.0189k`.

---

### Additional Upstream Contributions

- **[`infiniflow/ragflow`](https://github.com/infiniflow/ragflow)** (⭐ 75k) — Open [**`#21997`**](https://github.com/infiniflow/ragflow/pull/21997) (`Fixes #21975`): Validate PDFium archives by platform, relink when archive contents change, and keep linker caches safe through concurrent builds and interruptions.
- **[`swe-bench/SWE-bench`](https://github.com/SWE-bench/SWE-bench)** (⭐ 6.1k) — [**`#712`**](https://github.com/SWE-bench/SWE-bench/pull/712) (`Fixes #708`) · [**`#719`**](https://github.com/SWE-bench/SWE-bench/pull/719): Prevent printed `PASSED` stdout lines from overwriting `pytest` `FAILED` status, and unwind nested/sibling `describe` indentation stacks in Karma log parsers.
- **[`OpenHands/software-agent-sdk`](https://github.com/OpenHands/software-agent-sdk)** — Draft [**`#6463`**](https://github.com/OpenHands/software-agent-sdk/pull/6463): Surface per-source `hooks.json` load errors in `agent-server` (`#6376`).
- **[`QwenLM/Qwen-Agent`](https://github.com/QwenLM/Qwen-Agent)** (⭐ 17.3k) — Open [**`#1031`**](https://github.com/QwenLM/Qwen-Agent/pull/1031): Assign unique `tool_call` IDs for parallel tool calls in OpenAI format (`Fixes #1029`). A [community review](https://github.com/QwenLM/Qwen-Agent/pull/1031#pullrequestreview-5868955747) reported five passing regression tests and checked five additional input scenarios.
- **[`NousResearch/hermes-agent`](https://github.com/NousResearch/hermes-agent)** (⭐ 26.5w) — Open [**`#148791`**](https://github.com/NousResearch/hermes-agent/pull/148791) (`Fixes #148726`) · [**`#148809`**](https://github.com/NousResearch/hermes-agent/pull/148809) (`Fixes #148702`) · [**`#148811`**](https://github.com/NousResearch/hermes-agent/pull/148811): Documented SSH file-sync opt-out, per-request background review and title opt-outs, and recovery of intact skill-usage telemetry from partially corrupt ledgers in CLI and Web reports.
- **[`volcengine/OpenViking`](https://github.com/volcengine/OpenViking)** (⭐ 4.1w) — [**`#6997`**](https://github.com/volcengine/OpenViking/pull/6997) (`Fixes #6922, #6923`) · [**`#7000`**](https://github.com/volcengine/OpenViking/pull/7000): Reject unadvertised tool calls in memory extraction loop and preserve frontmatter metadata during session skill evolution. Open [**`#7457`**](https://github.com/volcengine/OpenViking/pull/7457) documents how MCP integrations use the Session API and an explicit `peer_id` to attribute session messages to a project.

---

### Open-Source Systems

- **[`SeekMorph`](https://github.com/peterzhang987723/SeekMorph)** — Hybrid AI search, personalized reranking, pre-retrieval RBAC/ACL tenant filtering, and `ProactiveTicketRuntime` governance engine.
- **[`DocMorph`](https://github.com/peterzhang987723/DocMorph)** — Structure-aware multi-format document parser (`.md`, `.html`, `.csv`, `.tsv`, `.json`, `.txt`) with cross-chunk table-header preservation and Reciprocal Rank Fusion (RRF).
