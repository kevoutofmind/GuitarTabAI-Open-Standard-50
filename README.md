# 🎸 GuitarTab AI Open Standard: The Semantic Fuel for Music LLMs

![Format](https://img.shields.io/badge/Format-JSONL-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=for-the-badge)
![Architecture](https://img.shields.io/badge/Architecture-Decoupled_Pipeline-success?style=for-the-badge)

> **"Talk is cheap, show me the data."**

传统的 AI 音乐大模型训练，充斥着混乱、未对齐且充满噪音的 MIDI 文件。这直接导致了端到端模型在推演和声时，频繁产生违背物理规律的“幻觉”。

**GuitarTab AI Open Standard** 是 GuitarTab AI 内部高维精修私域语料库的开源切片（Mini-Slice）。我们在此开源这批流行金曲的底层数据结构与清洗规范，旨在向开源社区展示下一代 AI 音乐数据的**“极客标准”**。

## 💡 为什么我们需要这套新标准？

我们摒弃了臃肿的音频和原始 MIDI，将音乐降维提纯为对大语言模型（LLM）极其友好的“机器饲料”。本标准的三大核心支柱：

1. **强制降维 (C-Major Normalization)：** 彻底剥离绝对音高，将全宇宙的调性强制移调至 C 大调 / A 小调。让 LLM 专注于纯粹的相对乐理逻辑与级数推演，极限压缩算力成本。
2. **骨干音提取 (Anchor Note Alignment)：** 抛弃细碎的装饰音噪音，毫秒级强绑定“旋律重拍”与“和弦级数”，为大模型的 Attention 机制提供最致命的因果关系对齐。
3. **零幻觉物理脱水 (Zero-Hallucination JSONL)：** 开箱即用，专为 LLM 的微调（LoRA）与上下文学习（Few-Shot）量身定制，完美衔接下游的吉他指板数学求解器。

## 📂 仓库结构 (Repository Structure)

```text
GuitarTab-AI-Open-Standard/
├── data_mini/                  # 开源数据切片
│   ├── sample_pop_c_major.jsonl # C调归一化后的核心结构化数据
│   └── data_schema.md          # 字段定义文档 (什么是 scale_degree 等)
├── scripts/                    # 极简处理工具链
│   ├── dataloader.py           # 极速读取 JSONL 的 Python 脚本
│   └── transpose_tools.py      # 演示归一化逻辑的移调代码切片
├── LICENSE                     # CC BY-NC 4.0 协议
└── README.md
