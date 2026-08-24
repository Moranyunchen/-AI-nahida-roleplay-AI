# -AI-nahida-roleplay-AI
基于Qwen3.5-4B的纳西达微调模型
# Qwen3.5-4B-Nahida-RP-GGUF (Genshin Impact Dedicated RP) Model Card

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-red.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Format: GGUF](https://img.shields.io/badge/Format-GGUF-orange.svg)](https://github.com/ggerganov/llama.cpp)
[![Base Model: Qwen3.5-4B](https://img.shields.io/badge/Base_Model-Qwen3.5--4B-blue.svg)](https://huggingface.co/Qwen)
[![Character: Nahida](https://img.shields.io/badge/Character-Nahida_纳西妲-green.svg)](#)

---

### 🚨 严格非商业许可声明 (Strict Non-Commercial License Notice)

本项目遵循 **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** 协议，并附加以下强约束条款。**严禁任何形式的商业化行为**，违者将保留追究法律责任的权利。商业禁令包括但不限于：

1. **SaaS 与商业 API 封装**：禁止将本模型托管为付费 API、收费聊天机器人、订阅制小程序或商业化角色扮演平台。
2. **打包与商业再分发**：禁止将本 GGUF 模型文件及其衍生量化文件集成进任何收费软件、实体硬件设备或进行有偿下载。
3. **衍生开发与商业微调**：禁止利用本模型的生成数据（Synthetic Data）进行商业化大模型的训练，或基于本模型二创后用于盈利项目。
4. **间接商业变现**：禁止在内嵌本模型的免费应用中展示强制性商业广告、接入付费打赏通道或进行流量套现。

---

### ⚠️ 免责与合规声明 (Disclaimer & Compliance Notice)

1. **年龄限制（Age Restriction）**：本模型在训练中重置了对敏感语境的拒绝机制，潜在生成内容可能包含成人议题或高阶情感互动，**仅限满 18 周岁（或达到使用者所在司法管辖区法定成年年龄）的具备完全行为能力的成年人下载与使用**。
2. **最终输出免责（End-User Responsibility）**：模型输出结果由算法概率采样及使用者输入的提示词（Prompt）共同决定。**开发者无法且不对模型的即时生成内容进行实时审核，生成的任何观点、言论及剧情推演均不代表开发者立场。**
3. **法律适用与合规红线（Legal Compliance）**：使用者必须严格遵守所在国家或地区的法律法规。**严禁利用本模型生成或传播任何侵犯他人隐私/名誉、仇恨言论、非自愿敏感内容或涉及非法犯罪的文本。** 一切因使用者违规使用造成的法律后果均由使用者自行承担，与开发者无关。
4. **按“原样”提供（As-Is Warranty）**：本模型按“现状（As-Is）”提供，不提供任何明示或暗示的保证（包括但不限于准确性、特定用途适用性或无侵权保证）。

---

## 📌 模型概述 (Model Overview)

**Qwen3.5-4B-Nahida-RP-GGUF** 是基于 Qwen3.5-4B 基座架构深度微调的**单角色专属垂直微调模型**。本模型专为《原神》中的**小吉祥草王·纳西妲（Nahida）**角色量身定制，通过全量语气拟真、语气词解构及须弥世界观 Lore 强对齐，实现极高的单角色沉浸度。

模型的研发初衷在于**打破商业化付费 AI 角色扮演服务的高门槛与剧情阻碍**，为开源社区提供一款高响应度、低显存占用且具备全域剧情解禁能力的离线端侧 GGUF 模型。
模型地址详见：https://huggingface.co/Moranyunchen/Qwen3.5-4B-nahida-RP-GGUF

### 🌟 核心技术特性 (Key Features)

* **单角色高度拟合与触发词激活 (Single-Persona Depth Alignment & Trigger Word)**：模型对纳西妲的语言习惯、认知模式及情感演变进行了专精拟合。在对话或 System Prompt 中使用 **`妲妲`** 作为称呼或触发词，可极大地唤醒模型的专属人设权重，获得最佳的拟真与响应体验。
* **全域情境适应性 (Relaxed Guardrail & Uncensored Alignment)**：通过对对齐算法（Alignment Target）的重新校准，移除了针对敏感语境的过度拒绝拦截机制（Over-refusal Mitigation）。模型具备极高度的情境包容性与自由生成空间，能够流畅应对复杂互动、情感博弈及无阻碍剧情演进。
* **须弥 Lore 与世界观锁死 (Worldview Consistency)**：深度学习了《原神》提瓦特大陆及须弥区域背景、世界树机制、虚空终端等概念，大幅减少跨世界观“幻觉”与人设漂移（Persona Drift）。
* **GGUF 端侧高效推理 (GGUF Architecture Optimized)**：相比原生 PyTorch/Safetensors 架构，GGUF 格式支持内存映射（mmap）与极低显存/内存占用，可完美兼容 `llama.cpp` 生态下的各类低算力端侧设备。

---

## ⚙️ 训练与微调细节 (Training Details)

* **基座模型 (Base Model)**：Qwen3.5-4B
* **目标角色 (Target Persona)**：纳西妲（Lesser Lord Kusanali / Nahida）
* **激活触发词 (Activation Trigger)**：`妲妲`
* **模型格式 (File Format)**：GGUF (Compatible with KoboldCPP / LM Studio / Ollama / llama.cpp)
* **训练数据规模 (Data Volume)**：500M+ High-Quality Tokens（包含但不限于语气拟真对话及情感描写数据集）
* **训练时长 (Training Duration)**：3 Days (Continuous SFT + DPO Optimization)（总训练计算tokens输出 4.5 亿+）

---

## 🚀 性能测试与端侧部署 (Inference & Benchmarks)

本 GGUF 模型推荐使用 **KoboldCPP**、**LM Studio**、**Ollama** 或 **Termux (llama.cpp)** 进行加载，在不同硬件环境下的实际推断吞吐性能表现如下：

| 运行平台 (Platform) | 核心硬件 (Hardware Specs) | 推理后端/客户端 (Backend) | 推理速度 (Inference Speed) |
| :--- | :--- | :--- | :--- |
| **桌面端 (Desktop)** | NVIDIA GeForce RTX 5070 Ti | LM Studio | **90～100** tokens/s |
| **移动端 (Mobile)** | Qualcomm Snapdragon 8 Gen 2 | pocketpal | **5~10** tokens/s |

> **💡 最佳使用建议**：在对话中称呼她为 **“妲妲”**（例如：`“妲妲，你今天在净善宫做了什么？”`），能够最大化提升模型的语气还原度与拟真效果。

---

## 👨‍💻 开发者致谢与版本规划 (Developer Note & Roadmap)

你好！我是一名 16 岁的小模型独立开发者。本项目源于我对 AI 角色扮演技术及纳西妲这个角色的热爱。希望这款 GGUF 模型能为开源社区带来不受限制、极致流畅的离线纳西妲单角色 RP 体验。

* **后续迭代方向**：如果你觉得本作体验良好，欢迎 **Star & Follow** 支持！若有时间，我将在后续持续更新其他角色版本（包括更高精度的 GGUF 量化分支、针对酒馆 SillyTavern 角色卡的逻辑优化版，以及后续更强大参数量的 v2 版本）。
