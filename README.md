### Shoufa Zhang

AI Systems & Agent Infrastructure: LLM inference (`vLLM`), retrieval and memory kernels (`RAGFlow`, `OpenViking`), proactive and personal agent runtimes (`Hermes-Agent`, `dsh-superagent`, `Qwen-Agent`, `OpenHands`), and evaluation benchmarks (`SWE-bench`, `AgentDojo`).

#### Projects (Owner)
- **[SeekMorph](https://github.com/peterzhang987723/SeekMorph)** ([Live Space](https://huggingface.co/spaces/zhangshoufa/DocMorph)): Hybrid AI search, personalized recommendation reranking (intent routing, user interest affinity, Bayesian CTR, recency decay), pre-retrieval RBAC/ACL filtering (`0.0%` cross-tenant leakage), and Personal SuperAgent memory/mandate runtime (`PersonalMemoryStore` & `ProactiveTicketRuntime`).
- **[DocMorph](https://github.com/peterzhang987723/DocMorph)** ([Live Space](https://huggingface.co/spaces/zhangshoufa/DocMorph)): Structure-aware document morphing (`.md`, `.html`, `.csv`, `.json`), `100%` table-header preservation across split chunks, and thread-safe inverted-index hybrid retrieval (`BM25 + Dense Vector RRF`, `NDCG@3 = 1.0000`).

#### Upstream Pull Requests & Patches
- **vllm-project/vllm**: [#65647](https://github.com/vllm-project/vllm/pull/65647) (Register `packed_modules_mapping` for DeepSeek-V4/V4.1 DSpark speculative decoding across AMD ROCm, NVIDIA, and Intel XPU)
- **infiniflow/ragflow**: [#21997](https://github.com/infiniflow/ragflow/pull/21997) (Decouple macOS vs. Linux `pdfium-static` archive validation and track platform stamps)
- **SWE-bench/SWE-bench**: [#712](https://github.com/SWE-bench/SWE-bench/pull/712) (Prevent stdout `PASSED` lines from overwriting pytest `FAILED` status in harness log parsers)
- **QwenLM/Qwen-Agent**: [#1031](https://github.com/QwenLM/Qwen-Agent/pull/1031) (Assign unique `tool_call` IDs for parallel tool calls in OpenAI message conversion)
- **OpenHands/software-agent-sdk**: [#6463](https://github.com/OpenHands/software-agent-sdk/pull/6463) (Surface structured `HooksSourceError` diagnostics for corrupt `hooks.json` files)
- **volcengine/OpenViking**: [#6997](https://github.com/volcengine/OpenViking/pull/6997), [#7000](https://github.com/volcengine/OpenViking/pull/7000) (Reject unadvertised tool calls in memory extraction loop, forward `prefetch_search_topn`, and preserve skill metadata on update)
- **NousResearch/hermes-agent**: [#148791](https://github.com/NousResearch/hermes-agent/pull/148791), [#148809](https://github.com/NousResearch/hermes-agent/pull/148809), [#148811](https://github.com/NousResearch/hermes-agent/pull/148811) (Expose `ssh_sync_files` opt-out, per-request `skip_background_review` / `skip_title`, and partial telemetry recovery)
- **deepseek-ai/dsh-superagent-prototype**: [172e245](https://github.com/peterzhang987723/dsh-superagent-prototype/commit/172e245) (Drop refused waiting inputs in `Tickets.refuse()`, exclude human-stopped tickets from `participating()`, and detect `@agent` mentions in GitHub Issue/PR titles)

#### Research & Benchmark Audits
- *When Reference Solutions Pass but Violate Explicit Goals: An AgentDojo Case Study*: [DOI: 10.5281/zenodo.23839673](https://doi.org/10.5281/zenodo.23839673) | [Hugging Face Dataset](https://huggingface.co/datasets/zhangshoufa/AgentDojo-Reference-Solution-Audit) | [ethz-spylab/agentdojo#244](https://github.com/ethz-spylab/agentdojo/issues/244)
