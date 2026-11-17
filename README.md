# Hi there, I'm uphome 👋

专注于 **Agent、LLM 推理引擎与模型后训练**。

主要使用 `Python`、`CPP`、`CUDA`  ，喜欢在实践中理解系统设计与底层原理。

---

## 🚀 Featured Projects

### [MyCoder](https://github.com/uphome/MyCoder) — Agent Framework from Scratch

**一个注重架构设计与工程实践的 Python 本地编码 Agent 框架。**

一次关于 Agent 框架如何设计、组织与演进的实践。

- **日志是唯一事实源**：模型看到的每一条消息都能从 `.sessions/*.jsonl` 重建，支持崩溃/OOM 后恢复执行。
- **六层架构**：values → capability → state → runtime → app → web，通过分层设计明确模块职责与边界。
- **完整工具体系**：12 个真实工具，支持文件操作、代码执行等能力。
- **零构建 Web UI**：单个 HTML 文件，CLI 与 Web 共享同一份日志投影。
- 核心设计取舍与实现细节记录在 [架构文档](https://github.com/uphome/MyCoder/blob/main/docs/architecture.md)。

`Python` `Agent Framework` `Tool Use` `Test-Driven Design`

---

### [Qwen3-engine-from-scratch](https://github.com/uphome/Qwen3-engine-from-scratch) — LLM Inference Engine from Scratch

**使用纯 PyTorch 从零实现 Qwen3 推理引擎，探索 LLM 推理系统的底层实现。**

从模型结构到推理调度，逐步理解 LLM Inference Engine 的核心技术，并尝试使用 Triton 替换 PyTorch 实现。

- **核心算子**：手写 RMSNorm、RoPE、GQA、SwiGLU 等模块，完整覆盖 Prefill / Decode 路径。
- **推理调度**：实现 Continuous Batching、Paged KV Cache 与 CUDA Graph 图池。
- **服务接口**：提供 OpenAI 兼容 HTTP API，支持 Chat / Completion、函数调用与思考链开关。
- **性能分析**：配套 Benchmark 体系，覆盖吞吐量、延迟分布、显存占用与算子级耗时分析。

`PyTorch` `Qwen3` `Inference Engine` `CUDA Graph` `Triton`

---

### [HowToMove](https://github.com/uphome/HowToMove) — Agentic RL with GRPO

**使用 GRPO 训练 Qwen3-0.6B，让模型通过工具调用完成网格迷宫中的长程寻路任务。**

探索 LLM 后训练与 Agent 能力的结合，研究如何通过强化学习让模型学会规划、决策与使用工具。

- **训推同源**：单进程、共享模型对象，保证 Rollout 与训练 Log Probability 一致，支持 4GB 显存设备。
- **自研环境**：基于 MiniGrid 思路构建迷宫生成器，包含 4200 张地图数据。
- **手写 GRPO**：不依赖 TRL / verl，实现完整训练循环，支持 LoRA 与 Full Fine-tuning。
- **训练目标**：随机地图成功率 ≥ 80%，工具调用格式合法率 ≥ 99%。

`Reinforcement Learning` `GRPO` `Qwen3` `Agentic RL` `Tool Calling`

---

> "Build it from scratch, understand it from the inside."
