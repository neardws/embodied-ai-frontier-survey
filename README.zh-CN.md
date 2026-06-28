<div align="center">

# 🤖 Awesome Embodied AI Papers

**围绕 VLN、VLA、WAM、规划、本体扩展和部署评测整理的顶会具身智能研究地图。**

[English](README.md) | 中文

[![Awesome](https://img.shields.io/badge/Awesome-Embodied%20AI-fc60a8?style=for-the-badge)](https://awesome.re)
[![Survey Entries](https://img.shields.io/badge/Survey%20Entries-646-0984e3?style=for-the-badge)](README.zh-CN.md)
[![Last Commit](https://img.shields.io/github/last-commit/neardws/awesome-embodied-ai-papers?style=for-the-badge&color=00b894)](https://github.com/neardws/awesome-embodied-ai-papers/commits)
[![Stars](https://img.shields.io/github/stars/neardws/awesome-embodied-ai-papers?style=for-the-badge&color=fdcb6e&logo=github)](https://github.com/neardws/awesome-embodied-ai-papers/stargazers)
[![Forks](https://img.shields.io/github/forks/neardws/awesome-embodied-ai-papers?style=for-the-badge&color=e17055&logo=github)](https://github.com/neardws/awesome-embodied-ai-papers/network/members)

更新日期：2026-06-28

</div>

## 📋 目录

| | 章节 | 说明 |
|:---:|:---|:---|
| 🏷️ | [标签图例](#标签图例) | 各方向标签的含义 |
| 🧭 | [总体判断](#总体判断) | 领域整体判断和系统路线 |
| 🗺️ | [方向总览表](#方向总览表) | 六条方向及论文条目数 |
| 📚 | [各方向详细表格](#各方向详细表格) | 按方向和子方向展开的论文表 |
| 🔎 | [重点阅读顺序](#重点阅读顺序) | 建议优先阅读的方向 |
| 🧾 | [数据来源说明](#数据来源说明) | 来源追溯和参考元数据 |

> [!NOTE]
> 条目范围限定为已读公开来源中可核验的论文，覆盖 CCF-A 会议以及 ICRA/IROS 等机器人传统强会。

> [!TIP]
> 如果有遗漏论文或资源，可以通过 Issue 或 Pull Request 补充。

## 标签图例

| 标签 | 含义 |
| --- | --- |
| `VLN` | 大范围导航 |
| `VLA` | 视觉-语言-动作操作策略 |
| `WAM` | 世界动作模型 |
| `Planning` | 任务分解、记忆、失败恢复、约束规划 |
| `Embodiment` | 人形、双臂、灵巧手、触觉 |
| `Deployment` | 轻量化、评测、数据、sim2real、安全 |

## 总体判断

当前具身智能的热点可以分成六条线：VLN 大范围导航、VLA 操作策略、WAM 世界动作模型、Agentic Planning 推理规划、本体扩展/灵巧操作、轻量化/评测/数据。

最值得持续跟踪的系统路线是：

```text
任务理解与细粒度规划 agent
        -> WAM / world model 做想象、验证和失败预测
        -> 小 VLA、diffusion policy、技能库或传统控制执行
        -> 机器人本地安全闭环
```

原因很直接：单体 VLA 仍然重要，但真实机器人需要可解释规划、可执行约束、低延迟控制、失败恢复和端侧自治。

## 方向总览表

<table>
<thead>
<tr>
<th nowrap>标签</th>
<th nowrap>方向</th>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>结果判断</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap><code>VLN</code></td>
<td nowrap>VLN / 大范围导航</td>
<td nowrap>连续环境 VLN、地图记忆、物理可执行导航、城市/开放环境导航、低成本/端侧导航</td>
<td nowrap>87</td>
<td nowrap>VLN 关注语言目标、空间地图、记忆、探索和导航决策，核心问题是把自然语言任务变成可执行的大范围移动计划。当前调研条目显示，研究正在从离散导航图转向连续环境、物理可执行导航、开放城市环境和低成本端侧导航。</td>
</tr>
<tr>
<td nowrap><code>VLA</code></td>
<td nowrap>VLA / 操作策略</td>
<td nowrap>generalist VLA、action representation、diffusion/flow policy、3D grounding、online/RL fine-tuning、安全鲁棒性</td>
<td nowrap>213</td>
<td nowrap>VLA 是机械臂和移动操作的主战场，但它不只是“大模型接动作头”。调研论文集中在动作表示、diffusion/flow policy、3D grounding、在线/RL 微调和安全鲁棒性上。</td>
</tr>
<tr>
<td nowrap><code>WAM</code></td>
<td nowrap>WAM / 世界模型</td>
<td nowrap>cascaded WAM、joint WAM、video/latent world model、world model for VLA、world model evaluation</td>
<td nowrap>64</td>
<td nowrap>WAM 将未来世界状态预测和动作生成合在一起，适合放在 agent 规划和低层控制之间。它的价值不是替代所有控制器，而是提供可想象、可验证、可恢复的中间层。</td>
</tr>
<tr>
<td nowrap><code>Planning</code></td>
<td nowrap>Agentic Planning / 推理规划</td>
<td nowrap>任务分解、memory、failure monitor、constraint / affordance planning、self-improving planning</td>
<td nowrap>98</td>
<td nowrap>这一方向强调任务分解、记忆、失败监控、约束/affordance planning 和自改进规划。它最贴近“agent 规划，小模型或传统方法执行”的系统路线。</td>
</tr>
<tr>
<td nowrap><code>Embodiment</code></td>
<td nowrap>本体扩展 / 灵巧操作</td>
<td nowrap>humanoid、bimanual、dexterous hand、tactile/contact-rich、grasp</td>
<td nowrap>89</td>
<td nowrap>本体扩展决定具身智能是否能从单机械臂走向人形、双臂、灵巧手和触觉接触任务。表中论文体现了动作空间、传感方式和控制目标随本体变化而复杂化。</td>
</tr>
<tr>
<td nowrap><code>Deployment</code></td>
<td nowrap>轻量化 / 评测 / 数据</td>
<td nowrap>quantization/cache/tokenization、real-time execution、benchmark/dataset、sim2real、safety evaluation</td>
<td nowrap>95</td>
<td nowrap>这一方向决定能不能真实部署：端侧推理、缓存/量化/action tokenization、实时执行、sim2real、benchmark 和 safety evaluation 都是必需条件。</td>
</tr>
</tbody>
</table>

## 各方向详细表格

### VLN / 大范围导航

VLN 关注语言目标、空间地图、记忆、探索和导航决策，核心问题是把自然语言任务变成可执行的大范围移动计划。当前调研条目显示，研究正在从离散导航图转向连续环境、物理可执行导航、开放城市环境和低成本端侧导航。

子方向：连续环境 VLN、地图记忆、物理可执行导航、城市/开放环境导航、低成本/端侧导航。

共 87 篇。

<table>
<thead>
<tr>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>观察重点</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>连续环境 VLN</td>
<td nowrap>35</td>
<td nowrap>看是否从离散导航图走向连续观察和实时决策。</td>
</tr>
<tr>
<td nowrap>地图记忆</td>
<td nowrap>22</td>
<td nowrap>看地图表示、语义记忆、缓存和检索机制。</td>
</tr>
<tr>
<td nowrap>物理可执行导航</td>
<td nowrap>7</td>
<td nowrap>看真实本体约束、动态环境和安全解码。</td>
</tr>
<tr>
<td nowrap>城市/开放环境导航</td>
<td nowrap>20</td>
<td nowrap>看开放世界、城市、拥挤环境和长期导航。</td>
</tr>
<tr>
<td nowrap>低成本/端侧导航</td>
<td nowrap>3</td>
<td nowrap>看端侧推理、低成本记忆和数据效率。</td>
</tr>
</tbody>
</table>

#### 连续环境 VLN

共 35 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>任务类型</th>
<th nowrap>环境</th>
<th nowrap>地图/记忆</th>
<th nowrap>训练/反馈</th>
<th nowrap>Sim/Real/Benchmark</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2023</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2023/html/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.html">Adaptive Zone-Aware Hierarchical Planner for Vision-Language Navigation</a></td>
<td nowrap>AZHP plans navigation by adapting hierarchy and local zones for language-conditioned visual navigation.</td>
<td nowrap>Vision-language navigation</td>
<td nowrap>continuous indoor navigation</td>
<td nowrap>zone-aware hierarchical memory</td>
<td nowrap>hierarchical planning</td>
<td nowrap>VLN benchmarks</td>
<td nowrap>Use zone-level structure to make long-horizon VLN decisions more reliable.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2023/papers/Gao_Adaptive_Zone-Aware_Hierarchical_Planner_for_Vision-Language_Navigation_CVPR_2023_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/gao24p.html">Fast-Slow Test-Time Adaptation for Online Vision-and-Language Navigation</a></td>
<td nowrap>Fast-Slow TTA adapts VLN agents online using complementary fast and slow adaptation signals.</td>
<td nowrap>Online VLN</td>
<td nowrap>continuous navigation</td>
<td nowrap>episodic adaptation memory</td>
<td nowrap>test-time adaptation</td>
<td nowrap>VLN benchmarks</td>
<td nowrap>Improve online VLN robustness under distribution shift.</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/gao24p/gao24p.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2509.19480">OmniVLA: An Omni-Modal Vision-Language-Action Model for Robot Navigation</a></td>
<td nowrap>OmniVLA 统一语言、目标图像和 2D pose 等目标规格，用 VLA 方式学习机器人导航策略。</td>
<td nowrap>Vision-language-action navigation</td>
<td nowrap>continuous navigation</td>
<td nowrap>multimodal goal context</td>
<td nowrap>navigation VLA training</td>
<td nowrap>Sim + Real</td>
<td nowrap>用多模态目标表达训练可泛化导航 VLA。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.19480">paper</a></td>
<td nowrap><a href="https://omnivla-nav.github.io/">project</a></td>
<td nowrap><a href="https://github.com/NHirose/OmniVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://sites.google.com/view/opennav/home">Open-Nav: Exploring Zero-Shot Vision-and-Language Navigation in Continuous Environment with Open-Source LLMs</a></td>
<td nowrap>Open-Nav 用开源 LLM 做时空 CoT、进度估计和动作决策，面向连续环境零样本 VLN。</td>
<td nowrap>Continuous VLN</td>
<td nowrap>continuous indoor environment</td>
<td nowrap>spatio-temporal CoT</td>
<td nowrap>zero-shot LLM planning</td>
<td nowrap>VLN-CE benchmark</td>
<td nowrap>让开源 LLM 在连续环境中按语言指令导航。</td>
<td nowrap><a href="https://sites.google.com/view/opennav/home">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/opennav/home">project</a></td>
<td nowrap><a href="https://github.com/YanyuanQiao/Open-Nav">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=kkBOIsrCXh">Embodied Navigation Foundation Model</a></td>
<td nowrap>NavFoM 用 800 万跨具身导航样本训练统一导航基础模型，覆盖 VLN、目标搜索、跟踪和自动驾驶。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>多模态历史/轨迹上下文</td>
<td nowrap>大规模监督预训练</td>
<td nowrap>跨具身 benchmark</td>
<td nowrap>跨具身跨任务泛化</td>
<td nowrap><a href="https://openreview.net/forum?id=kkBOIsrCXh">paper</a></td>
<td nowrap><a href="https://pku-epic.github.io/NavFoM-Web/">project</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://pku-epic.github.io/NavFoM-Web/">data</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=GK4rznYwhn">Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-Language Navigation</a></td>
<td nowrap>DualVLN 用慢速视觉语言全局规划器和快速扩散式低层控制器结合，提升连续真实环境 VLN 的平滑执行。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>VLM waypoint planner + diffusion policy</td>
<td nowrap>sim+real robot</td>
<td nowrap>解决端到端 VLN 动作碎片化、高延迟和动态避障差的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=GK4rznYwhn">paper</a></td>
<td nowrap><a href="https://internrobotics.github.io/internvla-n1-dualvln.github.io/">project</a></td>
<td nowrap><a href="https://github.com/InternRobotics/InternNav">code</a></td>
<td nowrap>InternData-N1</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=eqcDckWHik">CompassNav: Steering From Path Imitation to Decision Understanding In Navigation</a></td>
<td nowrap>CompassNav 从轨迹模仿转向动作可行性理解，用 Compass-Data-22k 和 gap-aware 训练提升 VLN 决策。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>RFT + action feasibility supervision</td>
<td nowrap>Compass-Data-22k</td>
<td nowrap>从路径模仿到决策理解</td>
<td nowrap><a href="https://openreview.net/forum?id=eqcDckWHik">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=pFh5ygjN3V">M$^3$E: Continual Vision-and-Language Navigation via Mixture of Macro and Micro Experts</a></td>
<td nowrap>M3E 用宏观场景专家和微观感知专家分离建模，缓解持续 VLN 跨环境适应中的灾难性遗忘。</td>
<td nowrap>持续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>hierarchical MoE continual learning</td>
<td nowrap>-</td>
<td nowrap>跨环境持续学习与抗遗忘</td>
<td nowrap><a href="https://openreview.net/forum?id=pFh5ygjN3V">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=zGtTQTD1zu">OmniNav: A Unified Framework for Prospective Exploration and Visual-Language Navigation</a></td>
<td nowrap>OmniNav 用统一 waypoint policy 同时处理指令目标、物体目标、点目标导航和 frontier 探索。</td>
<td nowrap>统一导航/探索</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>continuous waypoint policy</td>
<td nowrap>real-time 5Hz deployment claimed</td>
<td nowrap>统一多种导航范式并支持低延迟连续空间 waypoint 输出。</td>
<td nowrap><a href="https://openreview.net/forum?id=zGtTQTD1zu">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=0c7nAZjyr5">From Seeing to Experiencing: Scaling Navigation Foundation Models with Reinforcement Learning</a></td>
<td nowrap>S2E 将离线视频预训练导航模型通过强化学习后训练，学习动作后果、避障和城市交互行为。</td>
<td nowrap>连续 VLN</td>
<td nowrap>城市/动态环境</td>
<td nowrap>-</td>
<td nowrap>offline pretraining + RL post-training</td>
<td nowrap>-</td>
<td nowrap>交互式安全导航泛化</td>
<td nowrap><a href="https://openreview.net/forum?id=0c7nAZjyr5">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=apaLoTumdO">CE-Nav: Flow-Guided Reinforcement Refinement for Cross-Embodiment Local Navigation</a></td>
<td nowrap>CE-Nav 先用流模型学习跨具身可行动作分布，再用 RL 针对具体机器人动力学细化。</td>
<td nowrap>跨具身局部导航</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>IL + RL, conditional normalizing flow</td>
<td nowrap>-</td>
<td nowrap>跨形态局部导航泛化</td>
<td nowrap><a href="https://openreview.net/forum?id=apaLoTumdO">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=bMrH2PFMsi">CoNavBench: Collaborative Long-Horizon Vision-Language Navigation Benchmark</a></td>
<td nowrap>CoNavBench 提供 4048 个单体/协作长程 VLN episodes，用于评估交接、拥堵和协作导航。</td>
<td nowrap>协作长程 VLN benchmark</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>VLN policy</td>
<td nowrap>Benchmark</td>
<td nowrap>协作 VLN 评测</td>
<td nowrap><a href="https://openreview.net/forum?id=bMrH2PFMsi">paper</a></td>
<td nowrap><a href="https://navcraft.github.io">project</a></td>
<td nowrap>-</td>
<td nowrap>CoNavBench/NavCraft</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38886">NaVLA$^2$: A Vision-Language-Audio-Action Model for Multimodal Instruction Navigation</a></td>
<td nowrap>NaVLA2 提出 MINav 任务，用语言、图像和声音线索消解导航指令歧义并构建 43.9K episodes。</td>
<td nowrap>多模态指令导航</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>vision-language-audio-action policy</td>
<td nowrap>MINav benchmark</td>
<td nowrap>解决多相似物体场景中单语言指令不足导致的目标 grounding 歧义。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38886">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38888">VPN: Visual Prompt Navigation</a></td>
<td nowrap>VPN 用 2D 顶视图视觉提示替代自然语言指令，并扩展 R2R/R2R-CE 形成 VP 数据集。</td>
<td nowrap>visual prompt navigation</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>top-view map prompt</td>
<td nowrap>VLN policy</td>
<td nowrap>R2R-VP/R2R-CE-VP</td>
<td nowrap>研究用用户绘制/标记的视觉路径提示指导导航。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38888">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38891">SeqWalker: Sequential-Horizon Vision-and-Language Navigation with Hierarchical Planning</a></td>
<td nowrap>SeqWalker 面向长程多任务指令，用高层子指令选择和低层探索验证缓解信息过载。</td>
<td nowrap>长程/序列 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>hierarchical planning</td>
<td nowrap>-</td>
<td nowrap>长指令分解与执行</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38891">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38895">UNeMo: Collaborative Visual-Language Reasoning and Navigation via a Multimodal World Model</a></td>
<td nowrap>UNeMo 用多模态世界模型联合优化视觉状态推理和导航决策，补足只用语言推理的 VLN 方法。</td>
<td nowrap>世界模型 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>multimodal world model collaborative optimization</td>
<td nowrap>-</td>
<td nowrap>解决 LLM 推理模块与导航策略分离、缺少视觉推理的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38895">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38914">DNOI-4DRO: Deep 4D Radar Odometry with Differentiable Neural-Optimization Iterations</a></td>
<td nowrap>DNOI-4DRO 将 4D 雷达运动流网络与可微 Gauss-Newton 优化结合，提高雷达里程计精度。</td>
<td nowrap>4D radar odometry，不是 VLN</td>
<td nowrap>移动机器人/自动驾驶雷达定位</td>
<td nowrap>-</td>
<td nowrap>differentiable neural optimization</td>
<td nowrap>VoD/Snail-Radar</td>
<td nowrap>解决稀疏 4D 雷达点云中的自定位/里程计估计。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38914">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38954">Run, Ruminate, and Regulate: A Dual-process Thinking System for Vision-and-Language Navigation</a></td>
<td nowrap>R3 将快速执行、慢速 LLM 反思和调节模块结合，零样本提升 VLN 推理与效率。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>dual-process LLM reasoning</td>
<td nowrap>-</td>
<td nowrap>零样本 VLN 推理效率与性能</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38954">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61535">AdaNav: Adaptive Reasoning with Uncertainty for Vision-Language Navigation</a></td>
<td nowrap>AdaNav 用动作熵触发不确定性感知推理，避免固定步长推理带来的额外计算和性能损失。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>uncertainty-adaptive reasoning + RL refinement</td>
<td nowrap>-</td>
<td nowrap>自适应推理触发</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61535">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61535">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64780">Instruction Decomposition and Action Alignment for Vision-Language Navigation</a></td>
<td nowrap>IDEAL-VLN 将长指令分解为因果执行链，并做动作对齐以减少无关文本干扰和视觉 token 延迟。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>instruction decomposition + action alignment</td>
<td nowrap>-</td>
<td nowrap>长程指令分解执行</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64780">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64780">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65809">TIC-VLA: A Think-in-Control Vision-Language-Action Model for Robot Navigation in Dynamic Environments</a></td>
<td nowrap>TIC-VLA 显式建模语义推理延迟，把延迟视觉语言状态接入实时动作控制。</td>
<td nowrap>VLA robot navigation</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>latency-aware VLA control</td>
<td nowrap>-</td>
<td nowrap>在动态人类环境中实现语言指令遵循与实时反应控制。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65809">paper</a></td>
<td nowrap><a href="https://ucla-mobility.github.io/TIC-VLA/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61357">Hydra-Nav: Object Navigation via Adaptive Dual-Process Reasoning</a></td>
<td nowrap>Hydra-Nav 在物体导航中自适应切换慢速历史推理和快速反应，兼顾成功率与计算效率。</td>
<td nowrap>ObjectNav</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>adaptive dual-process VLM reasoning</td>
<td nowrap>-</td>
<td nowrap>解决 unseen object navigation 中时空推理弱和推理开销大的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61357">paper</a></td>
<td nowrap><a href="https://zixuan-wang99.github.io/Hydra-Nav/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60775">SafeDec: Constrained Decoding for Safe Autoregressive Generalist Robot Navigation Policies</a></td>
<td nowrap>SafeDec 对自回归机器人导航策略做约束解码，在生成动作序列时强制满足安全约束。</td>
<td nowrap>安全约束机器人导航</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>constrained decoding</td>
<td nowrap>-</td>
<td nowrap>为可物理执行的通用导航策略加入显式安全正确性。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60775">paper</a></td>
<td nowrap><a href="https://constrained-robot-fms.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2511.20620">Wanderland: Geometrically Grounded Simulation for Open-World Embodied AI</a></td>
<td nowrap>Wanderland 是 real-to-sim 框架，用多传感器采集和几何可靠重建构建开放世界导航仿真评测。</td>
<td nowrap>仿真/评测平台</td>
<td nowrap>开放城市仿真</td>
<td nowrap>-</td>
<td nowrap>planning / RL</td>
<td nowrap>Sim/Benchmark</td>
<td nowrap>提供几何 grounded 的开放城市 embodied AI 闭环评测环境。</td>
<td nowrap><a href="https://arxiv.org/abs/2511.20620">paper</a></td>
<td nowrap><a href="https://ai4ce.github.io/wanderland/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2512.04069">SpaceTools: Tool-Augmented Spatial Reasoning via Double Interactive RL</a></td>
<td nowrap>SpaceTools 通过双交互 RL 学习调用深度、分割、姿态等工具来增强 VLM 的度量空间推理。</td>
<td nowrap>工具增强空间推理</td>
<td nowrap>移动机器人/导航环境</td>
<td nowrap>-</td>
<td nowrap>double interactive RL</td>
<td nowrap>-</td>
<td nowrap>解决 VLM 在 embodied spatial reasoning 中缺少精确度量能力的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2512.04069">paper</a></td>
<td nowrap><a href="https://spacetools.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2512.17907">Dexterous World Models</a></td>
<td nowrap>DWM 是场景-动作条件视频扩散世界模型，用手部动作驱动静态 3D 场景产生动态交互视频。</td>
<td nowrap>灵巧交互世界模型，不是 VLN</td>
<td nowrap>egocentric hand-scene interaction</td>
<td nowrap>-</td>
<td nowrap>world model / planning / RL</td>
<td nowrap>-</td>
<td nowrap>预测灵巧人手与 3D 场景交互后的动态变化。</td>
<td nowrap><a href="https://arxiv.org/abs/2512.17907">paper</a></td>
<td nowrap><a href="https://snuvclab.github.io/dwm/">project</a></td>
<td nowrap><a href="https://github.com/snuvclab/dwm">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2508.09423">Distilling LLM Prior to Flow Model for Generalizable Agent’s Imagination in Object Goal Navigation</a></td>
<td nowrap>GOAL 将 LLM 空间先验蒸馏进 flow model，用生成式语义地图想象支持 ObjectNav。</td>
<td nowrap>ObjectNav/semantic map imagination</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>flow matching + LLM prior</td>
<td nowrap>-</td>
<td nowrap>在未见室内环境中补全未观测区域以提升物体目标导航。</td>
<td nowrap><a href="https://arxiv.org/abs/2508.09423">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/Badi-Li/GOAL">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2511.17225">TP-MDDN: Task-Preferenced Multi-Demand-Driven Navigation with Autonomous Decision-Making</a></td>
<td nowrap>TP-MDDN 提出多需求、带偏好长程导航 benchmark，并用 AWMSystem 分解需求、选目标、监控状态和纠错。</td>
<td nowrap>multi-demand-driven navigation benchmark</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>MASMap 3D point cloud + 2D semantic map</td>
<td nowrap>LLM/MLLM autonomous decision system</td>
<td nowrap>-</td>
<td nowrap>解决多子需求和显式偏好约束下的长程需求驱动导航。</td>
<td nowrap><a href="https://arxiv.org/abs/2511.17225">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.06630">Active Test-time Vision-Language Navigation</a></td>
<td nowrap>ATENA 在测试时主动学习并用熵最小化降低不确定性，减少 VLN 部署到新环境时的累积错误。</td>
<td nowrap>连续 VLN</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>test-time active learning/adaptation</td>
<td nowrap>-</td>
<td nowrap>做无外部反馈条件下的 VLN test-time adaptation。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.06630">paper</a></td>
<td nowrap><a href="https://kuai-lab.github.io/neurips2025atena/">project</a></td>
<td nowrap><a href="https://github.com/kuai-lab/NeurIPS25_att_vln">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.00441">Seeing through Uncertainty: Robust Task-Oriented Optimization in Visual Navigation</a></td>
<td nowrap>NeuRO 将感知网络与任务级鲁棒优化耦合，在小样本视觉导航中处理噪声和 OOD 泛化。</td>
<td nowrap>开放环境</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>learning-to-optimize robust optimization</td>
<td nowrap>-</td>
<td nowrap>解决数据稀缺下长程多目标视觉导航策略过拟合问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.00441">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/PyyWill/NeuRO">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.18525">RoboTron-Nav: A Unified Framework for Embodied Navigation Integrating Perception, Planning, and Prediction</a></td>
<td nowrap>RoboTron-Nav 通过导航和 embodied QA 多任务协作整合感知、规划和预测，减少历史冗余。</td>
<td nowrap>开放环境</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>multitask navigation + EQA</td>
<td nowrap>-</td>
<td nowrap>在语言引导视觉导航中提升未见环境的感知、规划和预测能力。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.18525">paper</a></td>
<td nowrap><a href="https://yvfengzhong.github.io/RoboTron-Nav">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.05552">SAME: Learning Generic Language-Guided Visual Navigation with State-Adaptive Mixture of Experts</a></td>
<td nowrap>SAME 用状态自适应 MoE 统一高层类别搜索和低层语言引导导航。</td>
<td nowrap>generic language-guided visual navigation</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>state-adaptive MoE</td>
<td nowrap>-</td>
<td nowrap>学习可跨多类语言引导导航任务共享的通用策略。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.05552">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/GengzeZhou/SAME">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1984">Embodied Navigation with Auxiliary Task of Action Description Prediction</a></td>
<td nowrap>该文把动作语言描述作为 RL 辅助任务，让导航策略在保持性能的同时解释自己的动作。</td>
<td nowrap>开放环境</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>RL + action description auxiliary task</td>
<td nowrap>-</td>
<td nowrap>可解释导航动作预测</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1984">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.10439">CogNav: Cognitive Process Modeling for Object Goal Navigation with LLMs</a></td>
<td nowrap>CogNav 用 LLM 建模目标记忆和认知更新过程，补强 ObjectNav 中的高层决策。</td>
<td nowrap>ObjectNav</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>cognitive memory</td>
<td nowrap>LLM planning</td>
<td nowrap>-</td>
<td nowrap>让 ObjectNav agent 具备类似人类的认知地图更新和目标推理。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.10439">paper</a></td>
<td nowrap><a href="https://yhancao.github.io/CogNav/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11081">MoMa-Kitchen: A 100K+ Benchmark for Affordance-Grounded Last-Mile Navigation in Mobile Manipulation</a></td>
<td nowrap>MoMa-Kitchen 提供 10 万+ 厨房样本，标注有利于后续操作的最后一段导航终止位姿。</td>
<td nowrap>mobile manipulation last-mile navigation benchmark</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>affordance-grounded labels</td>
<td nowrap>affordance</td>
<td nowrap>Benchmark</td>
<td nowrap>评测移动操作中接近目标后能否停在可操作位置。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11081">paper</a></td>
<td nowrap><a href="https://momakitchen.github.io/">project</a></td>
<td nowrap><a href="https://github.com/MoMaKitchen/MoMaKitchen">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/IPEC-COMMUNITY/MoMa-Kitchen-Data">hf</a></td>
</tr>
</tbody>
</table>

#### 地图记忆

共 22 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>任务类型</th>
<th nowrap>环境</th>
<th nowrap>地图/记忆</th>
<th nowrap>训练/反馈</th>
<th nowrap>Sim/Real/Benchmark</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ACL 2024</td>
<td nowrap><a href="https://aclanthology.org/2024.acl-long.529/">MapGPT: Map-Guided Prompting for Unified Vision-and-Language Navigation</a></td>
<td nowrap>MapGPT uses map-guided prompting to connect language instructions with spatial navigation decisions.</td>
<td nowrap>Vision-language navigation</td>
<td nowrap>indoor VLN</td>
<td nowrap>map-guided prompt memory</td>
<td nowrap>LLM prompting + navigation</td>
<td nowrap>VLN benchmarks</td>
<td nowrap>Use explicit maps to ground LLM navigation decisions.</td>
<td nowrap><a href="https://aclanthology.org/2024.acl-long.529.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Zhao_OVER-NAV_Elevating_Iterative_Vision-and-Language_Navigation_with_Open-Vocabulary_Detection_and_StructurEd_CVPR_2024_paper.html">OVER-NAV: Elevating Iterative Vision-and-Language Navigation with Open-Vocabulary Detection and Structured Representation</a></td>
<td nowrap>OVER-NAV combines open-vocabulary detection with structured scene memory for iterative VLN.</td>
<td nowrap>Vision-language navigation</td>
<td nowrap>indoor VLN</td>
<td nowrap>open-vocabulary structured memory</td>
<td nowrap>iterative navigation planning</td>
<td nowrap>VLN benchmarks</td>
<td nowrap>Improve VLN grounding with open-vocabulary object and scene structure.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Zhao_OVER-NAV_Elevating_Iterative_Vision-and-Language_Navigation_with_Open-Vocabulary_Detection_and_StructurEd_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2403.14158">Volumetric Environment Representation for Vision-Language Navigation</a></td>
<td nowrap>VER builds volumetric scene representations to improve spatial memory and grounding in VLN.</td>
<td nowrap>Vision-language navigation</td>
<td nowrap>3D indoor navigation</td>
<td nowrap>volumetric map memory</td>
<td nowrap>3D representation learning</td>
<td nowrap>VLN benchmarks</td>
<td nowrap>Represent navigable space volumetrically for language-guided navigation.</td>
<td nowrap><a href="https://arxiv.org/abs/2403.14158">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2606.25497">SAGE-Nav: Leveraging LLM Planning and Alignment Fusion for Hierarchical Scene Graph-Guided Navigation</a></td>
<td nowrap>SAGE-Nav 结合 LLM 高层规划和层级场景图，引导 object-goal navigation。</td>
<td nowrap>Object-goal navigation</td>
<td nowrap>indoor navigation</td>
<td nowrap>hierarchical scene graph</td>
<td nowrap>LLM planning + alignment fusion</td>
<td nowrap>Benchmark</td>
<td nowrap>用场景图记忆把语言规划落到目标导航。</td>
<td nowrap><a href="https://arxiv.org/abs/2606.25497">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.02247">WMNav: Integrating Vision-Language Models into World Models for Object Goal Navigation</a></td>
<td nowrap>WMNav 将 VLM 接入导航世界模型，预测未来状态并维护导航记忆以提升目标搜索。</td>
<td nowrap>Object-goal navigation</td>
<td nowrap>indoor navigation</td>
<td nowrap>world-model memory</td>
<td nowrap>VLM-guided world model</td>
<td nowrap>Benchmark</td>
<td nowrap>用世界模型想象和反馈支持 object-goal navigation。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.02247">paper</a></td>
<td nowrap><a href="https://b0b8k1ng.github.io/WMNav/">project</a></td>
<td nowrap><a href="https://github.com/B0B8K1ng/WMNavigation">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=HB6KvsqcAn">Towards Physically Executable 3D Gaussian for Embodied Navigation</a></td>
<td nowrap>SAGE-3D 将 3DGS 升级为带对象语义和物理可执行性的导航环境表示。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>semantic and physically aligned 3D Gaussian</td>
<td nowrap>3DGS environment construction</td>
<td nowrap>-</td>
<td nowrap>3DGS 可执行导航环境</td>
<td nowrap><a href="https://openreview.net/forum?id=HB6KvsqcAn">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=LPv59noPAy">Uncertainty-Aware Gaussian Map for Vision-Language Navigation</a></td>
<td nowrap>该文构建语义 Gaussian Map 并显式编码几何、语义和外观不确定性以指导 VLN 动作。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>uncertainty-aware semantic Gaussian map</td>
<td nowrap>uncertainty-informed policy</td>
<td nowrap>-</td>
<td nowrap>在 VLN 决策中利用感知不确定性而不是忽略模糊观测。</td>
<td nowrap><a href="https://openreview.net/forum?id=LPv59noPAy">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=RnuB0Nlbd5">JanusVLN: Decoupling Semantics and Spatiality with Dual Implicit Memory for Vision-Language Navigation</a></td>
<td nowrap>JanusVLN 用双隐式记忆分别建模语义和空间信息，减少显式文本/帧记忆的冗余和空间损失。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>地图/记忆</td>
<td nowrap>dual implicit neural memory; KV-cache incremental update</td>
<td nowrap>VLN benchmark</td>
<td nowrap>解决 MLLM-VLN 中显式记忆膨胀和空间信息损失。</td>
<td nowrap><a href="https://openreview.net/forum?id=RnuB0Nlbd5">paper</a></td>
<td nowrap><a href="https://miv-xjtu.github.io/JanusVLN.github.io/">project</a></td>
<td nowrap><a href="https://github.com/MIV-XJTU/JanusVLN">code</a></td>
<td nowrap><a href="https://miv-xjtu.github.io/JanusVLN.github.io/">data</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=li1vfqDzRD">Emergence of Spatial Representation in an Actor-Critic Agent with Hippocampus-Inspired Sequence Generator</a></td>
<td nowrap>该文用海马体启发的序列生成器作为时间记忆缓冲，解释 actor-critic 导航 agent 中空间表征涌现。</td>
<td nowrap>神经启发视觉导航/RL</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>hippocampus-inspired temporal sequence memory</td>
<td nowrap>actor-critic RL</td>
<td nowrap>-</td>
<td nowrap>研究连续迷宫视觉导航中空间表征如何由序列记忆机制产生。</td>
<td nowrap><a href="https://openreview.net/forum?id=li1vfqDzRD">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=KcC5mwfGf0">GRL-SNAM: Geometric Reinforcement Learning with Differential Hamiltonians for Navigation and Mapping in Unknown Environments</a></td>
<td nowrap>GRL-SNAM 用局部感知构造 Hamiltonian 能量景观，在未知环境中联合导航与映射而不建全局地图。</td>
<td nowrap>simultaneous navigation and mapping</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>local energy landscape/no global map</td>
<td nowrap>geometric RL</td>
<td nowrap>-</td>
<td nowrap>做未知环境中的同步导航与映射。</td>
<td nowrap><a href="https://openreview.net/forum?id=KcC5mwfGf0">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38884">RflyPano: A Panoramic Benchmark for Ultra-low Altitude UAV Localization Powered by RflySim</a></td>
<td nowrap>RflyPano 是面向 120 米以下 UAV 视觉定位的全景数据集，基于 RflySim 四鱼眼相机生成。</td>
<td nowrap>UAV localization benchmark</td>
<td nowrap>超低空 UAV / RflySim 仿真</td>
<td nowrap>评测/数据而非地图记忆</td>
<td nowrap>localization</td>
<td nowrap>Benchmark</td>
<td nowrap>提供低空 UAV GNSS 不可靠场景下的全景视觉定位 benchmark。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38884">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/DUNDAI1998/RflyPano">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38887">MHED-SLAM: Multi-Scale Hybrid Encoding-Based Decoupled SLAM</a></td>
<td nowrap>MHED-SLAM 用多尺度混合编码和解耦几何/颜色建模提升 NeRF-SLAM 的建图和跟踪质量。</td>
<td nowrap>SLAM</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>neural scene representation</td>
<td nowrap>NeRF/TSDF SLAM</td>
<td nowrap>-</td>
<td nowrap>视觉 SLAM 建图定位</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38887">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38893">LOG-Nav: Efficient Layout-Aware Object-Goal Navigation with Hierarchical Planning</a></td>
<td nowrap>LOG-Nav 用全局拓扑布局地图和局部场景记忆进行层级规划，提升多房间 ObjectNav 效率。</td>
<td nowrap>ObjectNav</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>topological layout map + local scene memory</td>
<td nowrap>LLM hierarchical planning/no costly training</td>
<td nowrap>-</td>
<td nowrap>让 LLM agent 在复杂室内多房间环境中高效找物体。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38893">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38899">PanoNav: Mapless Zero-Shot Object Navigation with Panoramic Scene Parsing and Dynamic Memory</a></td>
<td nowrap>PanoNav 用 RGB-only 全景场景解析和动态记忆实现无地图零样本 ObjectNav。</td>
<td nowrap>zero-shot ObjectNav</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>dynamic memory/mapless RGB-only</td>
<td nowrap>MLLM reasoning</td>
<td nowrap>-</td>
<td nowrap>在无深度、无预建图条件下进行零样本物体导航。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38899">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38901">Lightweight Adaptive Topological Layout and Semantic Mapping in Vision-and-Language Navigation on Websites</a></td>
<td nowrap>ATLAS 为网站 VLN 构建轻量自适应拓扑布局与语义图，提升网页导航准确率和推理速度。</td>
<td nowrap>地图/记忆</td>
<td nowrap>Web navigation，不是物理机器人</td>
<td nowrap>adaptive topological layout + semantic map</td>
<td nowrap>LLM web navigation</td>
<td nowrap>-</td>
<td nowrap>解决 web agent 在开放动态网页结构中的导航和问答。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38901">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38929">Expand Your SCOPE: Semantic Cognition over Potential-Based Exploration for Embodied Visual Navigation</a></td>
<td nowrap>SCOPE 用 frontier 边界和潜势探索建模局部观测与导航目标关系，做零样本视觉导航。</td>
<td nowrap>zero-shot embodied visual navigation</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>frontier/potential-based semantic memory</td>
<td nowrap>zero-shot framework</td>
<td nowrap>-</td>
<td nowrap>提升未知环境中目标导向探索的长程规划。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38929">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38948">Agent Journey Beyond RGB: Hierarchical Semantic-Spatial Representation Enrichment for Vision-and-Language Navigation</a></td>
<td nowrap>SUSA 用层级语义理解和空间感知融合非 RGB 表征，增强 VLN 中语义-空间 grounding。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>hierarchical semantic-spatial representation</td>
<td nowrap>representation enrichment</td>
<td nowrap>-</td>
<td nowrap>解决 egocentric VLN 对多模态环境表示利用不足的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38948">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64902">MapDream: Task-Driven Map Learning for Vision-Language Navigation</a></td>
<td nowrap>MapDream 将地图构建视为任务驱动的 BEV 图像自回归生成，而非手工重建地图。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>learned task-driven BEV map</td>
<td nowrap>map-in-the-loop autoregressive BEV synthesis</td>
<td nowrap>-</td>
<td nowrap>学习直接服务导航目标的地图表示。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64902">paper</a></td>
<td nowrap><a href="https://horizonrobotics.github.io/robot_lab/mapdream/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2605.01736">GLMap: Multi-Scale Gaussian-Language Map for Zero-shot Embodied Navigation and Reasoning</a></td>
<td nowrap>GLMap 用多尺度语义单元同时保存自然语言描述和 3D Gaussian，实现零样本导航与推理。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>multi-scale Gaussian-language map</td>
<td nowrap>zero-shot navigation/reasoning</td>
<td nowrap>-</td>
<td nowrap>给大模型提供几何显式、语义多尺度的 3D map 接口。</td>
<td nowrap><a href="https://arxiv.org/abs/2605.01736">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/sx-zhang/GLMap">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.18546">EfficientNav: Towards On-Device Object-Goal Navigation with Navigation Map Caching and Retrieval</a></td>
<td nowrap>EfficientNav 用导航地图缓存与检索降低本地小 LLM 做 ObjectNav 时的长提示和延迟。</td>
<td nowrap>on-device ObjectNav</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>navigation map caching/retrieval</td>
<td nowrap>small LLM planning</td>
<td nowrap>-</td>
<td nowrap>在端侧设备上高效执行零样本 ObjectNav。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.18546">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/PKU-SEC-Lab/EfficientNav">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.04047">Move to Understand a 3D Scene: Bridging Visual Grounding and Exploration for Efficient and Versatile Embodied Navigation</a></td>
<td nowrap>MTU3D 将主动探索和 3D 视觉语言 grounding 结合，让 agent 通过移动补全场景理解。</td>
<td nowrap>active 3D scene understanding/navigation</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>3D-VL active perception</td>
<td nowrap>3D representation</td>
<td nowrap>-</td>
<td nowrap>决定去哪里看以提升 3D 场景 grounding 和导航效率。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.04047">paper</a></td>
<td nowrap><a href="https://mtu3d.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/944">NavQ: Learning a Q-Model for Foresighted Vision-and-Language Navigation</a></td>
<td nowrap>NavQ 用大规模无标注轨迹训练 Q-model，为候选动作估计未来可见信息以做前瞻决策。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>foresighted Q-feature from trajectory data</td>
<td nowrap>Q-learning on unlabeled trajectories</td>
<td nowrap>-</td>
<td nowrap>前瞻 VLN 决策</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/944">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### 物理可执行导航

共 7 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>任务类型</th>
<th nowrap>环境</th>
<th nowrap>地图/记忆</th>
<th nowrap>训练/反馈</th>
<th nowrap>Sim/Real/Benchmark</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Ehsani_SPOC_Imitating_Shortest_Paths_in_Simulation_Enables_Effective_Navigation_and_CVPR_2024_paper.html">SPOC: Imitating Shortest Paths in Simulation Enables Effective Navigation and Manipulation in the Real World</a></td>
<td nowrap>SPOC trains embodied agents from simulated shortest paths and transfers the behavior to navigation and manipulation.</td>
<td nowrap>Navigation + manipulation</td>
<td nowrap>physical embodied environments</td>
<td nowrap>implicit spatial policy memory</td>
<td nowrap>imitation from shortest paths</td>
<td nowrap>Sim + Real</td>
<td nowrap>Convert shortest-path supervision into physically executable embodied behavior.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Ehsani_SPOC_Imitating_Shortest_Paths_in_Simulation_Enables_Effective_Navigation_and_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38942">CorrectNav: Self-Correction Flywheel Empowers Vision-Language-Action Navigation Model</a></td>
<td nowrap>CorrectNav 利用模型错误轨迹自动生成感知与动作自纠正数据，后训练 VLA 导航模型。</td>
<td nowrap>VLA navigation self-correction</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>self-correction flywheel/post-training</td>
<td nowrap>-</td>
<td nowrap>让 VLA 导航模型偏离正确轨迹后能恢复。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38942">paper</a></td>
<td nowrap><a href="https://correctnav.github.io/">project</a></td>
<td nowrap><a href="https://github.com/owlet914/CorrectNav">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64257">SC$^{2}$-WM: A Self-Correcting World Model with Closed-Loop Feedback for Vision-and-Language Navigation in Continuous Environments</a></td>
<td nowrap>SC2-WM 用世界模型前瞻产生内部反馈，在 VLN-CE 推理中闭环修正状态漂移和计划。</td>
<td nowrap>世界模型导航</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>world-model foresight/internal feedback</td>
<td nowrap>closed-loop self-correcting world model</td>
<td nowrap>-</td>
<td nowrap>解决连续 VLN 中 open-loop 执行无法检测和纠正内部状态漂移。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64257">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64257">project</a></td>
<td nowrap><a href="https://github.com/sunrise-ikun/SC2_WM">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.13019">Rethinking the Embodied Gap in Vision-and-Language Navigation: A Holistic Study of Physical and Visual Disparities</a></td>
<td nowrap>VLN-PE 系统评估 humanoid、quadruped、wheeled robots 上视觉和物理差异对 VLN 的影响。</td>
<td nowrap>physical VLN evaluation</td>
<td nowrap>humanoid/quadruped/wheeled robots</td>
<td nowrap>-</td>
<td nowrap>embodied navigation</td>
<td nowrap>physical robotic settings</td>
<td nowrap>衡量理想 VLN 假设到真实机器人执行之间的 embodied gap。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.13019">paper</a></td>
<td nowrap><a href="https://crystalsixone.github.io/vln_pe.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.23468">NavMorph: A Self-Evolving World Model for Vision-and-Language Navigation in Continuous Environments</a></td>
<td nowrap>NavMorph 用自演化世界模型和上下文演化记忆对 VLN-CE 环境动态进行前瞻建模和策略细化。</td>
<td nowrap>世界模型导航</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>contextual evolution memory</td>
<td nowrap>self-evolving world model/RL</td>
<td nowrap>-</td>
<td nowrap>提升连续 VLN 在新环境和过程变化中的自适应规划。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.23468">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/Feliciaxyao/NavMorph">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/299">3D Gaussian Map with Open-Set Semantic Grouping for Vision-Language Navigation</a></td>
<td nowrap>该文用 open-set semantic grouping 将 3D 几何先验和开放语义统一进 Gaussian map。</td>
<td nowrap>地图/记忆</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>3D Gaussian map + open-set semantic grouping</td>
<td nowrap>3D representation</td>
<td nowrap>-</td>
<td nowrap>开放语义 3D map for VLN</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/299">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1792">monoVLN: Bridging the Observation Gap between Monocular and Panoramic Vision and Language Navigation</a></td>
<td nowrap>monoVLN 用 3DGS 补全单目 RGBD 观测缺失区域，缩小单目机器人和全景 VLN 设置的观测差距。</td>
<td nowrap>monocular VLN</td>
<td nowrap>monocular RGBD robot</td>
<td nowrap>3DGS implicit partial completion</td>
<td nowrap>embodied navigation</td>
<td nowrap>-</td>
<td nowrap>让只有单目相机的机器人执行原本依赖全景观测的 VLN。</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1792">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### 城市/开放环境导航

共 20 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>任务类型</th>
<th nowrap>环境</th>
<th nowrap>地图/记忆</th>
<th nowrap>训练/反馈</th>
<th nowrap>Sim/Real/Benchmark</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Khanna_GOAT-Bench_A_Benchmark_for_Multi-Modal_Lifelong_Navigation_CVPR_2024_paper.html">GOAT-Bench: A Benchmark for Multi-Modal Lifelong Navigation</a></td>
<td nowrap>GOAT-Bench evaluates lifelong navigation with multimodal goals and open-ended object/place targets.</td>
<td nowrap>Lifelong navigation benchmark</td>
<td nowrap>open-world indoor scenes</td>
<td nowrap>goal-conditioned memory</td>
<td nowrap>benchmark evaluation</td>
<td nowrap>GOAT-Bench</td>
<td nowrap>Measure multimodal lifelong navigation beyond single instruction episodes.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Khanna_GOAT-Bench_A_Benchmark_for_Multi-Modal_Lifelong_Navigation_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2024</td>
<td nowrap><a href="https://arxiv.org/pdf/2407.14758">DISCO: Embodied Navigation and Interaction via Differentiable Scene-Conditioned Options</a></td>
<td nowrap>DISCO learns scene-conditioned options for embodied navigation and interaction in open environments.</td>
<td nowrap>Navigation + interaction</td>
<td nowrap>open embodied scenes</td>
<td nowrap>scene-conditioned options</td>
<td nowrap>option learning</td>
<td nowrap>Embodied interaction benchmarks</td>
<td nowrap>Tie navigation and interaction through reusable scene-conditioned options.</td>
<td nowrap><a href="https://arxiv.org/pdf/2407.14758">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=88RKxlFUNY">AutoFly: Vision-Language-Action Model for UAV Autonomous Navigation in the Wild</a></td>
<td nowrap>AutoFly 是端到端 UAV VLA 模型，用伪深度编码和两阶段训练支持野外连续规划与避障。</td>
<td nowrap>开放环境</td>
<td nowrap>无人机/城市环境</td>
<td nowrap>-</td>
<td nowrap>two-stage VLA training</td>
<td nowrap>sim+real UAV</td>
<td nowrap>从显式路线跟随转向粗粒度指令下的自主 UAV 导航。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.09657">paper</a></td>
<td nowrap><a href="https://xiaolousun.github.io/AutoFly/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=OKm3w71ymP">OpenFly: A Comprehensive Platform for Aerial Vision-Language Navigation</a></td>
<td nowrap>OpenFly 集成 UE、GTA V、Google Earth 和 3DGS，生成大规模 aerial VLN 数据和平台。</td>
<td nowrap>aerial VLN platform/benchmark</td>
<td nowrap>无人机/城市环境</td>
<td nowrap>-</td>
<td nowrap>open-world navigation</td>
<td nowrap>Benchmark</td>
<td nowrap>降低 UAV VLN 数据采集成本并提供空中导航评测平台。</td>
<td nowrap><a href="https://openreview.net/forum?id=OKm3w71ymP">paper</a></td>
<td nowrap><a href="https://shailab-ipec.github.io/openfly/">project</a></td>
<td nowrap><a href="https://github.com/Eziotic/OpenFly">code</a></td>
<td nowrap><a href="https://shailab-ipec.github.io/openfly/">data</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=qSak1Hjfdq">All-day Multi-scenes Lifelong Vision-and-Language Navigation with Tucker Adaptation</a></td>
<td nowrap>TuKA 将多场景多时间导航知识表示为 Tucker 分解适配器，缓解全天多场景 VLN 中遗忘。</td>
<td nowrap>lifelong VLN</td>
<td nowrap>无人机/城市环境</td>
<td nowrap>-</td>
<td nowrap>Tucker Adaptation/parameter-efficient tuning</td>
<td nowrap>-</td>
<td nowrap>全天多场景持续适应</td>
<td nowrap><a href="https://openreview.net/forum?id=qSak1Hjfdq">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=PaYo96rjij">Lifelong Embodied Navigation Learning</a></td>
<td nowrap>Uni-Walker 用 DE-LoRA 分离共享和任务特定导航知识，支持多任务序列持续学习。</td>
<td nowrap>lifelong embodied navigation</td>
<td nowrap>无人机/城市环境</td>
<td nowrap>-</td>
<td nowrap>DE-LoRA continual learning</td>
<td nowrap>-</td>
<td nowrap>导航技能持续学习</td>
<td nowrap><a href="https://openreview.net/forum?id=PaYo96rjij">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=hzf23XSDcs">CitySeeker: How Do VLMs Explore Embodied Urban Navigation with Implicit Human Needs?</a></td>
<td nowrap>CitySeeker 用 8 城市 6440 条轨迹评测 VLM 是否能把“我渴了”等隐式需求转成城市导航目标。</td>
<td nowrap>urban implicit-need navigation benchmark</td>
<td nowrap>无人机/城市环境</td>
<td nowrap>-</td>
<td nowrap>open-world navigation</td>
<td nowrap>Benchmark</td>
<td nowrap>评测 VLM 在城市环境中理解隐式人类需求并找目标地点的能力。</td>
<td nowrap><a href="https://openreview.net/forum?id=hzf23XSDcs">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>CitySeeker 6,440 trajectories/8 cities</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38878">AerialVLA: A Vision-Language-Action Model for Aerial Navigation with Online Dialogue</a></td>
<td nowrap>AerialVLA 面向 UAV 视觉对话导航，支持主动询问和利用历史地标纠正路线。</td>
<td nowrap>aerial visual dialogue navigation</td>
<td nowrap>UAV</td>
<td nowrap>-</td>
<td nowrap>online dialogue VLA</td>
<td nowrap>-</td>
<td nowrap>让 UAV 通过在线对话到达目标并主动修正导航。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38878">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38885">History-Enhanced Two-Stage Transformer for Aerial Vision-and-Language Navigation</a></td>
<td nowrap>HETT 先用历史网格地图粗定位目标，再用细粒度视觉分析优化 UAV 动作。</td>
<td nowrap>开放环境</td>
<td nowrap>large-scale urban UAV</td>
<td nowrap>historical grid map</td>
<td nowrap>coarse-to-fine two-stage transformer</td>
<td nowrap>-</td>
<td nowrap>平衡 aerial VLN 中全局环境推理和局部场景理解。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38885">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38897">RENEW: Risk- and Energy-Aware Navigation in Dynamic Waterways</a></td>
<td nowrap>RENEW 为动态水流扰动下的 ASV 规划风险和能耗感知路径，并加入自适应安全约束。</td>
<td nowrap>ASV global path planning</td>
<td nowrap>dynamic waterways</td>
<td nowrap>-</td>
<td nowrap>risk/energy-aware planning</td>
<td nowrap>-</td>
<td nowrap>水域导航而非 VLN</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38897">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38898">Towards Autonomous UAV Visual Object Search in City Space: Benchmark and Agentic Methodology</a></td>
<td nowrap>CityAVOS 提供 2420 个城市 UAV 视觉目标搜索任务，并用 PRPSearcher 做感知-推理-规划搜索。</td>
<td nowrap>UAV visual object search benchmark</td>
<td nowrap>无人机/城市环境</td>
<td nowrap>3D cognitive/uncertainty/dynamic semantic maps</td>
<td nowrap>open-world navigation</td>
<td nowrap>Benchmark</td>
<td nowrap>让 UAV 在城市空间中自主搜索静态目标物体。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38898">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>CityAVOS 2,420 tasks</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38916">UrbanNav: Learning Language-Guided Embodied Urban Navigation from Web-Scale Human Trajectories</a></td>
<td nowrap>UrbanNav 用网页级城市步行视频和语言轨迹对齐，训练 agent 按自由语言在城市中导航。</td>
<td nowrap>language-guided urban navigation</td>
<td nowrap>ground urban robot</td>
<td nowrap>-</td>
<td nowrap>open-world navigation</td>
<td nowrap>-</td>
<td nowrap>支持最后一公里机器人在陌生城市街景中按自然语言导航。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38916">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/CASIA-IVA-Lab/UrbanNav">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/Vigar001/UrbanNav">hf</a></td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38917">Autonomous Vehicle Path Planning by Searching with Differentiable Simulation</a></td>
<td nowrap>DSS 用可微 Waymax 模拟器作为状态预测器和 critic，通过梯度搜索自动驾驶动作序列。</td>
<td nowrap>autonomous driving path planning</td>
<td nowrap>Waymax/traffic scenarios</td>
<td nowrap>-</td>
<td nowrap>differentiable simulation search</td>
<td nowrap>-</td>
<td nowrap>自动驾驶规划而非 VLN</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38917">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38920">Real-Time Path Planning for UAVs in Windy Environments Without Computational Fluid Dynamics</a></td>
<td nowrap>GZS 无需 CFD，用点云局部拓扑和物理启发风风险建模进行实时 UAV 路径规划。</td>
<td nowrap>UAV real-time path planning</td>
<td nowrap>windy cluttered 3D environments</td>
<td nowrap>-</td>
<td nowrap>zero-shot training-free planning</td>
<td nowrap>-</td>
<td nowrap>在有风扰和障碍的 3D 环境中做机载实时 UAV 规划。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38920">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38938">ReflexDiffusion: Reflection-Enhanced Trajectory Planning for High-lateral-acceleration Scenarios in Autonomous Driving</a></td>
<td nowrap>ReflexDiffusion 在扩散轨迹规划推理阶段加入反思式梯度调整，处理高横向加速度长尾场景。</td>
<td nowrap>autonomous driving trajectory planning</td>
<td nowrap>high-lateral-acceleration driving</td>
<td nowrap>-</td>
<td nowrap>inference-stage diffusion reflection</td>
<td nowrap>-</td>
<td nowrap>自动驾驶规划而非开放 VLN</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38938">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38941">Learning from Human Gaze: Human-like Robot Social Navigation in Dense Crowds</a></td>
<td nowrap>GazeNav/Gaze2Nav 用人类眼动数据预测社交注意对象，并把该注意注入拥挤人群运动规划。</td>
<td nowrap>social navigation</td>
<td nowrap>dense crowds</td>
<td nowrap>gaze/semantic attention</td>
<td nowrap>open-world navigation</td>
<td nowrap>GazeNav dataset</td>
<td nowrap>让机器人在密集人群中进行更像人的社交导航。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38941">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63554">Plan in Sandbox, Navigate in Open Worlds: Learning Physics-Grounded Abstracted Experience for Embodied Navigation</a></td>
<td nowrap>SAGE 让 agent 在物理 grounded 的语义抽象 sandbox 中学习，再迁移到开放世界导航。</td>
<td nowrap>开放环境</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>physics-grounded abstracted experience/RL</td>
<td nowrap>-</td>
<td nowrap>用抽象物理经验减少对逼真仿真的依赖并提升开放世界导航。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63554">paper</a></td>
<td nowrap><a href="https://frankzxshen.github.io/SAGE">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.20685">C-NAV: Towards Self-Evolving Continual Object Navigation in Open World</a></td>
<td nowrap>C-Nav 提出持续 ObjectNav benchmark，并用双路径抗遗忘机制学习新物体类别同时保留旧知识。</td>
<td nowrap>continual ObjectNav benchmark</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>dual-path anti-forgetting/RL</td>
<td nowrap>-</td>
<td nowrap>在动态开放世界中持续学习新目标类别的物体导航。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.20685">paper</a></td>
<td nowrap><a href="https://bigtree765.github.io/C-Nav-project/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2512.10046">SimWorld-Robotics: Synthesizing Photorealistic and Dynamic Urban Environments for Multimodal Robot Navigation and Collaboration</a></td>
<td nowrap>SimWorld-Robotics 用 UE5 程序化生成动态城市，提供多模态指令导航和多机器人搜索协作 benchmark。</td>
<td nowrap>urban simulation benchmark</td>
<td nowrap>无人车/城市环境</td>
<td nowrap>-</td>
<td nowrap>open-world navigation</td>
<td nowrap>Sim/Benchmark</td>
<td nowrap>构建大规模逼真城市仿真以评测机器人开放环境导航和协作。</td>
<td nowrap><a href="https://arxiv.org/abs/2512.10046">paper</a></td>
<td nowrap><a href="https://scai.cs.jhu.edu/projects/SimWorldRobotics/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2408.15503">RoboSense: Large-scale Dataset and Benchmark for Egocentric Robot Perception and Navigation in Crowded and Unstructured Environments</a></td>
<td nowrap>RoboSense 提供相机、LiDAR、鱼眼等多传感器 egocentric 数据，评测拥挤非结构环境中的感知和导航。</td>
<td nowrap>评测/数据</td>
<td nowrap>crowded/unstructured egocentric robot environments</td>
<td nowrap>-</td>
<td nowrap>open-world navigation</td>
<td nowrap>Benchmark</td>
<td nowrap>建立面向移动机器人近场感知与导航的数据集和 benchmark。</td>
<td nowrap><a href="https://arxiv.org/abs/2408.15503">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/suhaisheng/RoboSense">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/suhaisheng0527/RoboSense">hf</a></td>
</tr>
</tbody>
</table>

#### 低成本/端侧导航

共 3 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>任务类型</th>
<th nowrap>环境</th>
<th nowrap>地图/记忆</th>
<th nowrap>训练/反馈</th>
<th nowrap>Sim/Real/Benchmark</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.11886">Aux-Think: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation</a></td>
<td nowrap>Aux-Think 系统比较 No/Pre/Post-Think 推理策略，发现 VLN 中推理可能坍缩并构建 R2R-CoT-320k。</td>
<td nowrap>data-efficient VLN reasoning</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>reasoning strategy evaluation</td>
<td nowrap>-</td>
<td nowrap>研究数据高效 VLN 中何种推理策略真正有用。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.11886">paper</a></td>
<td nowrap><a href="https://horizonrobotics.github.io/robot_lab/aux-think/">project</a></td>
<td nowrap>-</td>
<td nowrap>R2R-CoT-320k</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://openreview.net/pdf?id=5gptKWnVPF">Harnessing Input-Adaptive Inference for Efficient VLN</a></td>
<td nowrap>该文在视角选择、early-exit 阈值和历史视图缓存三个层面做输入自适应推理，使 VLN 计算量降低 2 倍以上。</td>
<td nowrap>端侧/低成本</td>
<td nowrap>移动机器人/导航环境</td>
<td nowrap>-</td>
<td nowrap>efficient navigation</td>
<td nowrap>7 VLN benchmarks</td>
<td nowrap>在保持性能的同时降低历史感知 transformer VLN agent 的推理成本。</td>
<td nowrap><a href="https://arxiv.org/abs/2508.09262">paper</a></td>
<td nowrap><a href="https://true-lab.ai/efficient_vln/">project</a></td>
<td nowrap><a href="https://github.com/secure-ai-systems-group/adaptive-vision-and-language-navigation">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.24065">COSMO: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation</a></td>
<td nowrap>COSMO 结合状态空间模块和 transformer，并设计 RSS 与跨模态选择记忆以降低 VLN 计算成本。</td>
<td nowrap>端侧/低成本</td>
<td nowrap>移动机器人/移动操作</td>
<td nowrap>-</td>
<td nowrap>selective state-space memorization + transformer</td>
<td nowrap>-</td>
<td nowrap>低成本 VLN 模型结构</td>
<td nowrap><a href="https://arxiv.org/abs/2503.24065">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

### VLA / 操作策略

VLA 是机械臂和移动操作的主战场，但它不只是“大模型接动作头”。调研论文集中在动作表示、diffusion/flow policy、3D grounding、在线/RL 微调和安全鲁棒性上。

子方向：generalist VLA、action representation、diffusion/flow policy、3D grounding、online/RL fine-tuning、安全鲁棒性。

共 213 篇。

<table>
<thead>
<tr>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>观察重点</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>generalist VLA</td>
<td nowrap>70</td>
<td nowrap>看跨任务泛化、真实机器人验证和通用操作能力。</td>
</tr>
<tr>
<td nowrap>action representation</td>
<td nowrap>21</td>
<td nowrap>看动作 token、latent action、chunking 和动作空间设计。</td>
</tr>
<tr>
<td nowrap>diffusion/flow policy</td>
<td nowrap>68</td>
<td nowrap>看连续动作生成、稳定控制和执行平滑性。</td>
</tr>
<tr>
<td nowrap>3D grounding</td>
<td nowrap>31</td>
<td nowrap>看点云、几何、affordance 与操作定位。</td>
</tr>
<tr>
<td nowrap>online/RL fine-tuning</td>
<td nowrap>16</td>
<td nowrap>看在线强化、人在回路和测试时适配。</td>
</tr>
<tr>
<td nowrap>安全鲁棒性</td>
<td nowrap>7</td>
<td nowrap>看攻击鲁棒、安全对齐和风险暴露。</td>
</tr>
</tbody>
</table>

#### generalist VLA

共 70 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>Base VLA</th>
<th nowrap>Action</th>
<th nowrap>训练/反馈</th>
<th nowrap>Algorithm</th>
<th nowrap>Policy/Type</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Li_ManipLLM_Embodied_Multimodal_Large_Language_Model_for_Object-Centric_Robotic_Manipulation_CVPR_2024_paper.html">ManipLLM: Embodied Multimodal Large Language Model for Object-Centric Robotic Manipulation</a></td>
<td nowrap>ManipLLM grounds multimodal language reasoning in object-centric robotic manipulation.</td>
<td nowrap>multimodal LLM</td>
<td nowrap>robot action</td>
<td nowrap>VLA / Generalist VLA</td>
<td nowrap>object-centric embodied reasoning</td>
<td nowrap>robot manipulation policy</td>
<td nowrap>simulation manipulation</td>
<td nowrap>Use multimodal LLM reasoning for object-centric manipulation.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Li_ManipLLM_Embodied_Multimodal_Large_Language_Model_for_Object-Centric_Robotic_Manipulation_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2024/hash/62203a74e233e933b160711e791e1a02-Abstract-Conference.html">PEAC: Unsupervised Pre-training for Cross-Embodiment Reinforcement Learning</a></td>
<td nowrap>PEAC pretrains policies across embodiments to improve transfer before downstream robot learning.</td>
<td nowrap>cross-embodiment policy</td>
<td nowrap>robot action</td>
<td nowrap>VLA / cross-embodiment</td>
<td nowrap>unsupervised pretraining</td>
<td nowrap>generalist robot policy</td>
<td nowrap>cross-embodiment benchmarks</td>
<td nowrap>Improve cross-embodiment policy transfer.</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2024/file/62203a74e233e933b160711e791e1a02-Paper-Conference.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2025/html/Chen_CombatVLA_An_Efficient_Vision-Language-Action_Model_for_Combat_Tasks_in_3D_ICCV_2025_paper.html">CombatVLA: An Efficient Vision-Language-Action Model for Combat Tasks in 3D Action Role-Playing Games</a></td>
<td nowrap>CombatVLA studies efficient VLA control for real-time 3D game combat tasks.</td>
<td nowrap>CombatVLA</td>
<td nowrap>game action</td>
<td nowrap>VLA / Generalist VLA</td>
<td nowrap>efficient VLA control</td>
<td nowrap>real-time embodied agent</td>
<td nowrap>3D game tasks</td>
<td nowrap>Evaluate VLA-style action models in fast 3D interactive tasks.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2025/papers/Chen_CombatVLA_An_Efficient_Vision-Language-Action_Model_for_Combat_Tasks_in_3D_ICCV_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://openreview.net/forum?id=lFYj0oibGR">Vision-Language Foundation Models as Effective Robot Imitators</a></td>
<td nowrap>This work adapts vision-language foundation models as robot imitators for manipulation policies.</td>
<td nowrap>VLM foundation model</td>
<td nowrap>robot action</td>
<td nowrap>imitation learning</td>
<td nowrap>VLM-to-policy adaptation</td>
<td nowrap>robot imitation policy</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Use pretrained VLMs as effective robot imitation learners.</td>
<td nowrap><a href="https://openreview.net/forum?id=lFYj0oibGR">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2023</td>
<td nowrap><a href="https://arxiv.org/abs/2311.01977">RT-Trajectory: Robotic Task Generalization via Hindsight Trajectory Sketches</a></td>
<td nowrap>RT-Trajectory uses hindsight trajectory sketches to improve robot task generalization.</td>
<td nowrap>robot policy</td>
<td nowrap>trajectory sketches</td>
<td nowrap>VLA / Generalist VLA</td>
<td nowrap>hindsight trajectory conditioning</td>
<td nowrap>generalist manipulation policy</td>
<td nowrap>robot manipulation tasks</td>
<td nowrap>Improve task generalization with trajectory sketch supervision.</td>
<td nowrap><a href="https://arxiv.org/abs/2311.01977">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2023</td>
<td nowrap><a href="https://openreview.net/forum?id=nkDMZ8yqBt">VIMA: General Robot Manipulation with Multimodal Prompts</a></td>
<td nowrap>VIMA formulates robot manipulation as multimodal prompt-conditioned policy learning.</td>
<td nowrap>VIMA</td>
<td nowrap>manipulation action</td>
<td nowrap>multimodal prompt policy</td>
<td nowrap>prompt-conditioned imitation</td>
<td nowrap>generalist manipulation policy</td>
<td nowrap>VIMA-Bench</td>
<td nowrap>Use multimodal prompts to specify diverse manipulation tasks.</td>
<td nowrap><a href="https://openreview.net/forum?id=nkDMZ8yqBt">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://proceedings.iclr.cc/paper_files/paper/2025/hash/8667f264f88c7938a73a53ab01eb1327-Abstract-Conference.html">TraceVLA: Visual Trace Prompting Enhances Spatial-Temporal Awareness for Generalist Robotic Policies</a></td>
<td nowrap>TraceVLA adds visual trace prompts to improve spatial-temporal awareness in generalist robot policies.</td>
<td nowrap>generalist VLA</td>
<td nowrap>robot action</td>
<td nowrap>VLA / Generalist VLA</td>
<td nowrap>visual trace prompting</td>
<td nowrap>generalist robot policy</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Enhance robot policy awareness with visual traces.</td>
<td nowrap><a href="https://proceedings.iclr.cc/paper_files/paper/2025/hash/8667f264f88c7938a73a53ab01eb1327-Abstract-Conference.html">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2024</td>
<td nowrap><a href="https://openreview.net/forum?id=Sa7upAJOIN">QUAR-VLA: Vision-Language-Action Model for Quadruped Robots</a></td>
<td nowrap>QUAR-VLA extends VLA-style policy learning to quadruped robot control.</td>
<td nowrap>quadruped VLA</td>
<td nowrap>locomotion action</td>
<td nowrap>VLA / quadruped robots</td>
<td nowrap>vision-language-action control</td>
<td nowrap>quadruped policy</td>
<td nowrap>quadruped robot tasks</td>
<td nowrap>Apply VLA modeling to quadruped embodied control.</td>
<td nowrap><a href="https://openreview.net/forum?id=Sa7upAJOIN">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2508.05186">Learning to See and Act: Task-Aware Virtual View Exploration for Robotic Manipulation</a></td>
<td nowrap>This work uses task-aware virtual view exploration to improve perception and action in manipulation.</td>
<td nowrap>robot manipulation model</td>
<td nowrap>manipulation action</td>
<td nowrap>VLA / Generalist VLA</td>
<td nowrap>virtual-view exploration</td>
<td nowrap>robot manipulation policy</td>
<td nowrap>manipulation benchmarks</td>
<td nowrap>Use task-aware view exploration for better manipulation policy inputs.</td>
<td nowrap><a href="https://arxiv.org/abs/2508.05186">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2409.12514">TinyVLA: Towards Fast, Data-Efficient Vision-Language-Action Models for Robotic Manipulation</a></td>
<td nowrap>TinyVLA 用小型 VLA 和 diffusion policy 提升机器人操作的数据效率与推理速度。</td>
<td nowrap>TinyVLA</td>
<td nowrap>Diffusion action</td>
<td nowrap>VLA / Generalist VLA</td>
<td nowrap>compact VLA + diffusion policy</td>
<td nowrap>data-efficient VLA</td>
<td nowrap>Real robot manipulation</td>
<td nowrap>构建更小、更快的数据高效 VLA 操作策略。</td>
<td nowrap><a href="https://arxiv.org/abs/2409.12514">paper</a></td>
<td nowrap><a href="https://tiny-vla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/JayceWen/tinyvla">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2502.05485">HAMSTER: Hierarchical Action Models For Open-World Robot Manipulation</a></td>
<td nowrap>HAMSTER 用分层动作模型连接开放世界操作中的高层决策和低层可执行机器人动作。</td>
<td nowrap>HAMSTER</td>
<td nowrap>hierarchical action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>hierarchical action modeling</td>
<td nowrap>open-world manipulation policy</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>构建带显式动作层级的开放世界机器人操作策略。</td>
<td nowrap><a href="https://arxiv.org/abs/2502.05485">paper</a></td>
<td nowrap><a href="https://hamster-robot.github.io/">project</a></td>
<td nowrap><a href="https://github.com/liyi14/HAMSTER_beta">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2406.20095">LLaRA: Supercharging Robot Learning Data for Vision-Language Policy</a></td>
<td nowrap>LLaRA 通过转换和增强机器人学习数据，提升视觉语言策略训练效果。</td>
<td nowrap>LLaRA</td>
<td nowrap>policy action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>robot-data augmentation for VLP/VLA</td>
<td nowrap>vision-language policy</td>
<td nowrap>robot learning datasets</td>
<td nowrap>用更强的语言对齐训练数据提升机器人策略学习。</td>
<td nowrap><a href="https://arxiv.org/abs/2406.20095">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/LostXine/LLaRA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=54U3XHf7qq">MemoryVLA: Perceptual-Cognitive Memory in Vision-Language-Action Models for Robotic Manipulation</a></td>
<td nowrap>提出带工作记忆与长期感知-认知记忆库的 VLA，使长时序操作能利用历史上下文生成动作。</td>
<td nowrap>VLM + diffusion action expert</td>
<td nowrap>Diffusion action sequences</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Cognition-Memory-Action + Perceptual-Cognitive Memory Bank</td>
<td nowrap>memory-conditioned VLA</td>
<td nowrap>Sim + Real</td>
<td nowrap>长时序机器人操作中的历史记忆建模</td>
<td nowrap><a href="https://openreview.net/forum?id=54U3XHf7qq">paper</a></td>
<td nowrap><a href="https://shihao1895.github.io/MemoryVLA">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=DdrsHWobR1">Disentangled Robot Learning via Separate Forward and Inverse Dynamics Pretraining</a></td>
<td nowrap>DeFI 将视觉前向动力学与逆动力学预训练解耦，再统一微调用于动作预测。</td>
<td nowrap>DeFI</td>
<td nowrap>latent action / inverse dynamics</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>GFDM + GIDM disentangled pretraining</td>
<td nowrap>forward-inverse dynamics VLA</td>
<td nowrap>Sim + Real</td>
<td nowrap>解耦视频预测与动作预测以提升泛化</td>
<td nowrap><a href="https://openreview.net/forum?id=DdrsHWobR1">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=IBJtOltTbx">Hybrid Training for Vision-Language-Action Models</a></td>
<td nowrap>HyT 让 VLA 从 CoT 推理轨迹中学习，但测试时可直接输出动作以保持快速推理。</td>
<td nowrap>-</td>
<td nowrap>AR/direct action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Hybrid Training</td>
<td nowrap>CoT-trained direct-action VLA</td>
<td nowrap>Sim + Real</td>
<td nowrap>在保留推理收益的同时降低 VLA 推理延迟</td>
<td nowrap><a href="https://openreview.net/forum?id=IBJtOltTbx">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=LYyoRqf0Ij">End-to-end Listen, Look, Speak and Act</a></td>
<td nowrap>ELLSA 用 SA-MoE 在单一架构中同时感知并生成视觉、文本、语音和动作。</td>
<td nowrap>ELLSA</td>
<td nowrap>multimodal action generation</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>SA-MoE</td>
<td nowrap>full-duplex omni-modal VLA</td>
<td nowrap>speech-interaction + robot benchmarks</td>
<td nowrap>端到端多模态交互与动作生成</td>
<td nowrap><a href="https://openreview.net/forum?id=LYyoRqf0Ij">paper</a></td>
<td nowrap><a href="https://anonymous.4open.science/r/LLSA-E821">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=OJh7oBCYhL">RoboOmni: Proactive Robot Manipulation in Omni-modal Context</a></td>
<td nowrap>RoboOmni 从语音、环境声和视觉线索中主动推断意图并执行操作。</td>
<td nowrap>omni-modal LLM</td>
<td nowrap>executor action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Perceiver-Thinker-Talker-Executor</td>
<td nowrap>proactive omni-modal VLA</td>
<td nowrap>-</td>
<td nowrap>跨模态上下文中的主动机器人操作</td>
<td nowrap><a href="https://openreview.net/forum?id=OJh7oBCYhL">paper</a> / <a href="https://arxiv.org/pdf/2510.23763">paper</a></td>
<td nowrap><a href="https://openmoss.github.io/RoboOmni/">project</a></td>
<td nowrap><a href="https://github.com/OpenMOSS/RoboOmni">code</a></td>
<td nowrap><a href="https://huggingface.co/OpenMOSS-Team/RoboOmni">hf</a> / <a href="https://huggingface.co/datasets/fnlp/OmniAction">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=PklMD8PwUy">Unified Vision-Language-Action Model</a></td>
<td nowrap>UniVLA 将视觉、语言、动作统一为离散 token 序列，并用世界模型后训练提升长程策略学习。</td>
<td nowrap>UniVLA</td>
<td nowrap>discrete token AR</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>unified multimodal token modeling + world-model post-training</td>
<td nowrap>autoregressive unified VLA</td>
<td nowrap>CALVIN/LIBERO/SimplerEnv + ALOHA real</td>
<td nowrap>解决传统 VLA 过度依赖 VLM 语义、忽略视觉中的时序因果结构的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=PklMD8PwUy">paper</a> / <a href="https://arxiv.org/abs/2503.10631">paper</a> / <a href="https://arxiv.org/abs/2506.19850">paper</a></td>
<td nowrap><a href="https://hybrid-vla.github.io/">project</a> / <a href="https://robertwyq.github.io/univla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/PKU-HMI-Lab/Hybrid-VLA">code</a> / <a href="https://github.com/baaivision/UniVLA">code</a></td>
<td nowrap>CALVIN/LIBERO/SimplerEnv/ALOHA</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=T3i7Ifeatk">Align-Then-stEer: Adapting the Vision-Language Action Models through Unified Latent Guidance</a></td>
<td nowrap>ATE 先对齐不同动作空间，再用统一潜空间指导扩散/flow VLA 适配新任务和新本体。</td>
<td nowrap>pretrained diffusion/flow VLA</td>
<td nowrap>latent action guidance</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>Align-Then-stEer / reverse-KL VAE latent alignment</td>
<td nowrap>plug-in adaptation</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决预训练 VLA 下游适配时动作分布错配、数据和算力成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=T3i7Ifeatk">paper</a> / <a href="https://arxiv.org/abs/2509.02055">paper</a></td>
<td nowrap><a href="https://align-then-steer.github.io/">project</a></td>
<td nowrap><a href="https://github.com/TeleHuman/Align-Then-Steer">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=UD4Rw8MOEK">Verifier-free Test-Time Sampling for Vision Language Action Models</a></td>
<td nowrap>MG-Select 用模型内部 masked reference action distribution 的 KL 置信度在测试时选择动作候选。</td>
<td nowrap>-</td>
<td nowrap>AR candidate selection</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>MG-Select / masking distribution guided selection</td>
<td nowrap>verifier-free test-time scaling</td>
<td nowrap>Sim + Real</td>
<td nowrap>无额外 verifier 的测试时动作选择</td>
<td nowrap><a href="https://openreview.net/forum?id=UD4Rw8MOEK">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=kt51kZH4aG">X-VLA: Soft-Prompted Transformer as Scalable Cross-Embodiment Vision-Language-Action Model</a></td>
<td nowrap>X-VLA 用本体特定 soft prompts 和 flow-matching Transformer 学习跨机器人平台的通用控制。</td>
<td nowrap>X-VLA</td>
<td nowrap>flow-matching continuous action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>embodiment-specific soft prompts</td>
<td nowrap>cross-embodiment VLA</td>
<td nowrap>6 sim envs + 3 real platforms</td>
<td nowrap>跨本体 VLA 训练与泛化</td>
<td nowrap><a href="https://openreview.net/forum?id=kt51kZH4aG">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=tc2UsBeODW">VLM4VLA: Revisiting Vision-Language-Models in Vision-Language-Action Models</a></td>
<td nowrap>VLM4VLA 系统比较不同 VLM 作为 VLA backbone 的迁移效果，指出通用 VLM 能力不能直接预测控制性能。</td>
<td nowrap>VLM4VLA minimal adapter</td>
<td nowrap>policy action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>minimal VLM-to-VLA adaptation + embodied capability ablation</td>
<td nowrap>benchmark/adaptation pipeline</td>
<td nowrap>3 benchmarks</td>
<td nowrap>评估 VLM backbone 对 VLA 控制的真实贡献</td>
<td nowrap><a href="https://openreview.net/forum?id=tc2UsBeODW">paper</a></td>
<td nowrap><a href="https://cladernyjorn.github.io/VLM4VLA.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=tsxwloasw5">Vision-Language-Action Instruction Tuning: From Understanding to Manipulation</a></td>
<td nowrap>InstructVLA 用 VLA instruction tuning 同时保留 VLM 推理能力并提升精细操作性能。</td>
<td nowrap>InstructVLA</td>
<td nowrap>AR/action generation</td>
<td nowrap>VLA / RL/在线微调</td>
<td nowrap>VLA-IT + MoE adaptation</td>
<td nowrap>end-to-end instruction-tuned VLA</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 在视觉语言理解与动作生成之间互相牺牲、且容易遗忘预训练能力的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=tsxwloasw5">paper</a> / <a href="https://arxiv.org/abs/2507.17520">paper</a></td>
<td nowrap><a href="https://yangs03.github.io/InstructVLA_Home/">project</a></td>
<td nowrap><a href="https://github.com/InternRobotics/InstructVLA">code</a></td>
<td nowrap>650K VLA-IT dataset</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=KcJ9U0x6kO">HAMLET: Switch Your Vision-Language-Action Model into a History-Aware Policy</a></td>
<td nowrap>HAMLET 用 moment tokens 和轻量记忆模块把只看当前帧的 VLA 改造成历史感知策略。</td>
<td nowrap>GR00T N1.5 / pretrained VLA</td>
<td nowrap>history-aware action prediction</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>moment tokens + time-contrastive init + memory module</td>
<td nowrap>history-aware VLA adapter</td>
<td nowrap>RoboCasa/LIBERO + real</td>
<td nowrap>长程历史依赖操作</td>
<td nowrap><a href="https://openreview.net/forum?id=KcJ9U0x6kO">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38902">DiTEA: Mixture-of-Experts for Vision-Language-Action Model in Robotic Manipulation</a></td>
<td nowrap>DiTEA 在扩散 VLA action head 中加入 Action MoE 和任务指令门控以减轻多任务遗忘。</td>
<td nowrap>diffusion-based VLA</td>
<td nowrap>Diffusion</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Diffusion Transformer Action MoE + Task-Instruction Gate</td>
<td nowrap>MoE VLA</td>
<td nowrap>Sim + Real</td>
<td nowrap>多任务扩散 VLA 的指令跟随与抗遗忘</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38902">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38910">TTF-VLA: Temporal Token Fusion via Pixel-Attention Integration for Vision-Language-Action Models</a></td>
<td nowrap>TTF-VLA 训练自由地融合历史与当前视觉 token，提升 VLA 在噪声和时序场景下的推理质量。</td>
<td nowrap>OpenVLA / VLA-Cache</td>
<td nowrap>token-level inference enhancement</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Temporal Token Fusion + pixel difference + attention relevance</td>
<td nowrap>training-free inference plugin</td>
<td nowrap>LIBERO + SimplerEnv + Real</td>
<td nowrap>时序视觉 token 融合</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38910">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62813">Being-H0: Vision-Language-Action Pretraining from Large-Scale Human Videos</a></td>
<td nowrap>Being-H0 从大规模人手视频中进行物理指令调优和手部运动 token 化，迁移到灵巧操作。</td>
<td nowrap>Being-H0</td>
<td nowrap>part-level motion tokens / AR</td>
<td nowrap>VLA / RL/在线微调</td>
<td nowrap>physical instruction tuning + hand motion tokenization</td>
<td nowrap>dexterous VLA</td>
<td nowrap>human video pretrain + real robot</td>
<td nowrap>解决 VLA 依赖昂贵机器人示教、灵巧操作泛化不足的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62813">paper</a> / <a href="https://arxiv.org/pdf/2507.15597">paper</a> / <a href="https://arxiv.org/abs/2507.15597">paper</a></td>
<td nowrap><a href="https://beingbeyond.github.io/Being-H0">project</a> / <a href="https://beingbeyond.github.io/Being-H0/">project</a></td>
<td nowrap><a href="https://github.com/BeingBeyond/Being-H0">code</a></td>
<td nowrap>BeingBeyond h0_post_train dataset</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60980">RA-VLA: Retrieval-Augmented VLA for Test-Time Adaptation</a></td>
<td nowrap>RA-VLA 用行为对齐检索和 grounded execution pipeline 在无需训练的测试时适配新任务分布。</td>
<td nowrap>RA-VLA</td>
<td nowrap>retrieval-grounded action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>behavior-aligned retrieval + grounded execution</td>
<td nowrap>test-time adaptation VLA</td>
<td nowrap>LIBERO + UR5e real</td>
<td nowrap>训练自由测试时适配</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60980">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60980">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62270">A Generalist Pair-wise Progress Critic Model for Vision-Language-Action Robots</a></td>
<td nowrap>VLAC 将动作策略与成对任务进度 critic 统一在自回归架构中，为 RL 提供内在奖励。</td>
<td nowrap>VLAC</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL/在线微调</td>
<td nowrap>pair-wise progress critic + intrinsic reward RL</td>
<td nowrap>action-critic VLA</td>
<td nowrap>diverse tasks + real RL</td>
<td nowrap>通用任务进度评估与动作生成</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62270">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62270">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62528">Bring My Cup! Personalizing Vision-Language-Action Models with Visual Attentive Prompting</a></td>
<td nowrap>VAP 用少量参考图像作为视觉记忆，对冻结 VLA 注入目标实例注意力以执行个性化指令。</td>
<td nowrap>frozen VLA</td>
<td nowrap>visual-prompted action</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Visual Attentive Prompting</td>
<td nowrap>training-free personalization adapter</td>
<td nowrap>Personalized-SIMPLER/Personalized-VLABench + real</td>
<td nowrap>个性化对象操作</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62528">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62528">project</a></td>
<td nowrap>-</td>
<td nowrap>Personalized-SIMPLER</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66596">From Abstraction to Instantiation: Learning Behavioral Representation for Vision-Language-Action Model</a></td>
<td nowrap>BehaviorVLA 学习长时序行为表征，并按执行阶段解码为精确动作以增强分布外泛化。</td>
<td nowrap>BehaviorVLA</td>
<td nowrap>AR / behavior-conditioned decoding</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>VBE + PBD</td>
<td nowrap>behavior-representation VLA</td>
<td nowrap>RoboTwin2/LIBERO/CALVIN + real sim2real</td>
<td nowrap>时序一致行为表征</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66596">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66596">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61157">VLA-ATTC: Adaptive Test-Time Compute for VLA Models with Relative Action Critic Model</a></td>
<td nowrap>VLA-ATTC 用不确定性触发测试时思考，并用相对动作 critic 在候选动作中选择最优。</td>
<td nowrap>PI0.5 / VLA</td>
<td nowrap>candidate action selection</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>adaptive TTC + Relative Action Critic</td>
<td nowrap>test-time compute VLA</td>
<td nowrap>LIBERO-LONG</td>
<td nowrap>自适应测试时计算与动作选择</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61157">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61157">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66066">SCALE: Self-uncertainty Conditioned Adaptive Looking and Execution for Vision-Language-Action Models</a></td>
<td nowrap>SCALE 用 VLA 自身不确定性在单次前向中同时调节视觉感知和动作探索/利用。</td>
<td nowrap>generic VLA</td>
<td nowrap>adaptive execution</td>
<td nowrap>VLA / RL/在线微调</td>
<td nowrap>self-uncertainty conditioned adaptive looking/execution</td>
<td nowrap>training-free single-pass inference strategy</td>
<td nowrap>Sim + Real</td>
<td nowrap>训练自由测试时鲁棒执行</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66066">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66066">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64826">XR-1: Towards Versatile Vision-Language-Action Models via Learning Unified Vision-Motion Representations</a></td>
<td nowrap>XR-1 学习统一的视觉-运动编码，用于在异构机器人、任务和演示数据上训练通用 VLA 策略。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64826">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66510">Escaping the Diversity Trap in Robotic Manipulation via Anchor-Centric Adaptation</a></td>
<td nowrap>ACA 证明少量预算下盲目追求示教多样性会带来密度不足，并用锚点重复示教再扩展边界来适配。</td>
<td nowrap>VLA adaptation</td>
<td nowrap>residual updates</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>Anchor-Centric Adaptation</td>
<td nowrap>data-efficient real-robot adaptation</td>
<td nowrap>Real</td>
<td nowrap>低预算本体适配</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66510">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66510">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63997">Embodied Interpretability: Linking Causal Understanding to Generalization in Vision-Language-Action Models</a></td>
<td nowrap>该文用 interventional masking 估计视觉区域对动作预测的因果影响，并用 NMR 预测泛化。</td>
<td nowrap>-</td>
<td nowrap>diagnostic not action representation</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>ISS + NMR</td>
<td nowrap>interpretability/diagnostic</td>
<td nowrap>manipulation tasks</td>
<td nowrap>VLA 因果归因与泛化诊断</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63997">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63997">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2511.04555">Evo-1: Lightweight Vision-Language-Action Model with Preserved Semantic Alignment</a></td>
<td nowrap>Evo-1 面向轻量 VLA，在压缩模型规模时保持语言-视觉语义对齐与操作能力。</td>
<td nowrap>Evo-1</td>
<td nowrap>-</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>-</td>
<td nowrap>lightweight VLA</td>
<td nowrap>-</td>
<td nowrap>轻量化 VLA 语义对齐保持</td>
<td nowrap><a href="https://arxiv.org/abs/2511.04555">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/MINT-SJTU/Evo-1">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2512.09928">HiF-VLA: Hindsight, Insight and Foresight through Motion Representation for Vision-Language-Action Models</a></td>
<td nowrap>HiF-VLA 用运动表征引入 hindsight、insight、foresight 来增强 VLA 对动作过程的理解。</td>
<td nowrap>HiF-VLA</td>
<td nowrap>motion representation</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>hindsight/insight/foresight motion modeling</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>运动表征增强 VLA</td>
<td nowrap><a href="https://arxiv.org/abs/2512.09928">paper</a></td>
<td nowrap><a href="https://hifvla.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2603.12193">SaPaVe: Towards Active Perception and Manipulation in Vision-Language-Action Models for Robotics</a></td>
<td nowrap>SaPaVe 将主动感知与操作结合，让 VLA 在不确定场景中能先看再做。</td>
<td nowrap>SaPaVe</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>active perception + manipulation</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>主动感知驱动操作</td>
<td nowrap><a href="https://arxiv.org/abs/2603.12193">paper</a></td>
<td nowrap><a href="https://lmzpai.github.io/SaPaVe">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2601.12796">Contact-Aware Neural Dynamics</a></td>
<td nowrap>该文学习接触感知神经动力学，用于建模接触丰富操作中的状态变化。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>contact-rich dynamics / 机器人操作</td>
<td nowrap>contact-aware neural dynamics</td>
<td nowrap>dynamics model, not generalist VLA</td>
<td nowrap>-</td>
<td nowrap>接触感知动力学建模</td>
<td nowrap><a href="https://arxiv.org/abs/2601.12796">paper</a></td>
<td nowrap><a href="https://changwei-jing.github.io/neural-physics/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2508.21046">CogVLA: Cognition-Aligned Vision-Language-Action Model via Instruction-Driven Routing &amp; Sparsification</a></td>
<td nowrap>CogVLA 通过指令驱动路由与稀疏化减少 VLA 后训练开销并提升效率。</td>
<td nowrap>CogVLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>instruction-driven routing + sparsification</td>
<td nowrap>efficient VLA</td>
<td nowrap>-</td>
<td nowrap>解决大 VLM-based VLA 后训练和部署计算成本高的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2508.21046">paper</a></td>
<td nowrap><a href="https://jiutian-vl.github.io/CogVLA-page/">project</a></td>
<td nowrap><a href="https://github.com/JiuTian-VL/CogVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.15660">Exploring the Limits of Vision-Language-Action Manipulation in Cross-task Generalization</a></td>
<td nowrap>该文系统评估 VLA 跨任务泛化边界，并提出 AGNOSTOS/X-ICM 相关方法提升泛化。</td>
<td nowrap>AGNOSTOS / X-ICM</td>
<td nowrap>-</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>-</td>
<td nowrap>cross-task generalization study</td>
<td nowrap>-</td>
<td nowrap>跨任务泛化边界评估</td>
<td nowrap><a href="https://arxiv.org/abs/2505.15660">paper</a> / <a href="https://arxiv.org/pdf/2505.15660">paper</a></td>
<td nowrap><a href="https://jiaming-zhou.github.io/AGNOSTOS/">project</a> / <a href="https://jiaming-zhou.github.io/AGNOSTOS">project</a></td>
<td nowrap><a href="https://github.com/jiaming-zhou/X-ICM">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.15517">Robo2VLM: Improving Visual Question Answering using Large-Scale Robot Manipulation Data</a></td>
<td nowrap>Robo2VLM 用大规模机器人操作数据改进 VLM/VQA 对物体状态和可操作性的理解。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>-</td>
<td nowrap>robot-data-enhanced VLM/VQA, not action policy</td>
<td nowrap>-</td>
<td nowrap>机器人操作数据增强视觉问答</td>
<td nowrap><a href="https://arxiv.org/abs/2505.15517">paper</a></td>
<td nowrap><a href="https://berkeleyautomation.github.io/robo2vlm/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.22242">4D-VLA: Spatiotemporal Vision-Language-Action Pretraining with Cross-Scene Calibration</a></td>
<td nowrap>4D-VLA 通过 RGB-D 时序、坐标对齐和 memory bank sampling 缓解跨场景预训练中的状态/坐标混乱。</td>
<td nowrap>4D-VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>4D spatiotemporal pretraining + cross-scene calibration + memory bank sampling</td>
<td nowrap>-</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决多源机器人数据预训练中输入不完整导致动作分布发散的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.22242">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/LogosRoboticsGroup/4D-VLA">code</a></td>
<td nowrap>MV-Bench</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.24194">Blindfolded Experts Generalize Better: Insights from Robotic Manipulation and Videogames</a></td>
<td nowrap>该文研究减少视觉依赖的 expert 为什么在机器人操作和游戏中更能泛化。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>blindfolded expert / reduced observation analysis</td>
<td nowrap>generalization analysis</td>
<td nowrap>-</td>
<td nowrap>视觉依赖与泛化关系</td>
<td nowrap><a href="https://arxiv.org/abs/2510.24194">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/blindfoldedexperts/home">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.11321">HiMaCon: Discovering Hierarchical Manipulation Concepts from Unlabeled Multi-Modal Data</a></td>
<td nowrap>HiMaCon 从无标注多模态数据中发现层级操作概念，用于结构化表示机器人技能。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>hierarchical manipulation concept discovery</td>
<td nowrap>concept representation</td>
<td nowrap>Sim/Benchmark confirmed</td>
<td nowrap>无标注层级操作概念发现</td>
<td nowrap><a href="https://arxiv.org/abs/2510.11321">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.23705">Knowledge Insulating Vision-Language-Action Models: Train Fast, Run Fast, Generalize Better</a></td>
<td nowrap>该文通过知识隔离降低 VLA 训练和推理成本，同时提升泛化。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>knowledge insulation</td>
<td nowrap>efficient/generalist VLA</td>
<td nowrap>-</td>
<td nowrap>快速训练、快速推理和泛化提升</td>
<td nowrap><a href="https://arxiv.org/abs/2505.23705">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=3XuUnUEI7e">Diversifying Parallel Ergodic Search: A Signature Kernel Evolution Strategy</a></td>
<td nowrap>该文用 signature kernel evolution strategy 增强并行 ergodic search 的轨迹多样性和探索效率。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>Signature Kernel Evolution Strategy</td>
<td nowrap>trajectory optimization/search, not VLA</td>
<td nowrap>robotic benchmarks</td>
<td nowrap>多样化并行 ergodic search</td>
<td nowrap><a href="https://openreview.net/forum?id=3XuUnUEI7e">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1325">FedVLA: Federated Vision-Language-Action Learning with Dual Gating Mixture-of-Experts for Robotic Manipulation</a></td>
<td nowrap>FedVLA 用联邦学习和双门控 MoE 在多端机器人数据上训练 VLA。</td>
<td nowrap>FedVLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>federated learning + dual-gating MoE</td>
<td nowrap>federated VLA</td>
<td nowrap>-</td>
<td nowrap>隐私/多客户端 VLA 学习</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1325">paper</a> / <a href="https://arxiv.org/abs/2508.02190">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/225">PASG: A Closed-Loop Framework for Automated Geometric Primitive Extraction and Semantic Anchoring in Robotic Manipulation</a></td>
<td nowrap>PASG 自动抽取几何 primitives 并用 VLM 语义锚定，连接几何 affordance 与任务语义。</td>
<td nowrap>VLM/Qwen2.5VL-PA</td>
<td nowrap>-</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Primitive-Aware Semantic Grounding</td>
<td nowrap>semantic-affordance grounding framework</td>
<td nowrap>benchmark</td>
<td nowrap>几何 primitive 与语义 affordance 锚定</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/225">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>spatial-semantic reasoning benchmark</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.07087">iManip: Skill-Incremental Learning for Robotic Manipulation</a></td>
<td nowrap>iManip 面向机器人操作的技能增量学习，在加入新技能时保持旧技能能力。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>incremental skill learning</td>
<td nowrap>skill-incremental manipulation</td>
<td nowrap>-</td>
<td nowrap>机器人技能增量学习</td>
<td nowrap><a href="https://arxiv.org/abs/2503.07087">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/972">4D Visual Pre-training for Robot Learning</a></td>
<td nowrap>FVP 将视觉预训练设为下一点云预测，用扩散模型提升真实机器人 3D 表征和模仿学习成功率。</td>
<td nowrap>FVP + DP3</td>
<td nowrap>3D policy support</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>next-point-cloud prediction diffusion pretraining</td>
<td nowrap>4D visual pretraining</td>
<td nowrap>Real manipulation</td>
<td nowrap>4D/点云视觉预训练</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/972">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2502.19417">Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models</a></td>
<td nowrap>Hi Robot 用层级 VLA 将开放式指令分解为高层规划和低层动作执行。</td>
<td nowrap>hierarchical VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>hierarchical policy/planning</td>
<td nowrap>open-ended instruction following</td>
<td nowrap>-</td>
<td nowrap>开放式层级指令跟随</td>
<td nowrap><a href="https://arxiv.org/abs/2502.19417">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/pdf/2503.03734">OTTER: A Vision-Language-Action Model with Text-Aware Visual Feature Extraction</a></td>
<td nowrap>OTTER 用文本感知视觉特征抽取让 VLA 更聚焦与语言目标相关的图像信息。</td>
<td nowrap>OTTER</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>text-aware visual feature extraction</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>文本感知视觉特征抽取</td>
<td nowrap><a href="https://arxiv.org/pdf/2503.03734">paper</a></td>
<td nowrap><a href="https://ottervla.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.18867">UP-VLA: A Unified Understanding and Prediction Model for Embodied Agent</a></td>
<td nowrap>UP-VLA 统一理解与预测任务，让 embodied agent 同时具备语义理解和未来/动作预测能力。</td>
<td nowrap>UP-VLA</td>
<td nowrap>-</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>-</td>
<td nowrap>unified understanding-prediction model</td>
<td nowrap>-</td>
<td nowrap>具身理解与预测统一建模</td>
<td nowrap><a href="https://arxiv.org/abs/2501.18867">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/CladernyJorn/UP-VLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18825">ELEMENTAL: Interactive Learning from Demonstrations and Vision-Language Models for Reward Design in Robotics</a></td>
<td nowrap>ELEMENTAL 结合示教交互和 VLM 生成/改进机器人奖励设计。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>interactive learning / reward design</td>
<td nowrap>demonstrations + VLM reward design</td>
<td nowrap>reward learning, not generalist VLA</td>
<td nowrap>-</td>
<td nowrap>交互式奖励设计</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18825">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2410.22391">A Large Recurrent Action Model: xLSTM enables Fast Inference for Robotics Tasks</a></td>
<td nowrap>LRAM 用 xLSTM 替代 Transformer 构建大动作模型，实现更快推理和长序列外推。</td>
<td nowrap>LRAM</td>
<td nowrap>sequence action model</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>xLSTM recurrent action model</td>
<td nowrap>large recurrent action model</td>
<td nowrap>-</td>
<td nowrap>解决 Transformer 大动作模型在机器人实时任务中推理慢的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2410.22391">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/ml-jku/LRAM">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/pdf/2502.13142">Pre-training Auto-regressive Robotic Models with 4D Representations</a></td>
<td nowrap>ARM4R 用 4D 表征预训练自回归机器人模型，增强时空理解与操作泛化。</td>
<td nowrap>ARM4R</td>
<td nowrap>AR</td>
<td nowrap>generalist VLA / 高效/轻量 VLA</td>
<td nowrap>4D representation pretraining</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>4D 表征自回归预训练</td>
<td nowrap><a href="https://arxiv.org/pdf/2502.13142">paper</a></td>
<td nowrap><a href="https://arm4r.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://www.arxiv.org/pdf/2506.03863">STAR: Learning Diverse Robot Skill Abstractions through Rotation-Augmented Vector Quantization</a></td>
<td nowrap>STAR 用旋转增强残差技能量化和因果 skill transformer 学习离散技能抽象与组合。</td>
<td nowrap>-</td>
<td nowrap>discrete skill tokens</td>
<td nowrap>generalist VLA / RL/在线微调</td>
<td nowrap>RaRSQ + causal skill transformer</td>
<td nowrap>skill abstraction</td>
<td nowrap>LIBERO + Real</td>
<td nowrap>解决 VQ 类技能抽象 codebook collapse 和技能因果组合建模不足的问题。</td>
<td nowrap><a href="https://www.arxiv.org/pdf/2506.03863">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/iLearn-Lab/ICML25-STAR">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.10105">UniAct: Universal Actions For Enhanced Embodied Foundation Models</a></td>
<td nowrap>UniAct 提出 universal actions 作为跨任务/跨本体的动作接口以增强具身基础模型。</td>
<td nowrap>UniAct</td>
<td nowrap>universal actions</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>universal action representation</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>通用动作表示</td>
<td nowrap><a href="https://arxiv.org/abs/2501.10105">paper</a></td>
<td nowrap><a href="https://2toinf.github.io/UniAct/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.13446">MoManipVLA: Transferring Vision-language-action Models for General Mobile Manipulation</a></td>
<td nowrap>MoManipVLA 将 VLA 迁移到移动操作场景，面向导航与机械臂协同的通用操作。</td>
<td nowrap>MoManipVLA</td>
<td nowrap>-</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>-</td>
<td nowrap>mobile manipulation VLA transfer</td>
<td nowrap>-</td>
<td nowrap>通用移动操作迁移</td>
<td nowrap><a href="https://arxiv.org/abs/2503.13446">paper</a></td>
<td nowrap><a href="https://gary3410.github.io/momanipVLA/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.06960">A Data-Centric Revisit of Pre-Trained Vision Models for Robot Learning</a></td>
<td nowrap>该文从数据中心角度重新评估预训练视觉模型对机器人学习的作用。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>-</td>
<td nowrap>data-centric robot visual pretraining study</td>
<td nowrap>-</td>
<td nowrap>预训练视觉模型的数据因素评估</td>
<td nowrap><a href="https://arxiv.org/abs/2503.06960">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/CVMI-Lab/SlotMIM">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2504.00420">Think Small, Act Big: Primitive Prompt Learning for Lifelong Robot Manipulation</a></td>
<td nowrap>PPL 通过可复用 primitive prompts 支持机器人终身学习中新技能的持续获取。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>Primitive Prompt Learning</td>
<td nowrap>lifelong robot manipulation</td>
<td nowrap>Sim + Real</td>
<td nowrap>可复用 primitive prompt 的终身学习</td>
<td nowrap><a href="https://arxiv.org/abs/2504.00420">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/32789">Phoenix: A Motion-based Self-Reflection Framework for Fine-grained Robotic Action Correction</a></td>
<td nowrap>Phoenix 用运动指令连接 MLLM 语义反思和低层扩散策略，实现细粒度动作纠错。</td>
<td nowrap>MLLM + motion-conditioned diffusion policy</td>
<td nowrap>Diffusion correction</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>dual-process motion adjustment + motion-conditioned diffusion policy</td>
<td nowrap>self-reflection/action correction</td>
<td nowrap>-</td>
<td nowrap>细粒度机器人动作纠错</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/32789">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2406.14235">Mitigating the Human-Robot Domain Discrepancy in Visual Pre-training for Robotic Manipulation</a></td>
<td nowrap>该文缓解人类视频视觉预训练与机器人操作之间的域差异。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA / 通用 VLA</td>
<td nowrap>human-robot domain discrepancy mitigation</td>
<td nowrap>visual pretraining for manipulation</td>
<td nowrap>-</td>
<td nowrap>人-机器人视觉预训练域差异</td>
<td nowrap><a href="https://arxiv.org/abs/2406.14235">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.02166">CrayonRobo: Object-Centric Prompt-Driven Vision-Language-Action Model for Robotic Manipulation</a></td>
<td nowrap>CrayonRobo 用叠加在图像上的对象中心 2D 视觉提示表达接触位姿和运动方向，指导长程操作。</td>
<td nowrap>-</td>
<td nowrap>SE(3) contact pose + motion direction</td>
<td nowrap>VLA / 高效/轻量 VLA</td>
<td nowrap>object-centric visual-language prompts</td>
<td nowrap>-</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决语言目标歧义、图像/视频目标过细且难表达动作约束的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.02166">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/clorislili/CrayonRobo">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/html/2505.00693">Robotic Visual Instruction</a></td>
<td nowrap>RoVI/VIEW 用手绘对象中心 2D 符号指令表达空间时序约束并转成 3D 操作动作。</td>
<td nowrap>VIEW pipeline with VLMs</td>
<td nowrap>3D action sequences</td>
<td nowrap>VLA / RL/在线微调</td>
<td nowrap>Robotic Visual Instruction + Visual Instruction Embodied Workflow</td>
<td nowrap>-</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决自然语言机器人指令空间精度不足、公共场景语音不便的问题。</td>
<td nowrap><a href="https://arxiv.org/html/2505.00693">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>open-source RoVI dataset</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.17662">RoboPEPP: Vision-Based Robot Pose and Joint Angle Estimation through Embedding Predictive Pre-Training</a></td>
<td nowrap>RoboPEPP 用 embedding predictive pre-training 从视觉估计机器人姿态和关节角。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>embedding predictive pre-training</td>
<td nowrap>robot pose/joint estimation pretraining, not generalist VLA</td>
<td nowrap>-</td>
<td nowrap>视觉机器人姿态与关节估计</td>
<td nowrap><a href="https://arxiv.org/abs/2411.17662">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2504.06961">Two by Two: Learning Multi-Task Pairwise Objects Assembly for Generalizable Robot Manipulation</a></td>
<td nowrap>2BY2 构建日常成对物体装配数据集，并用两步 SE(3) 位姿估计完成多任务装配。</td>
<td nowrap>-</td>
<td nowrap>SE(3) pose</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>two-step SE(3) pose estimation with equivariant features</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决现有装配数据集偏几何碎片/工业零件、不能覆盖日常对象功能关系的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2504.06961">paper</a></td>
<td nowrap><a href="https://tea-lab.github.io/TwoByTwo/">project</a></td>
<td nowrap><a href="https://github.com/TEA-Lab/TwoByTWo">code</a></td>
<td nowrap>2BY2 dataset</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11269">Prof. Robot: Differentiable Robot Rendering Without Static and Self-Collisions</a></td>
<td nowrap>Prof. Robot 提供避免静态和自碰撞的可微机器人渲染，用于机器人视觉/几何学习。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>generalist VLA / 通用 VLA</td>
<td nowrap>collision-free differentiable robot rendering</td>
<td nowrap>differentiable rendering/tooling, not VLA</td>
<td nowrap>-</td>
<td nowrap>可微机器人渲染</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11269">paper</a></td>
<td nowrap><a href="https://www.qrcat.cn/prof-robot/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### action representation

共 21 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>Base VLA</th>
<th nowrap>Action</th>
<th nowrap>训练/反馈</th>
<th nowrap>Algorithm</th>
<th nowrap>Policy/Type</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2310.08576">Learning to Act from Actionless Videos through Dense Correspondences</a></td>
<td nowrap>This work learns action representations from actionless videos using dense visual correspondences.</td>
<td nowrap>video pretraining</td>
<td nowrap>latent action</td>
<td nowrap>action representation / pretraining</td>
<td nowrap>dense correspondence learning</td>
<td nowrap>video-to-action representation</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Recover reusable action structure without action labels.</td>
<td nowrap><a href="https://arxiv.org/abs/2310.08576">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2402.07872">PIVOT: Iterative Visual Prompting Elicits Actionable Knowledge for VLMs</a></td>
<td nowrap>PIVOT elicits spatial and actionable knowledge from VLMs through iterative visual prompting.</td>
<td nowrap>VLM</td>
<td nowrap>actionable visual prompt</td>
<td nowrap>action representation / affordance</td>
<td nowrap>iterative visual prompting</td>
<td nowrap>VLM affordance reasoning</td>
<td nowrap>spatial action benchmarks</td>
<td nowrap>Extract actionable spatial knowledge from VLMs.</td>
<td nowrap><a href="https://arxiv.org/abs/2402.07872">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=y5CaJb17Fn">villa-X: Enhancing Latent Action Modeling in Vision-Language-Action Models</a></td>
<td nowrap>villa-X 学习并使用 latent actions 作为 VLA 预训练中的运动抽象，可零样本生成 latent action plans。</td>
<td nowrap>ViLLA/villa-X</td>
<td nowrap>latent action</td>
<td nowrap>action representation / 动作表示/tokenization</td>
<td nowrap>latent action modeling for VLA pretraining</td>
<td nowrap>Vision-Language-Latent-Action</td>
<td nowrap>SIMPLER + two real setups</td>
<td nowrap>latent action 预训练</td>
<td nowrap><a href="https://openreview.net/forum?id=y5CaJb17Fn">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2410.11758">Latent Action Pretraining from Videos</a></td>
<td nowrap>LAPA 先从视频中学习潜在动作抽象，再迁移到机器人动作生成。</td>
<td nowrap>LAPA</td>
<td nowrap>latent action</td>
<td nowrap>action representation / pretraining</td>
<td nowrap>latent action pretraining</td>
<td nowrap>video-to-action representation</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>从视频中学习可复用 latent action，用于下游 VLA 策略。</td>
<td nowrap><a href="https://arxiv.org/abs/2410.11758">paper</a></td>
<td nowrap><a href="https://latentactionpretraining.github.io/">project</a></td>
<td nowrap><a href="https://github.com/LatentActionPretraining/LAPA">code</a></td>
<td nowrap><a href="https://huggingface.co/latent-action-pretraining/LAPA-7B-openx">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=IZHk6BXBST">Rodrigues Network for Learning Robot Actions</a></td>
<td nowrap>RodriNet 将可学习 Neural Rodrigues Operator 作为运动学结构先验注入动作网络。</td>
<td nowrap>-</td>
<td nowrap>kinematics-aware action representation</td>
<td nowrap>action representation / 动作表示/tokenization</td>
<td nowrap>Neural Rodrigues Operator + RodriNet</td>
<td nowrap>action network architecture</td>
<td nowrap>synthetic + imitation benchmarks + hand reconstruction</td>
<td nowrap>机器人动作的运动学结构建模</td>
<td nowrap><a href="https://openreview.net/forum?id=IZHk6BXBST">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38937">Actor-Critic for Continuous Action Chunks: A Reinforcement Learning Framework for Long-Horizon Robotic Manipulation with Sparse Reward</a></td>
<td nowrap>AC3 用 actor-critic 直接学习连续 action chunks，并用成功轨迹非对称更新和 chunk 内 n-step return 稳定训练。</td>
<td nowrap>-</td>
<td nowrap>continuous action chunks</td>
<td nowrap>RL / sparse reward</td>
<td nowrap>AC3</td>
<td nowrap>actor-critic chunk policy</td>
<td nowrap>BiGym + RLBench</td>
<td nowrap>稀疏奖励长程连续动作块学习</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38937">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60681">DyGRO-VLA: Cross-Task Scaling of Vision-Language-Action Models via Dynamic Grouped Residual Optimization</a></td>
<td nowrap>DyGRO-VLA 先学习跨任务潜在表征，再用动态分组 RL residual 优化多任务 VLA。</td>
<td nowrap>DyGRO-VLA</td>
<td nowrap>residual policy optimization</td>
<td nowrap>RL/在线微调</td>
<td nowrap>Dynamic Grouped Residual Optimization</td>
<td nowrap>cross-task RL-optimized VLA</td>
<td nowrap>LIBERO/RoboTwin2 + Real</td>
<td nowrap>跨任务 VLA RL 优化</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60681">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60681">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61232">LARA: Latent Action Representation Alignment for Vision-Language-Action Models</a></td>
<td nowrap>LARA 联合优化 latent action model 与 VLA，使人类视频 latent action 更好对齐真实动作轨迹。</td>
<td nowrap>LARA plug-in</td>
<td nowrap>latent action representation</td>
<td nowrap>VLA / 动作表示/tokenization</td>
<td nowrap>LAM-VLA representation alignment</td>
<td nowrap>pre/post-training enhancement</td>
<td nowrap>3 sim + 1 real benchmark</td>
<td nowrap>latent action 对齐</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61232">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61232">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62908">From Noise to Intent: Anchoring Generative VLA Policies with Residual Bridges</a></td>
<td nowrap>ResVLA 将生成动作从“噪声生成”改为“意图锚定后残差细化”，分离低频意图与高频局部动力学。</td>
<td nowrap>ResVLA</td>
<td nowrap>Diffusion / residual bridge</td>
<td nowrap>VLA / 动作表示/tokenization</td>
<td nowrap>low-frequency intent anchor + high-frequency residual diffusion bridge</td>
<td nowrap>generative VLA policy</td>
<td nowrap>LIBERO/LIBERO-Plus</td>
<td nowrap>生成式动作解码稳定性</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62908">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62908">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65967">Demystifying Action Space Design for Robotic Manipulation Policies</a></td>
<td nowrap>该文用 13k+ 真实 rollout 和 500+ 模型系统分析绝对/增量、关节/任务空间动作设计的影响。</td>
<td nowrap>-</td>
<td nowrap>delta actions preferred</td>
<td nowrap>action representation / 动作表示/tokenization</td>
<td nowrap>large-scale action-space empirical study</td>
<td nowrap>action-space design study</td>
<td nowrap>Real bimanual robot</td>
<td nowrap>动作空间设计准则</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65967">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65967">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66520">FocalPolicy: Frequency-Optimized Chunking and Locally Anchored Flow Matching for Coherent Visuomotor Policy</a></td>
<td nowrap>FocalPolicy 用频域优化 chunking 和局部锚定 flow matching 提升长程动作块之间的连贯性。</td>
<td nowrap>visuomotor policy</td>
<td nowrap>Diffusion / Flow action chunks</td>
<td nowrap>flow matching / diffusion/flow policy</td>
<td nowrap>Frequency-Optimized Chunking + Locally Anchored Flow Matching</td>
<td nowrap>flow-matching visuomotor policy</td>
<td nowrap>-</td>
<td nowrap>跨 action chunk 连贯性</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66520">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66520">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62176">GeoMoLa: Geometry-Aware Motion Latents for Learning Robust Manipulation Policies</a></td>
<td nowrap>GeoMoLa 通过预测点云随操作的 4D 几何变化来学习离散 motion latent codes。</td>
<td nowrap>GeoMoLa</td>
<td nowrap>discrete motion latent codes</td>
<td nowrap>action representation / 动作表示/tokenization</td>
<td nowrap>geometry-aware point-cloud evolution objective</td>
<td nowrap>motion latent policy</td>
<td nowrap>benchmarks + Real</td>
<td nowrap>几何感知动作潜变量</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62176">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62176">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2604.04161">Adaptive Action Chunking at Inference-time for Vision-Language-Action Models</a></td>
<td nowrap>AAC 用 action entropy 在推理时动态选择动作块长度，平衡反应性和连续性。</td>
<td nowrap>generic VLA</td>
<td nowrap>adaptive action chunks</td>
<td nowrap>VLA / 动作表示/tokenization</td>
<td nowrap>action entropy based AAC</td>
<td nowrap>inference-time adaptation</td>
<td nowrap>Sim + Real</td>
<td nowrap>推理时自适应 action chunking</td>
<td nowrap><a href="https://arxiv.org/abs/2604.04161">paper</a></td>
<td nowrap><a href="https://lance-lot.github.io/adaptive-chunking.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2603.10158">Cross-Hand Latent Representation for Vision-Language-Action Models</a></td>
<td nowrap>XL-VLA/DexLatent 学习跨不同灵巧手的潜在表示，使单一策略可迁移到多种手型。</td>
<td nowrap>XL-VLA / DexLatent</td>
<td nowrap>cross-hand latent representation</td>
<td nowrap>VLA / 动作表示/tokenization</td>
<td nowrap>DexLatent</td>
<td nowrap>cross-embodiment dexterous VLA</td>
<td nowrap>-</td>
<td nowrap>解决多指灵巧手之间动作空间不同、策略难跨手迁移的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2603.10158">paper</a></td>
<td nowrap><a href="https://xl-vla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/EmptyBlueBox/DexLatent">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.16685">Compliant Residual DAgger: Improving Real-World Contact-Rich Manipulation with Human Corrections</a></td>
<td nowrap>CR-DAgger 用柔顺干预接口和力反馈残差策略，从人类 delta 修正中改进接触丰富操作。</td>
<td nowrap>-</td>
<td nowrap>delta action corrections / residual policy</td>
<td nowrap>DAgger / human corrections</td>
<td nowrap>Compliant Residual DAgger</td>
<td nowrap>human-in-the-loop residual policy</td>
<td nowrap>Real</td>
<td nowrap>解决真实接触操作中 DAgger 修正数据难采、策略更新难稳定的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.16685">paper</a></td>
<td nowrap><a href="https://compliant-residual-dagger.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.25138">Learning Spatial-Aware Manipulation Ordering</a></td>
<td nowrap>OrderMind 从空间上下文直接学习 cluttered scene 中各物体的操作优先级。</td>
<td nowrap>OrderMind</td>
<td nowrap>manipulation order priorities</td>
<td nowrap>VLA / 动作表示/tokenization</td>
<td nowrap>spatial graph encoder + temporal priority structuring</td>
<td nowrap>ordering policy</td>
<td nowrap>benchmark + Real</td>
<td nowrap>解决杂乱环境中错误操作顺序导致碰撞或遮挡的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.25138">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/yyxssm/OrderMind">code</a></td>
<td nowrap>Manipulation Ordering Benchmark</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.15607">PRIMT: Preference-based Reinforcement Learning with Multimodal Feedback and Trajectory Synthesis from Foundation Models</a></td>
<td nowrap>PRIMT 用 LLM/VLM 多模态合成偏好反馈和轨迹合成来减少 PbRL 对人工反馈的依赖。</td>
<td nowrap>-</td>
<td nowrap>RL policy actions</td>
<td nowrap>preference-based RL / multimodal synthetic feedback</td>
<td nowrap>PRIMT + neuro-symbolic fusion + trajectory synthesis</td>
<td nowrap>PbRL framework</td>
<td nowrap>2 locomotion + 6 manipulation benchmarks</td>
<td nowrap>解决偏好 RL 中人工反馈多、查询歧义和 credit assignment 难的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.15607">paper</a></td>
<td nowrap><a href="https://primt25.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2502.01218">Provable Ordering and Continuity in Vision-Language Pretraining for Generalizable Embodied Agents</a></td>
<td nowrap>AcTOL 用帧间语义排序和局部 Brownian bridge 连续性约束学习有序连续的视觉语言表征。</td>
<td nowrap>AcTOL features</td>
<td nowrap>pretraining representation</td>
<td nowrap>VLA / 动作表示/tokenization</td>
<td nowrap>Action Temporal Coherence Learning</td>
<td nowrap>VL pretraining for embodied agents</td>
<td nowrap>-</td>
<td nowrap>有序连续视觉语言预训练</td>
<td nowrap><a href="https://arxiv.org/abs/2502.01218">paper</a></td>
<td nowrap><a href="https://actol-pretrain.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2508.05941">Latent Policy Barrier: Learning Robust Visuomotor Policies by Staying In-Distribution</a></td>
<td nowrap>LPB 将专家示教 latent embedding 作为隐式安全边界，推理时优化未来 latent 保持在专家分布内。</td>
<td nowrap>LPB</td>
<td nowrap>Diffusion policy + latent barrier correction</td>
<td nowrap>action representation / 动作表示/tokenization</td>
<td nowrap>Latent Policy Barrier + dynamics model</td>
<td nowrap>robust visuomotor policy</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决行为克隆 visuomotor policy 因协变量偏移而逐步偏离专家轨迹的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2508.05941">paper</a></td>
<td nowrap><a href="https://project-latentpolicybarrier.github.io/">project</a></td>
<td nowrap><a href="https://github.com/zhanyisun/lpb">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04445">Moto: Latent Motion Token as the Bridging Language for Robot Manipulation</a></td>
<td nowrap>Moto 将视频转为 latent motion tokens，并用 Moto-GPT 自回归预训练把视频运动知识迁移到机器人控制。</td>
<td nowrap>Moto-GPT</td>
<td nowrap>latent motion tokens</td>
<td nowrap>VLA / action tokenization / 动作表示/tokenization</td>
<td nowrap>Latent Motion Tokenizer + Moto-GPT autoregression</td>
<td nowrap>video-pretrained motion-token policy</td>
<td nowrap>-</td>
<td nowrap>解决机器人缺少动作标注数据而视频数据中运动知识难直接利用的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04445">paper</a></td>
<td nowrap><a href="https://chenyi99.github.io/moto/">project</a></td>
<td nowrap><a href="https://github.com/TencentARC/Moto">code</a></td>
<td nowrap><a href="https://huggingface.co/TencentARC/Moto">hf</a></td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.14519">Tra-MoE: Learning Trajectory Prediction Model from Multiple Domains for Adaptive Policy Conditioning</a></td>
<td nowrap>Tra-MoE 从多域轨迹学习 MoE 预测模型，用预测轨迹自适应调节策略条件。</td>
<td nowrap>Tra-MoE</td>
<td nowrap>trajectory prediction / policy conditioning</td>
<td nowrap>action representation / 动作表示/tokenization</td>
<td nowrap>Mixture-of-Experts trajectory model</td>
<td nowrap>adaptive policy conditioning</td>
<td nowrap>-</td>
<td nowrap>多域轨迹预测与策略条件化</td>
<td nowrap><a href="https://arxiv.org/abs/2411.14519">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/MCG-NJU/Tra-MoE">code</a></td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### diffusion/flow policy

共 68 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>Base VLA</th>
<th nowrap>Action</th>
<th nowrap>训练/反馈</th>
<th nowrap>Algorithm</th>
<th nowrap>Policy/Type</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://diffusion-vla.github.io/">DiffusionVLA: Scaling Robot Foundation Models via Unified Diffusion and Autoregression</a></td>
<td nowrap>DiffusionVLA scales robot foundation models with unified diffusion and autoregressive generation.</td>
<td nowrap>DiffusionVLA</td>
<td nowrap>diffusion + AR action</td>
<td nowrap>VLA / diffusion-flow policy</td>
<td nowrap>unified diffusion and autoregression</td>
<td nowrap>robot foundation model</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Scale VLA policy learning with diffusion and autoregressive modeling.</td>
<td nowrap><a href="https://diffusion-vla.github.io/">paper</a></td>
<td nowrap><a href="https://diffusion-vla.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=nDmwloEl3N">Efficient Diffusion Transformer Policies with Mixture of Expert Denoisers for Multitask Learning</a></td>
<td nowrap>This work uses mixture-of-expert denoisers to make diffusion transformer policies more efficient across tasks.</td>
<td nowrap>diffusion transformer policy</td>
<td nowrap>continuous action</td>
<td nowrap>VLA / diffusion-flow policy</td>
<td nowrap>MoE denoisers</td>
<td nowrap>multitask diffusion policy</td>
<td nowrap>robot manipulation tasks</td>
<td nowrap>Improve multitask diffusion policy efficiency.</td>
<td nowrap><a href="https://openreview.net/forum?id=nDmwloEl3N">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2025</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/33617">FlowPolicy: Enabling Fast and Robust 3D Flow-Based Policy via Consistency Flow Matching for Robot Manipulation</a></td>
<td nowrap>FlowPolicy applies consistency flow matching to fast and robust 3D robot manipulation policies.</td>
<td nowrap>3D flow policy</td>
<td nowrap>continuous 3D action</td>
<td nowrap>VLA / diffusion-flow policy</td>
<td nowrap>consistency flow matching</td>
<td nowrap>fast 3D manipulation policy</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Build faster flow-based 3D manipulation policies.</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04987">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=asS4W7Yw5e">GauDP: Reinventing Multi-Agent Collaboration through Gaussian-Image Synergy in Diffusion Policies</a></td>
<td nowrap>GauDP uses Gaussian-image synergy inside diffusion policies for multi-agent collaboration.</td>
<td nowrap>diffusion policy</td>
<td nowrap>continuous action</td>
<td nowrap>VLA / diffusion-flow policy</td>
<td nowrap>Gaussian-image synergy</td>
<td nowrap>multi-agent diffusion policy</td>
<td nowrap>multi-agent manipulation tasks</td>
<td nowrap>Improve collaboration through diffusion policy representation.</td>
<td nowrap><a href="https://arxiv.org/pdf/2511.00998">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Ma_Hierarchical_Diffusion_Policy_for_Kinematics-Aware_Multi-Task_Robotic_Manipulation_CVPR_2024_paper.html">Hierarchical Diffusion Policy for Kinematics-Aware Multi-Task Robotic Manipulation</a></td>
<td nowrap>HDP combines hierarchy and kinematic awareness for multitask robotic manipulation with diffusion policies.</td>
<td nowrap>diffusion policy</td>
<td nowrap>continuous action</td>
<td nowrap>VLA / diffusion-flow policy</td>
<td nowrap>hierarchical kinematics-aware diffusion</td>
<td nowrap>multitask robot policy</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Make diffusion policies kinematics-aware for multitask manipulation.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Ma_Hierarchical_Diffusion_Policy_for_Kinematics-Aware_Multi-Task_Robotic_Manipulation_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=H1KDMNOKQn">HybridVLA: Collaborative Diffusion and Autoregression in a Unified Vision-Language-Action Model</a></td>
<td nowrap>HybridVLA 在一个 VLA 主干中结合自回归 token 预测和扩散去噪，以改进连续机器人动作生成。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=H1KDMNOKQn">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=UvQOcw2oCD">Unified Diffusion VLA: Vision-Language-Action Model via Joint Discrete Denosing Diffusion Process</a></td>
<td nowrap>Unified Diffusion VLA 联合去噪未来视觉 token 和动作 token，使生成与控制相互增强。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=UvQOcw2oCD">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=1vXMfIYFZp">Master Skill Learning with Policy-Grounded Synergy of LLM-based Reward Shaping and Exploring</a></td>
<td nowrap>提出 Master Skill Learning，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>RL / offline RL</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=1vXMfIYFZp">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=2RIqqNqALN">When would Vision-Proprioception Policies Fail in Robotic Manipulation?</a></td>
<td nowrap>该研究分析视觉-本体感觉策略在机器人操作中何时过度依赖本体感觉而未能利用视觉线索。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=2RIqqNqALN">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=AmczI1k3Yk">Capturing Visual Environment Structure Correlates with Control Performance</a></td>
<td nowrap>提出 Capturing Visual Environment Structure Correlates，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=AmczI1k3Yk">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=BTe5VLBjPg">VITA: Vision-to-Action Flow Matching Policy</a></td>
<td nowrap>VITA 使用从视觉表征到动作潜变量的流匹配，降低视觉运动策略生成中的条件建模开销。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Flow matching policy</td>
<td nowrap>Flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=BTe5VLBjPg">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=BvirMuKWV1">When a Robot is More Capable than a Human: Learning from Constrained Demonstrators</a></td>
<td nowrap>该工作通过建模示教者受限的动作接口，学习能够超越受限示范的机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=BvirMuKWV1">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=FqDmvMZish">Autonomous Functional Play with Correspondence-Driven Trajectory Warping</a></td>
<td nowrap>提出 Autonomous Functional Play，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>3D keypoint grounding</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=FqDmvMZish">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=IaGf8Eh5Uo">Reference Grounded Skill Discovery</a></td>
<td nowrap>Reference Grounded Skill Discovery 使用参考运动表征引导高维智能体的无监督技能学习。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=IaGf8Eh5Uo">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=KFu4p3pd11">Masked Generative Policy for Robotic Control</a></td>
<td nowrap>Masked Generative Policy 将动作 token 化，并用掩码 Transformer 细化实现快速连贯的视觉运动控制。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=KFu4p3pd11">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=OeDwYtp8n1">Learning Video Generation for Robotic Manipulation with Collaborative Trajectory Control</a></td>
<td nowrap>提出 Learning Video Generation for Robotic Manipulation，利用视频生成/预测或未来渲染学习机器人交互动态。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=OeDwYtp8n1">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=P9PVdWyM3U">Policy Contrastive Decoding for Robotic Foundation Models</a></td>
<td nowrap>Policy Contrastive Decoding 通过对比原始观测与目标遮挡观测下的动作分布，在推理时引导机器人基础模型。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=P9PVdWyM3U">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=PL0tJOfm7I">Demystifying Robot Diffusion Policies: Action Memorization and a Simple Lookup Table Alternative</a></td>
<td nowrap>该分析认为扩散策略在稀疏模仿学习场景中常表现得像有效的动作查找表。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=PL0tJOfm7I">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Q1CP0iAmOb">H$^3$DP: Triply‑Hierarchical Diffusion Policy for Visuomotor Learning</a></td>
<td nowrap>H^3DP 将深度感知输入、多尺度视觉特征和分层动作去噪结合起来，用于视觉运动扩散策略。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>5 simulation benchmarks + real Galaxea R1</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=Q1CP0iAmOb">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=TnLFRhLuZ6">Compose Your Policies! Improving Diffusion-based or Flow-based Robot Policies via Test-time Distribution-level Composition</a></td>
<td nowrap>该方法在测试时组合扩散或流策略的分布，无需额外训练即可改进行为表现。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>GPC; test-time distribution-level policy composition</td>
<td nowrap>Flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=TnLFRhLuZ6">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=VSWjHIveqZ">Abstracting Robot Manipulation Skills via Mixture-of-Experts Diffusion Policies</a></td>
<td nowrap>该工作使用混合专家扩散策略学习可复用技能基，并将动作路由到与任务相关的专家。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=VSWjHIveqZ">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=WVliGyFwZv">Accelerated co-design of robots through morphological pretraining</a></td>
<td nowrap>提出 Accelerated co-design of robots through morphological pretraining，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>RL / offline RL</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=WVliGyFwZv">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=aoorNQFpM6">VER: Vision Expert Transformer for Robot Learning via Foundation Distillation and Dynamic Routing</a></td>
<td nowrap>VER 提供端到端机器人学习的开源工具、数据格式或基准接口。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=aoorNQFpM6">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=d08yOXs1Dl">SpikePingpong: Spike Vision-based Fast-Slow Pingpong Robot System</a></td>
<td nowrap>SpikePingpong 结合基于事件的快速视觉和较慢控制推理，实现高速机器人乒乓行为。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=d08yOXs1Dl">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=dQ6d5bgXtM">Translating Flow to Policy via Hindsight Online Imitation</a></td>
<td nowrap>该方法通过将在线 rollout 的达成结果重标注为 hindsight 目标来改进低层策略。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy / RL/在线微调</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=dQ6d5bgXtM">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=eWe8zqGvs5">Cortical Policy: A Dual-Stream View Transformer for Robotic Manipulation</a></td>
<td nowrap>提出 Cortical Policy，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>3D keypoint grounding</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=eWe8zqGvs5">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=iKJbmx1iuQ">Contractive Diffusion Policies</a></td>
<td nowrap>Contractive Diffusion Policies 通过正则化扩散采样动力学，使连续控制中的动作生成更稳定。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=iKJbmx1iuQ">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=kIYNtxE13h">Scalable Exploration for High-Dimensional Continuous Control via Value-Guided Flow</a></td>
<td nowrap>提出 Scalable Exploration for High-Dimensional Continuous Control，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>RL / offline RL</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=kIYNtxE13h">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=w3Ik8HUyTT">ViPRA: Video Prediction for Robot Actions</a></td>
<td nowrap>提出 ViPRA，利用视频生成/预测或未来渲染学习机器人交互动态。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Generative action modeling</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=w3Ik8HUyTT">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=AcTsKglDdh">DataMIL: Selecting Data for Robot Imitation Learning with Datamodels</a></td>
<td nowrap>DataMIL 提供端到端机器人学习的开源工具、数据格式或基准接口。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=AcTsKglDdh">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=COrUdVuInH">MIMIC: Mask-Injected Manipulation Video Generation with Interaction Control</a></td>
<td nowrap>提出 MIMIC，利用视频生成/预测或未来渲染学习机器人交互动态。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=COrUdVuInH">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=CiZMMAFQR3">LeRobot: An Open-Source Library for End-to-End Robot Learning</a></td>
<td nowrap>LeRobot 提供端到端机器人学习的开源工具、数据格式或基准接口。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>simulation + real hardware</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=CiZMMAFQR3">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38881">ManiLong-Shot: Interaction-Aware One-Shot Imitation Learning for Long-Horizon Manipulation</a></td>
<td nowrap>ManiLong-Shot 将长时程一次示教操作分解为交互感知原语，并从示范中迁移执行。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38881">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38889">Learning Diffusion Policy from Primitive Skills for Robot Manipulation</a></td>
<td nowrap>该工作用可解释的原始技能条件化扩散策略，以对齐操作中的短时程动作生成。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38889">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38912">Intention-Aware Diffusion Model for Pedestrian Trajectory Prediction</a></td>
<td nowrap>该模型将短期和长期行人意图注入基于扩散的轨迹预测。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38912">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38919">MP1: MeanFlow Tames Policy Learning in 1-step for Robotic Manipulation</a></td>
<td nowrap>MP1 将 MeanFlow 用于点云操作策略，在一次网络评估中生成动作轨迹。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Flow matching policy</td>
<td nowrap>Flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38919">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38934">ForeDiffusion: Foresight-Conditioned Diffusion Policy via Future View Construction for Robot Manipulation</a></td>
<td nowrap>ForeDiffusion 用预测的未来视角条件化扩散策略，以减少操作中的误差累积。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38934">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38944">Balancing Signal and Variance: Adaptive Offline RL Post-Training for VLA Flow Models</a></td>
<td nowrap>提出 Balancing Signal and Variance，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>π₀</td>
<td nowrap>Flow</td>
<td nowrap>diffusion/flow policy / RL/在线微调 / Reward D</td>
<td nowrap>ARFM</td>
<td nowrap>Off-Policy / MF</td>
<td nowrap>Sim ✓ / Real ✓</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38944">paper</a> / <a href="https://arxiv.org/pdf/2509.04063">paper</a> / <a href="https://arxiv.org/abs/2509.04063">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38950">Bridging Scale Discrepancies in Robotic Control via Language-Based Action Representations</a></td>
<td nowrap>该工作将机器人动作转换为基于语言的表示，以降低任务和平台之间的尺度不匹配。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38950">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38959">D²PPO: Diffusion Policy Policy Optimization with Dispersive Loss</a></td>
<td nowrap>D2PPO 在扩散策略优化中加入分散损失正则，以防止操作学习中的表征坍缩。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>PPO</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38959">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62902">Discrete Diffusion VLA: Bringing Discrete Diffusion to Action Decoding in Vision-Language-Action Policies</a></td>
<td nowrap>Discrete Diffusion VLA 用主干内离散扩散建模离散化动作块，实现并行且可纠错的 VLA 动作解码。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>VLA / diffusion policy / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62902">paper</a> / <a href="https://arxiv.org/abs/2508.20072">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61717">STEP: Warm-Started Visuomotor Policies with Spatiotemporal Consistency Prediction</a></td>
<td nowrap>STEP 用时空一致的动作对扩散策略进行 warm start，以降低闭环推理延迟。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61717">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61049">Learning Human-Robot Collaboration via Heterogeneous-Agent Lyapunov Policy Optimization</a></td>
<td nowrap>HALyPO 通过 Lyapunov 式分歧控制稳定异构人机多智能体策略优化。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>Sim/Benchmark</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61049">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2511.15605">SRPO: Self-Referential Policy Optimization for Vision-Language-Action Models</a></td>
<td nowrap>提出 SRPO，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>OpenVLA* / π₀ / π₀-Fast</td>
<td nowrap>AR / Flow</td>
<td nowrap>VLA / RL/在线微调 / Reward D</td>
<td nowrap>SRPO</td>
<td nowrap>Hybrid / MF (MB-Reward but MF-RL)</td>
<td nowrap>Sim ✓(MT) / Real ✓(MT)</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2511.15605">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.01961">AC-DiT: Adaptive Coordination Diffusion Transformer for Mobile Manipulation</a></td>
<td nowrap>提出 AC-DiT，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>VLA / diffusion policy / diffusion transformer / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2507.01961">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.20406">PointMapPolicy: Structured Point Cloud Processing for Multi-Modal Imitation Learning</a></td>
<td nowrap>提出 PointMapPolicy，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>VLA / diffusion/flow policy</td>
<td nowrap>PPO</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2510.20406">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.00117">Emerging Risks from Embodied AI Require Urgent Policy Action</a></td>
<td nowrap>该政策分析梳理具身 AI 的物理、监控和社会风险，并呼吁针对性治理。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.07127">Human-assisted Robotic Policy Refinement via Action Preference Optimization</a></td>
<td nowrap>提出 Human-assisted Robotic Policy Refinement，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Preference optimization</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2506.07127">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2512.00085">Hyper-GoalNet: Goal-Conditioned Manipulation Policy Learning with HyperNetworks</a></td>
<td nowrap>Hyper-GoalNet 使用超网络根据目标描述生成目标特定的操作策略参数。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2512.00085">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.22094">ReinFlow: Fine-tuning Flow Matching Policy with Online Reinforcement Learning</a></td>
<td nowrap>提出 ReinFlow，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR / Flow</td>
<td nowrap>flow matching / RL / RL/在线微调</td>
<td nowrap>Flow matching policy</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2505.22094">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.13431">A Practical Guide for Incorporating Symmetry in Diffusion Policy</a></td>
<td nowrap>该指南评估在无需完整等变架构的情况下向扩散策略加入对称先验的轻量方法。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion policy / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2505.13431">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.25822">Act to See, See to Act: Diffusion-Driven Perception-Action Interplay for Adaptive Policies</a></td>
<td nowrap>DP-AG 用动作引导的扩散动力学建模感知-动作反馈，以获得更自适应的模仿策略。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion policy / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2509.25822">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2511.20906">DASIP: Dynamic Test-Time Compute Scaling for Robot Control with Stochastic Interpolant Policies</a></td>
<td nowrap>DASIP 根据估计的操作难度，在测试时调整随机插值策略的计算量。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>Flow matching policy</td>
<td nowrap>Flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2511.20906">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.13922">DynaGuide: Steering Diffusion Polices with Active Dynamic Guidance</a></td>
<td nowrap>提出 DynaGuide，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion policy / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2506.13922">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.19757">Dita: Scaling Diffusion Transformer for Generalist Vision-Language-Action Policy</a></td>
<td nowrap>Dita 扩展扩散 Transformer，在通用 VLA 策略内部去噪连续动作序列。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>VLA / diffusion policy / diffusion transformer / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>LIBERO + SimplerEnv + real Franka</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2503.19757">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1571">SD2Actor: Continuous State Decomposition via Diffusion Embeddings for Robotic Manipulation</a></td>
<td nowrap>SD2Actor 用扩散嵌入分解物体状态，以生成零样本连续操作动作。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>VLA / diffusion policy / diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1571">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.06224">EC-Flow: Enabling Versatile Robotic Manipulation from Action-Unlabeled Videos via Embodiment-Centric Flow</a></td>
<td nowrap>EC-Flow 提供端到端机器人学习的开源工具、数据格式或基准接口。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>flow matching / diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>Sim/Benchmark</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2507.06224">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.13217">Dense Policy: Bidirectional Autoregressive Learning of Actions</a></td>
<td nowrap>提出 Dense Policy，用动作 token、掩码生成或自回归建模改进机器人控制。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>autoregressive policy / diffusion/flow policy</td>
<td nowrap>Generative action modeling</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决机器人动作表示和长时序动作预测的效率与一致性问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.13217">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.06710">Spatial-Temporal Aware Visuomotor Diffusion Policy Learning</a></td>
<td nowrap>提出 Spatial-Temporal Aware Visuomotor Diffusion Policy Learning，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion policy / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2507.06710">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.04331">Wavelet Policy: Lifting Scheme for Policy Learning in Long-Horizon Tasks</a></td>
<td nowrap>Wavelet Policy 使用可学习的多尺度小波变换改进长时程策略学习。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2507.04331">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/pdf/2502.01800">Flow-based Domain Randomization for Learning and Sequencing Robotic Skills</a></td>
<td nowrap>提出 Flow-based Domain Randomization，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>flow matching / diffusion/flow policy</td>
<td nowrap>Flow matching policy</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/pdf/2502.01800">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.01885">Learning Policy Committees for Effective Personalization in MDPs with Diverse Tasks</a></td>
<td nowrap>提出 Learning Policy Committees for Effective Personalization in MDPs，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion/flow policy</td>
<td nowrap>RL / offline RL</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2503.01885">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18623">Lift3D Foundation Policy: Lifting 2D Large-Scale Pretrained Models for Robust 3D Robotic Manipulation</a></td>
<td nowrap>研究 Lift3D Foundation Policy 对多模态扰动、对抗输入或分布偏移下的 VLA 鲁棒性。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>3D representation / diffusion/flow policy</td>
<td nowrap>Generative action modeling</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>simulation benchmarks + real FR3</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18623">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Tian_PDFactor_Learning_Tri-Perspective_View_Policy_Diffusion_Field_for_Multi-Task_Robotic_CVPR_2025_paper.pdf">PDFactor: Learning Tri-Perspective View Policy Diffusion Field for Multi-Task Robotic Manipulation</a></td>
<td nowrap>PDFactor 将 3D 动作分布表示为三视角扩散场，用于高效多任务机器人操作。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>diffusion policy / diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Tian_PDFactor_Learning_Tri-Perspective_View_Policy_Diffusion_Field_for_Multi-Task_Robotic_CVPR_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.16201">FlowRAM: Grounding Flow Matching Policy with Region-Aware Mamba Framework for Robotic Manipulation</a></td>
<td nowrap>提出 FlowRAM，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>flow matching / diffusion/flow policy</td>
<td nowrap>Flow matching policy</td>
<td nowrap>Flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2506.16201">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18369">G3Flow: Generative 3D Semantic Flow for Pose-aware and Generalizable Object Manipulation</a></td>
<td nowrap>提出 G3Flow，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>flow matching / 3D representation / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18369">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>RoboTwin_Benchmark tasks</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.03142">AffordDP: Generalizable Diffusion Policy with Transferable Affordance</a></td>
<td nowrap>提出 AffordDP，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion policy / affordance / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Sim + Real</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2412.03142">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.13091">Touch2Shape: Touch-Conditioned 3D Diffusion for Shape Exploration and Reconstruction</a></td>
<td nowrap>Touch2Shape 用触觉观测条件化 3D 扩散模型，以探索并重建物体形状。</td>
<td nowrap>-</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>diffusion policy / 3D representation / diffusion/flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2505.13091">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### 3D grounding

共 31 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>Base VLA</th>
<th nowrap>Action</th>
<th nowrap>训练/反馈</th>
<th nowrap>Algorithm</th>
<th nowrap>Policy/Type</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/zhen24a.html">3D-VLA: A 3D Vision-Language-Action Generative World Model</a></td>
<td nowrap>3D-VLA builds a 3D generative world model for vision-language-action manipulation.</td>
<td nowrap>3D VLA</td>
<td nowrap>3D grounded action</td>
<td nowrap>3D grounding / world model</td>
<td nowrap>3D generative world modeling</td>
<td nowrap>3D VLA policy</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Ground VLA action generation in 3D world representations.</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/zhen24a/zhen24a.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2606.26800">SSI-Policy: Learning Structured Scene Interfaces for Vision-Language Robotic Manipulation</a></td>
<td nowrap>SSI-Policy 用结构化场景接口连接视觉语言推理和低数据机器人操作策略学习。</td>
<td nowrap>vision-language policy</td>
<td nowrap>continuous action</td>
<td nowrap>3D grounding / structured scene interface</td>
<td nowrap>scene-interface policy learning</td>
<td nowrap>structured VLA policy</td>
<td nowrap>Real robot manipulation</td>
<td nowrap>用结构化场景表示提升低数据机器人操作泛化。</td>
<td nowrap><a href="https://arxiv.org/abs/2606.26800">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://kalie-vlm.github.io/">KALIE: Fine-Tuning Vision-Language Models for Open-World Manipulation without Robot Data</a></td>
<td nowrap>KALIE 用 VLM 预测语言条件点式 affordance，通过合成数据支持开放世界机器人操作。</td>
<td nowrap>VLM</td>
<td nowrap>affordance point</td>
<td nowrap>3D grounding / affordance grounding</td>
<td nowrap>synthetic data fine-tuning</td>
<td nowrap>affordance-conditioned manipulation</td>
<td nowrap>Real robot manipulation</td>
<td nowrap>不用真实机器人数据学习语言条件 affordance。</td>
<td nowrap><a href="https://kalie-vlm.github.io/">paper</a></td>
<td nowrap><a href="https://kalie-vlm.github.io/">project</a></td>
<td nowrap><a href="https://github.com/gractang/kalie">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=7M6ryCABIc">PixelVLA: Advancing Pixel-level Understanding in Vision-Language-Action Model</a></td>
<td nowrap>提出 PixelVLA，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=7M6ryCABIc">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=eKhOrQWAVJ">Spatially Guided Training for Vision-Language-Action Model</a></td>
<td nowrap>提出 Spatially Guided Training，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=eKhOrQWAVJ">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=euMVC1DO4k">Spatial Forcing: Implicit Spatial Representation Alignment for Vision-language-action Model</a></td>
<td nowrap>提出 Spatial Forcing，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=euMVC1DO4k">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=fzmittHfq3">From Spatial to Actions: Grounding Vision-Language-Action Model in Spatial Foundation Priors</a></td>
<td nowrap>提出 From Spatial to Actions，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=fzmittHfq3">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=18gC6pZVVc">Geometry-aware 4D Video Generation for Robot Manipulation</a></td>
<td nowrap>提出 Geometry-aware 4D Video Generation，利用视频生成/预测或未来渲染学习机器人交互动态。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=18gC6pZVVc">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=WXFfMLyB6y">Generalizable Coarse-to-Fine Robot Manipulation via Language-Aligned 3D Keypoints</a></td>
<td nowrap>提出 Generalizable Coarse-to-Fine Robot Manipulation，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D keypoint grounding</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=WXFfMLyB6y">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=ggofj6tyr3">Geometry-aware Policy Imitation</a></td>
<td nowrap>提出 Geometry-aware Policy Imitation，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=ggofj6tyr3">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=qXfRXfAHOK">PA3FF:Learning Part-Aware Dense 3D Feature Field For Generalizable Articulated Object Manipulation</a></td>
<td nowrap>提出 PA3FF，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=qXfRXfAHOK">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=z8BN7KyaPl">RAVEN: End-to-end Equivariant Robot Learning with RGB Cameras</a></td>
<td nowrap>提出 RAVEN，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=z8BN7KyaPl">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=DE5ZJtR4bg">On the Generalization Capacities of MLLMs for Spatial Intelligence</a></td>
<td nowrap>提出 On the Generalization Capacities of MLLMs，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=DE5ZJtR4bg">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38921">ReconVLA: Reconstructive Vision-Language-Action Model as Effective Robot Perceiver</a></td>
<td nowrap>ReconVLA 通过重建目标注视区域来提升视觉-语言-动作机器人策略的视觉 grounding。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38921">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38939">Indoor Multi-View Radar Object Detection via 3D Bounding Box Diffusion</a></td>
<td nowrap>REXO 将基于扩散的 3D 边界框引入多视角雷达感知，用于室内目标检测。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>3D representation / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38939">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38946">RaLD: Generating High-Resolution 3D Radar Point Clouds with Latent Diffusion</a></td>
<td nowrap>RaLD 使用潜在扩散生成更密集、更高分辨率的 3D 雷达点云。</td>
<td nowrap>-</td>
<td nowrap>AR / Diffusion / Flow</td>
<td nowrap>3D representation / diffusion/flow policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38946">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38947">Grounding Actions in Camera Space: Observation-Centric Vision-Language-Action Policy</a></td>
<td nowrap>OC-VLA 在相机坐标中预测动作，以降低 VLA 策略中的观测-动作空间不一致。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38947">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.24261">DynaRend: Learning 3D Dynamics via Masked Future Rendering for Robotic Manipulation</a></td>
<td nowrap>提出 DynaRend，利用视频生成/预测或未来渲染学习机器人交互动态。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>Generative action modeling</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2510.24261">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://neurips.cc/virtual/2025/loc/san-diego/poster/118141">Building 3D Representations and Generating Motions From a Single Image via Video-Generation</a></td>
<td nowrap>VGER 从单张 RGB 图像生成视频来构建 3D 场景表示，用于无碰撞运动生成。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://neurips.cc/virtual/2025/loc/san-diego/poster/118141">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2504.12636">A0: An Affordance-Aware Hierarchical Model for General Robotic Manipulation</a></td>
<td nowrap>提出 A0，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / affordance / 3D grounding</td>
<td nowrap>Flow matching policy</td>
<td nowrap>Flow policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2504.12636">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2408.10123v1">Learning Precise Affordances from Egocentric Videos for Robotic Manipulation</a></td>
<td nowrap>提出 Learning Precise Affordances from Egocentric Videos，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>affordance / 3D grounding</td>
<td nowrap>Affordance grounding</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2408.10123v1">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04380">EmbodiedOcc: Embodied 3D Occupancy Prediction for Vision-based Online Scene Understanding</a></td>
<td nowrap>提出 EmbodiedOcc，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / RL/在线微调</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04380">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2504.08531">Embodied Image Captioning: Self-supervised Learning Agents for Spatially Coherent Image Descriptions</a></td>
<td nowrap>提出 Embodied Image Captioning，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2504.08531">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.10745">Unifying 2D and 3D Vision-Language Understanding</a></td>
<td nowrap>提出 Unifying 2D and 3D Vision-Language Understanding，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2503.10745">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.04119">GAPrompt: Geometry-Aware Point Cloud Prompt for 3D Vision Model</a></td>
<td nowrap>提出 GAPrompt，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2505.04119">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.00174">SOLAMI: Social Vision-Language-Action Modeling for Immersive Interaction with 3D Autonomous Characters</a></td>
<td nowrap>提出 SOLAMI，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 3D representation / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2412.00174">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.03841">OmniManip: Towards General Robotic Manipulation via Object-Centric Interaction Primitives as Spatial Constraints</a></td>
<td nowrap>提出 OmniManip，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 3D grounding</td>
<td nowrap>Affordance grounding</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2501.03841">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/pdf/2504.21530">RoboGround: Robot Manipulation with Grounded Vision-Language Priors</a></td>
<td nowrap>RoboGround 将视觉-语言 grounding 掩码作为中间空间先验，用于可泛化的操作策略。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA / 3D grounding</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2406.18158">3D-MVP: 3D Multiview Pretraining for Robotic Manipulation</a></td>
<td nowrap>提出 3D-MVP，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>Generative action modeling</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2406.18158">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.07135">VidBot: Learning Generalizable 3D Actions from In-the-Wild 2D Human Videos for Zero-Shot Robotic Manipulation</a></td>
<td nowrap>提出 VidBot，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>3D representation / 3D grounding</td>
<td nowrap>Diffusion policy</td>
<td nowrap>Diffusion policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2503.07135">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.05507">AutoURDF: Unsupervised Robot Modeling from Point Cloud Frames Using Cluster Registration</a></td>
<td nowrap>提出 AutoURDF，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>3D grounding</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2412.05507">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### online/RL fine-tuning

共 16 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>Base VLA</th>
<th nowrap>Action</th>
<th nowrap>训练/反馈</th>
<th nowrap>Algorithm</th>
<th nowrap>Policy/Type</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/springenberg24a.html">Offline Actor-Critic Reinforcement Learning Scales to Large Models</a></td>
<td nowrap>This work studies scaling offline actor-critic reinforcement learning to large model policies.</td>
<td nowrap>large policy model</td>
<td nowrap>policy action</td>
<td nowrap>offline RL / VLA post-training</td>
<td nowrap>offline actor-critic</td>
<td nowrap>model-based or actor-critic RL</td>
<td nowrap>offline RL benchmarks</td>
<td nowrap>Understand how large policies can be improved with offline RL.</td>
<td nowrap><a href="https://arxiv.org/abs/2402.05546">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2512.23703">General Process Reward Modeling for Robotic Reinforcement Learning</a></td>
<td nowrap>GPRM builds process reward models for robotic reinforcement learning and policy improvement.</td>
<td nowrap>robot policy</td>
<td nowrap>robot action</td>
<td nowrap>VLA / RL / reward modeling</td>
<td nowrap>process reward modeling</td>
<td nowrap>robotic RL</td>
<td nowrap>robot RL benchmarks</td>
<td nowrap>Use process-level rewards to improve robotic policy learning.</td>
<td nowrap><a href="https://arxiv.org/abs/2512.23703">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2503.05833">Refined Policy Distillation: From VLA Generalists to RL Experts</a></td>
<td nowrap>RPD 将 Octo/OpenVLA 等通用 VLA 通过 RL 蒸馏成任务专家策略。</td>
<td nowrap>Octo / OpenVLA</td>
<td nowrap>policy action</td>
<td nowrap>RL distillation / online fine-tuning</td>
<td nowrap>Refined Policy Distillation</td>
<td nowrap>RL expert policy</td>
<td nowrap>Sim + Real</td>
<td nowrap>把通用 VLA 迁移为更强的任务专家策略。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.05833">paper</a></td>
<td nowrap><a href="https://refined-policy-distillation.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Refined-Policy-Distillation/RPD">code</a></td>
<td nowrap><a href="https://huggingface.co/Juelg">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=ULTWUuGhC3">Interleave-VLA: Enhancing Robot Manipulation with Image-Text Interleaved Instructions</a></td>
<td nowrap>Interleave-VLA 提供端到端机器人学习的开源工具、数据格式或基准接口。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>policy action</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>-</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>SIMPLER + VIMA-Bench + real FANUC</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=ULTWUuGhC3">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>Interleaved X-Embodiment; 210k trajectories</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=eUGoqrZ6Ea">Self-Improving Vision-Language-Action Models with Data Generation via Residual RL</a></td>
<td nowrap>提出 Self-Improving Vision-Language-Action Models with Data Generation，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>PLD residual RL + SFT distillation</td>
<td nowrap>Off-policy residual RL</td>
<td nowrap>LIBERO + SimplerEnv + real Franka/YAM</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=eUGoqrZ6Ea">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=sFO9d6XSlf">Actions as Language: Fine-Tuning VLMs into VLAs Without Catastrophic Forgetting</a></td>
<td nowrap>Actions as Language 提供端到端机器人学习的开源工具、数据格式或基准接口。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>policy action</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>VLM2VLA; language action representation + LoRA</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>800+ real robot experiments</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=sFO9d6XSlf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=GrsoLVNy3Y">Cross-Embodiment Offline Reinforcement Learning for Heterogeneous Robot Datasets</a></td>
<td nowrap>提出 Cross-Embodiment Offline Reinforcement Learning，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>offline RL + morphology grouping</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=GrsoLVNy3Y">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>16 robot-platform locomotion dataset suite</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=ITeuGb2bYg">Policy Likelihood-based Query Sampling and Critic-Exploited Reset for Efficient Preference-based Reinforcement Learning</a></td>
<td nowrap>提出 Policy Likelihood-based Query Sampling and Critic-Exploited Reset，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>RL / offline RL</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=ITeuGb2bYg">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=TQhSodCM4r">SimpleVLA-RL: Scaling VLA Training via Reinforcement Learning</a></td>
<td nowrap>提出 SimpleVLA-RL，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>OpenVLA-OFT</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL / RL/在线微调 / Reward S</td>
<td nowrap>GRPO</td>
<td nowrap>On-Policy / MF</td>
<td nowrap>Sim ✓ (MT) / Real ✓ (ST)</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=TQhSodCM4r">paper</a> / <a href="https://arxiv.org/pdf/2509.09674">paper</a> / <a href="https://arxiv.org/abs/2509.09674">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=uWJwQ5SZoM">Robust Fine-tuning of Vision-Language-Action Robot Policies via Parameter Merging</a></td>
<td nowrap>研究 Robust Fine-tuning of Vision-Language-Action Robot Policies 对多模态扰动、对抗输入或分布偏移下的 VLA 鲁棒性。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>-</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=uWJwQ5SZoM">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=dc90uPqxWF">World2Minecraft: Occupancy-Driven simulated scenes Construction</a></td>
<td nowrap>提出 World2Minecraft，把 3D 几何、空间定位或可供性先验接入机器人感知与操作。</td>
<td nowrap>-</td>
<td nowrap>3D/spatial grounding</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>3D/spatial representation learning</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=dc90uPqxWF">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38876">Steering Visuomotor Policy in Open Worlds via Cross-View Goal Alignment</a></td>
<td nowrap>该方法允许用户从自身相机视角指定目标，并将其对齐到智能体视角以实现开放世界视觉运动控制。</td>
<td nowrap>-</td>
<td nowrap>policy action</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>-</td>
<td nowrap>RL fine-tuning / policy optimization</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38876">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63131">HIER: Human-in-the-Loop Imagination-Execution Refinement for General Real-World Vision-Language-Action Models</a></td>
<td nowrap>HIER 通过人在环的想象、执行和反馈迭代细化真实世界 VLA 行为。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63131">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=RkdTtznSAL">Real-World Reinforcement Learning of Active Perception Behaviors</a></td>
<td nowrap>该工作利用特权训练信号和非对称优势加权回归，在真实世界中训练主动感知策略。</td>
<td nowrap>-</td>
<td nowrap>AR</td>
<td nowrap>RL / RL/在线微调</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=RkdTtznSAL">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.19789">What Can RL Bring to VLA Generalization? An Empirical Study</a></td>
<td nowrap>RLVLA 系统研究 PPO、GRPO、DPO 等强化学习对 VLA 跨任务泛化的作用。</td>
<td nowrap>OpenVLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL / Online Fine-tuning</td>
<td nowrap>PPO / GRPO / DPO</td>
<td nowrap>Hybrid / MF</td>
<td nowrap>Sim ✓ (MT)</td>
<td nowrap>衡量强化学习能为 VLA 泛化带来什么增益。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.19789">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/gen-robot/RL4VLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.07395">ReinboT: Amplifying Robot Visual-Language Manipulation with Reinforcement Learning</a></td>
<td nowrap>提出 ReinboT，利用强化学习、偏好反馈或后训练信号提升机器人策略。</td>
<td nowrap>ReinboT</td>
<td nowrap>AR</td>
<td nowrap>VLA / RL / RL/在线微调</td>
<td nowrap>DT + RTG</td>
<td nowrap>Off-Policy / MF</td>
<td nowrap>Sim + Real</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2505.07395">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### 安全鲁棒性

共 7 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>Base VLA</th>
<th nowrap>Action</th>
<th nowrap>训练/反馈</th>
<th nowrap>Algorithm</th>
<th nowrap>Policy/Type</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2024/hash/d83fd70a31c64e020844ec80705ba87f-Abstract-Conference.html">Diffusion Policy Attacker: Crafting Adversarial Attacks for Diffusion-based Policies</a></td>
<td nowrap>DPA studies adversarial attacks against diffusion-based robot policies.</td>
<td nowrap>diffusion policy</td>
<td nowrap>continuous action</td>
<td nowrap>VLA / safety and robustness</td>
<td nowrap>diffusion policy attack</td>
<td nowrap>adversarial robustness evaluation</td>
<td nowrap>robot policy benchmarks</td>
<td nowrap>Evaluate attack surfaces in diffusion-based robot policies.</td>
<td nowrap><a href="https://arxiv.org/abs/2405.19424">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=OwinX7PI83">BEAT: Visual Backdoor Attacks on VLM-based Embodied Agents via Contrastive Trigger Learning</a></td>
<td nowrap>BEAT crafts visual backdoor attacks for VLM-based embodied agents using contrastive trigger learning.</td>
<td nowrap>VLM embodied agent</td>
<td nowrap>policy action</td>
<td nowrap>VLA / safety and robustness</td>
<td nowrap>contrastive trigger learning</td>
<td nowrap>backdoor attack evaluation</td>
<td nowrap>embodied agent benchmarks</td>
<td nowrap>Expose visual backdoor risks in embodied VLM agents.</td>
<td nowrap><a href="https://arxiv.org/abs/2510.27623">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://ieeexplore.ieee.org/document/11128017/">Run-time Observation Interventions Make Vision-Language-Action Models More Visually Robust</a></td>
<td nowrap>BYOVLA 在运行时识别并编辑任务无关视觉区域，提升 Octo/OpenVLA 对视觉干扰的鲁棒性。</td>
<td nowrap>Octo / OpenVLA</td>
<td nowrap>AR / policy action</td>
<td nowrap>VLA / safety and robustness</td>
<td nowrap>run-time observation intervention</td>
<td nowrap>robust VLA execution</td>
<td nowrap>Real robot manipulation</td>
<td nowrap>降低真实部署中无关视觉扰动导致的 VLA 失败。</td>
<td nowrap><a href="https://ieeexplore.ieee.org/document/11128017/">paper</a></td>
<td nowrap><a href="https://aasherh.github.io/byovla/">project</a></td>
<td nowrap><a href="https://github.com/irom-princeton/byovla">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=cS6xizdYD5">On Robustness of Vision-Language-Action Model against Multi-Modal Perturbations</a></td>
<td nowrap>研究 On Robustness of Vision-Language-Action Model against Multi-Modal Perturbations 对多模态扰动、对抗输入或分布偏移下的 VLA 鲁棒性。</td>
<td nowrap>π0 / OpenVLA</td>
<td nowrap>Diffusion / Flow</td>
<td nowrap>VLA / safety / 安全鲁棒</td>
<td nowrap>RobustVLA; 17 perturbations across 4 modalities</td>
<td nowrap>Flow policy</td>
<td nowrap>LIBERO + real FR5</td>
<td nowrap>-</td>
<td nowrap><a href="https://openreview.net/forum?id=cS6xizdYD5">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.03480">SafeVLA: Towards Safety Alignment of Vision-Language-Action Model via Constrained Learning</a></td>
<td nowrap>SafeVLA 通过约束强化学习让 VLA 策略满足安全约束。</td>
<td nowrap>SPOC</td>
<td nowrap>AR</td>
<td nowrap>VLA / safety and robustness</td>
<td nowrap>PPO with constrained learning</td>
<td nowrap>On-policy / MF</td>
<td nowrap>Sim ✓ (ST)</td>
<td nowrap>在部署前提升 VLA 策略的安全对齐。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.03480">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/pku-safevla">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.16640">BadVLA: Towards Backdoor Attacks on Vision-Language-Action Models via Objective-Decoupled Optimization</a></td>
<td nowrap>研究 BadVLA 如何对 VLA 注入后门触发并影响机器人动作输出。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 安全鲁棒</td>
<td nowrap>objective-decoupled backdoor attack</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>构造并评估针对 VLA 机器人策略的后门攻击。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.16640">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.13587">Exploring the Adversarial Vulnerabilities of Vision-Language-Action Models in Robotics</a></td>
<td nowrap>研究 Exploring the Adversarial Vulnerabilities of Vision-Language-Action Models in Robotics 对多模态扰动、对抗输入或分布偏移下的 VLA 鲁棒性。</td>
<td nowrap>未指定具体基座 VLA</td>
<td nowrap>AR</td>
<td nowrap>VLA / 安全鲁棒</td>
<td nowrap>UADA / UPA / TMA adversarial attacks</td>
<td nowrap>3D-grounded policy/perception</td>
<td nowrap>simulation + physical setup</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2411.13587">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>LIBERO + BridgeData V2 attack assets</td>
</tr>
</tbody>
</table>

### WAM / 世界模型

WAM 将未来世界状态预测和动作生成合在一起，适合放在 agent 规划和低层控制之间。它的价值不是替代所有控制器，而是提供可想象、可验证、可恢复的中间层。

子方向：cascaded WAM、joint WAM、video/latent world model、world model for VLA、world model evaluation。

共 64 篇。

<table>
<thead>
<tr>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>观察重点</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>cascaded WAM</td>
<td nowrap>24</td>
<td nowrap>看先想象后执行的分层链路。</td>
</tr>
<tr>
<td nowrap>joint WAM</td>
<td nowrap>3</td>
<td nowrap>看视觉、状态和动作的联合建模。</td>
</tr>
<tr>
<td nowrap>video/latent world model</td>
<td nowrap>27</td>
<td nowrap>看未来视频或隐状态预测质量。</td>
</tr>
<tr>
<td nowrap>world model for VLA</td>
<td nowrap>10</td>
<td nowrap>看世界模型如何服务 VLA 决策。</td>
</tr>
</tbody>
</table>

#### cascaded WAM

共 24 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>WAM 类型</th>
<th nowrap>状态表示</th>
<th nowrap>动作接口</th>
<th nowrap>用途</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://nvlabs.github.io/X-MOBILITY/">X-MOBILITY: End-To-End Generalizable Navigation via World Modeling</a></td>
<td nowrap>X-MOBILITY 用自回归 latent world model 解耦世界动态学习和动作策略，支持 zero-shot sim2real 导航。</td>
<td nowrap>navigation world model</td>
<td nowrap>latent future state</td>
<td nowrap>navigation action</td>
<td nowrap>navigation policy imagination</td>
<td nowrap>Sim + Real</td>
<td nowrap>通过世界模型提升端到端导航泛化和 sim2real。</td>
<td nowrap><a href="https://nvlabs.github.io/X-MOBILITY/">paper</a></td>
<td nowrap><a href="https://nvlabs.github.io/X-MOBILITY/">project</a></td>
<td nowrap><a href="https://github.com/NVlabs/X-MOBILITY">code</a></td>
<td nowrap><a href="https://github.com/NVlabs/X-MOBILITY">data</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=748bHL2BAv">Ctrl-World: A Controllable Generative World Model for Robot Manipulation</a></td>
<td nowrap>构建可控多视角机器人世界模型，用想象 rollout 评估并改进泛化机器人策略。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>多视角视频世界模型</td>
<td nowrap>frame-level action conditioning</td>
<td nowrap>policy evaluation + synthetic improvement</td>
<td nowrap>Real robot data/DROID</td>
<td nowrap>解决通用机器人策略在新物体和新指令下真实 rollout 昂贵、难扩展的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=748bHL2BAv">paper</a></td>
<td nowrap><a href="https://ctrl-world.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Robert-gyj/Ctrl-World">code</a></td>
<td nowrap><a href="https://huggingface.co/yjguo/Ctrl-World">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=0GNBqoYcAP">Context and Diversity Matter: The Emergence of In-Context Learning in World Models</a></td>
<td nowrap>研究世界模型如何通过上下文样例识别或学习新环境动力学。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>environment dynamics/world-model latent</td>
<td nowrap>-</td>
<td nowrap>ICL dynamics prediction</td>
<td nowrap>sim/analysis</td>
<td nowrap>解决静态世界模型遇到新环境或稀有配置时适应性差的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=0GNBqoYcAP">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=4HZgkwVVFO">NeMo-map: Neural Implicit Flow Fields for Spatio-Temporal Motion Mapping</a></td>
<td nowrap>用神经隐式函数连续建模场地特定的时空运动流场。</td>
<td nowrap>spatio-temporal motion world model</td>
<td nowrap>implicit neural flow field</td>
<td nowrap>-</td>
<td nowrap>motion mapping/navigation safety</td>
<td nowrap>public motion datasets</td>
<td nowrap>解决人类环境中动态运动地图离散采样、离线构建成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=4HZgkwVVFO">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=8UZpmrxoLG">Astra: General Interactive World Model with Autoregressive Denoising</a></td>
<td nowrap>用自回归去噪视频模型生成可动作控制的长时未来世界。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>video world model</td>
<td nowrap>action-aware adapter</td>
<td nowrap>interactive future prediction</td>
<td nowrap>robot + driving scenarios</td>
<td nowrap>解决通用场景中基于历史观测和动作预测长时未来的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=8UZpmrxoLG">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=LQD1MrnbxH">Test-Time Mixture of World Models for Embodied Agents in Dynamic Environments</a></td>
<td nowrap>在测试时动态路由和组合多个世界模型以适应变化环境。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>mixture of world models</td>
<td nowrap>agent action/API</td>
<td nowrap>test-time adaptation for embodied reasoning</td>
<td nowrap>dynamic embodied env benchmarks</td>
<td nowrap>解决 embodied agents 在未见动态环境中世界模型组合和持续适应不足的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=LQD1MrnbxH">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=MPabX9LEds">Learning Massively Multitask World Models for Continuous Control</a></td>
<td nowrap>Newt 在 200 个连续控制任务上预训练并在线优化语言条件世界模型。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>language-conditioned multitask latent world model</td>
<td nowrap>continuous control actions</td>
<td nowrap>online RL pretraining/fine-tuning</td>
<td nowrap>-</td>
<td nowrap>解决连续控制多任务、多 embodiment 在线 RL 难扩展的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=MPabX9LEds">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>200-task benchmark</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=a1zfcaNTkM">ExoPredicator: Learning Abstract Models of Dynamic Worlds for Robot Planning</a></td>
<td nowrap>学习符号状态和内外生因果过程，用于长时机器人规划。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>abstract symbolic state + causal processes</td>
<td nowrap>symbolic/endogenous actions</td>
<td nowrap>long-horizon planning</td>
<td nowrap>simulated tabletop</td>
<td nowrap>解决机器人规划中环境自身变化与动作效果并发发生的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=a1zfcaNTkM">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=oBXfPyi47m">Efficient Reinforcement Learning by Guiding World Models with Non-Curated Data</a></td>
<td nowrap>利用无奖励、跨 embodiment、混合质量离线数据引导世界模型以提升在线 RL 样本效率。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>world model from offline/online data</td>
<td nowrap>visuomotor RL actions</td>
<td nowrap>sample-efficient online RL</td>
<td nowrap>72 visuomotor tasks/6 embodiments</td>
<td nowrap>解决非精筛离线数据直接微调世界模型因分布偏移难以提升 RL 的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=oBXfPyi47m">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=qmEyJadwHA">Object-Centric World Models from Few-Shot Annotations for Sample-Efficient Reinforcement Learning</a></td>
<td nowrap>OC-STORM 用少量标注提取对象中心表示，提升像素 MBRL 样本效率。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>object-centric latent</td>
<td nowrap>RL actions</td>
<td nowrap>sample-efficient MBRL</td>
<td nowrap>-</td>
<td nowrap>解决像素级世界模型忽视小但关键对象导致样本效率低的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=qmEyJadwHA">paper</a></td>
<td nowrap><a href="https://oc-storm.weipuzhang.com">project</a></td>
<td nowrap>-</td>
<td nowrap>Atari 100k, Hollow Knight</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=w3w7WVG4ks">Building spatial world models from sparse transitional episodic memories</a></td>
<td nowrap>ESWM 从稀疏离散 episodic memories 构建空间认知地图并预测未观测转移。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>episodic spatial latent map</td>
<td nowrap>navigation transitions</td>
<td nowrap>exploration/navigation planning</td>
<td nowrap>simulated spatial environments</td>
<td nowrap>解决空间世界模型需要长连续轨迹才能建图的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=w3w7WVG4ks">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=yDmb7xAfeb">World-In-World: World Models in a Closed-Loop World</a></td>
<td nowrap>提供闭环平台评测世界模型是否真正提升 embodied task success。</td>
<td nowrap>world model evaluation/closed-loop WAM</td>
<td nowrap>heterogeneous WMs</td>
<td nowrap>standardized action API</td>
<td nowrap>closed-loop planning/evaluation</td>
<td nowrap>-</td>
<td nowrap>解决世界模型评测偏 open-loop 视觉质量、缺少任务成功闭环指标的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=yDmb7xAfeb">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>World-In-World benchmark</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Patx6MRipw">ENACT: Evaluating Embodied Cognition with World Modeling of Egocentric Interaction</a></td>
<td nowrap>ENACT 用自我中心交互序列重排任务评估 VLM 的前向和逆向世界建模能力。</td>
<td nowrap>world model evaluation</td>
<td nowrap>egocentric state/action sequences</td>
<td nowrap>inverse world modeling actions</td>
<td nowrap>benchmark/evaluation</td>
<td nowrap>-</td>
<td nowrap>解决 VLM 是否具备 embodied cognition 和交互世界建模能力的评测问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=Patx6MRipw">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>ENACT</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63978">Cross-Embodiment Robot Foundation World Models with Latent Actions</a></td>
<td nowrap>LAC-WM 用统一潜在动作空间训练跨 embodiment 机器人世界模型。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>latent action-conditioned world model</td>
<td nowrap>unified latent actions</td>
<td nowrap>cross-embodiment adaptation</td>
<td nowrap>dexterous manipulation benchmark</td>
<td nowrap>解决不同机器人动作空间不一致导致世界模型难泛化到新 embodiment 的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63978">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63978">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62480">DDP-WM: Disentangled Dynamics Prediction for Efficient World Models</a></td>
<td nowrap>DDP-WM 将主动态与背景更新解耦，提升世界模型实时推理和规划效率。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>disentangled latent dynamics</td>
<td nowrap>MPC/planner</td>
<td nowrap>efficient planning</td>
<td nowrap>navigation/tabletop/deformable benchmarks</td>
<td nowrap>解决 dense Transformer 世界模型计算开销高、难实时部署的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62480">paper</a></td>
<td nowrap><a href="https://hcplab-sysu.github.io/DDP-WM">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62543">RoboFlow4D: A Lightweight Flow World Model Toward Real-Time Flow-Guided Robotic Manipulation</a></td>
<td nowrap>RoboFlow4D 直接预测多帧 3D flow，用流引导实时机器人操作。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>multi-frame 3D flow</td>
<td nowrap>flow-guided action policy</td>
<td nowrap>real-time manipulation planning</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决 3D 操作中模块化预测流规划管线开销高、实时性差的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62543">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62543">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64209">Learning Task-Sufficient World Models by Synergizing Agentic Exploration and Structured Modeling</a></td>
<td nowrap>通过主动探索和结构化建模学习任务充分且紧凑的世界模型表示。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>task-sufficient structured latent</td>
<td nowrap>agentic exploration/actions</td>
<td nowrap>sample-efficient control/generalization</td>
<td nowrap>continuous control + manipulation benchmarks</td>
<td nowrap>解决通用视觉/隐空间世界模型保留太多控制无关因素、影响泛化效率的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64209">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64209">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.15536">SAMPO: Scale-wise Autoregression with Motion PrOmpt for Generative World Models</a></td>
<td nowrap>SAMPO 结合尺度级视觉自回归、因果下一帧建模和运动提示生成动作条件未来。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>video tokens + motion prompt</td>
<td nowrap>action-conditioned video prediction</td>
<td nowrap>model-based control/video prediction</td>
<td nowrap>robot/world-model benchmarks</td>
<td nowrap>解决自回归世界模型空间结构破坏、解码低效、运动建模不足的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.15536">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.05495">Learning 3D Persistent Embodied World Models</a></td>
<td nowrap>学习带显式 3D 记忆的 embodied world model，以更一致地模拟长时未来观测。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>RGB-D video + persistent 3D map</td>
<td nowrap>future action-conditioned observation prediction</td>
<td nowrap>planning/policy learning</td>
<td nowrap>embodied applications</td>
<td nowrap>解决视频世界模型缺少未观测场景记忆、长时规划不一致的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.05495">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.20425">OSVI-WM: One-Shot Visual Imitation for Unseen Tasks using World-Model-Guided Trajectory Generation</a></td>
<td nowrap>用世界模型生成潜在状态和动作轨迹，实现未见任务的一次视觉模仿。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>latent states/trajectory</td>
<td nowrap>decoded physical waypoints</td>
<td nowrap>one-shot imitation</td>
<td nowrap>2 sim benchmarks + 3 real robot platforms</td>
<td nowrap>解决 one-shot visual imitation 对语义或结构不同的新任务泛化差的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.20425">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/raktimgg/OSVI-WM">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2406.14540">IRASim: A Fine-Grained World Model for Robot Manipulation</a></td>
<td nowrap>IRASim 用逐帧动作条件扩散 Transformer 生成细粒度机器人-物体交互视频。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>action-conditioned video</td>
<td nowrap>robot action trajectories/frame-level conditioning</td>
<td nowrap>fine-grained manipulation simulation</td>
<td nowrap>robot manipulation datasets</td>
<td nowrap>解决机器人操作中动作与视觉帧精确对齐、细粒度交互预测困难的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2406.14540">paper</a></td>
<td nowrap><a href="https://gen-irasim.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://ziweiwangthu.github.io/data/GWM.pdf">GWM: Towards Scalable Gaussian World Models for Robotic Manipulation</a></td>
<td nowrap>GWM 用 3D Gaussian primitives 预测机器人动作后的未来 3D 场景。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>3D Gaussian splats latent</td>
<td nowrap>robot action-conditioned Gaussian propagation</td>
<td nowrap>imitation representation + MBRL simulator</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决图像世界模型缺少稳定 3D 几何信息、难支持策略训练的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.07954">paper</a></td>
<td nowrap><a href="https://gaussian-world-model.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Gaussian-World-Model/gaussianwm">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.16806">DyWA: Dynamics-adaptive World Action Model for Generalizable Non-prehensile Manipulation</a></td>
<td nowrap>DyWA 联合预测未来状态并适应动力学变化，提升非抓取操作泛化。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>single-view point cloud + geometry/state/physics</td>
<td nowrap>world action model</td>
<td nowrap>non-prehensile manipulation</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决非抓取操作在不同物体质量、桌面摩擦和单视角部分可观测下泛化困难的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.16806">paper</a></td>
<td nowrap><a href="https://pku-epic.github.io/DyWA/">project</a></td>
<td nowrap><a href="https://github.com/jiangranlv/DyWA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://openreview.net/pdf?id=mnwlhvmKMN">Learning 4D Embodied World Models</a></td>
<td nowrap>TesserAct 从图像和语言预测随动作演化的 4D 动态 mesh 世界。</td>
<td nowrap>cascaded WAM</td>
<td nowrap>4D dynamic mesh</td>
<td nowrap>inverse dynamics/policy execution</td>
<td nowrap>4D prediction + policy learning</td>
<td nowrap>dataset + embodied tasks</td>
<td nowrap>解决 2D 视频世界模型缺少精确 3D 几何和时间动态、难学逆动力学的问题。</td>
<td nowrap><a href="https://openreview.net/pdf?id=mnwlhvmKMN">paper</a> / <a href="https://arxiv.org/pdf/2504.20995">paper</a></td>
<td nowrap><a href="https://tesseractworld.github.io/">project</a></td>
<td nowrap><a href="https://github.com/UMass-Embodied-AGI/TesserAct">code</a></td>
<td nowrap><a href="https://huggingface.co/anyeZHY/tesseract">hf</a></td>
</tr>
</tbody>
</table>

#### joint WAM

共 3 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>WAM 类型</th>
<th nowrap>状态表示</th>
<th nowrap>动作接口</th>
<th nowrap>用途</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=IvUM6UwYCJ">Empowering Multi-Robot Cooperation via Sequential World Models</a></td>
<td nowrap>SeqWM 用自回归 agent-wise 世界模型降低多机器人联合动力学建模复杂度。</td>
<td nowrap>joint WAM</td>
<td nowrap>sequential agent-wise world models</td>
<td nowrap>multi-agent RL actions</td>
<td nowrap>multi-robot cooperation/planning</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决物理多机器人合作中 joint dynamics 复杂、MBRL 难扩展的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=IvUM6UwYCJ">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/zhaozijie2022/seqwm-marl">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64447">Dual-Stream Diffusion for World-Model Augmented Vision-Language-Action Model</a></td>
<td nowrap>DUST 用双流扩散 Transformer 分别建模视觉和动作并跨模态共享信息。</td>
<td nowrap>joint WAM</td>
<td nowrap>vision tokens + action tokens</td>
<td nowrap>diffusion/flow-matching action tokens</td>
<td nowrap>world-model augmented VLA</td>
<td nowrap>RoboCasa, GR-1, Franka Research 3</td>
<td nowrap>解决 VLA 中联合预测状态和动作时视觉-动作模态差异带来的训练困难。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64447">paper</a></td>
<td nowrap><a href="https://periphanes.github.io/dust/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.11296">Diffusion-Based Imaginative Coordination for Bimanual Manipulation</a></td>
<td nowrap>通过联合视频和动作扩散预测提升双臂操作协调。</td>
<td nowrap>joint WAM</td>
<td nowrap>multi-frame latent future states</td>
<td nowrap>diffusion action prediction</td>
<td nowrap>bimanual coordination</td>
<td nowrap>ALOHA + RoboTwin + Real</td>
<td nowrap>解决双臂操作高维动作空间和复杂协同导致策略学习困难的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.11296">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/return-sleep/Diffusion_based_imaginative_Coordination">code</a></td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### video/latent world model

共 27 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>WAM 类型</th>
<th nowrap>状态表示</th>
<th nowrap>动作接口</th>
<th nowrap>用途</th>
<th nowrap>Sim/Real</th>
<th nowrap>Benchmark</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>NeurIPS 2023</td>
<td nowrap><a href="https://arxiv.org/abs/2302.00111">Learning Universal Policies via Text-Guided Video Generation</a></td>
<td nowrap>This work learns policies by using text-guided video generation as an intermediate representation.</td>
<td nowrap>video/latent world model</td>
<td nowrap>text-guided generated video</td>
<td nowrap>video-conditioned action</td>
<td nowrap>policy learning from generated video</td>
<td nowrap>robot policy learning</td>
<td nowrap>robot manipulation tasks</td>
<td nowrap>Use generated videos as guidance for policy learning.</td>
<td nowrap><a href="https://arxiv.org/abs/2302.00111">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2310.10625">Video Language Planning</a></td>
<td nowrap>Video Language Planning uses video prediction and language goals to support planning.</td>
<td nowrap>video/latent world model</td>
<td nowrap>future video</td>
<td nowrap>language-conditioned plan/action</td>
<td nowrap>video-language planning</td>
<td nowrap>embodied planning</td>
<td nowrap>planning benchmarks</td>
<td nowrap>Plan with predicted video futures and language instructions.</td>
<td nowrap><a href="https://arxiv.org/abs/2310.10625">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=CKpqRFTRfc">MVISTA-4D: View-Consistent 4D World Model with Test-Time Action Inference for Robotic Manipulation</a></td>
<td nowrap>MVISTA-4D builds a view-consistent 4D world model and infers manipulation actions at test time.</td>
<td nowrap>video/latent world model</td>
<td nowrap>4D view-consistent world state</td>
<td nowrap>test-time action inference</td>
<td nowrap>4D world modeling</td>
<td nowrap>robot manipulation</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Use 4D world prediction to infer robot actions.</td>
<td nowrap><a href="https://openreview.net/forum?id=CKpqRFTRfc">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2312.13139">Unleashing Large-Scale Video Generative Pre-training for Visual Robot Manipulation</a></td>
<td nowrap>This work transfers large-scale video generative pretraining to visual robot manipulation.</td>
<td nowrap>video/latent world model</td>
<td nowrap>pretrained video generative model</td>
<td nowrap>robot action head</td>
<td nowrap>video generative pretraining</td>
<td nowrap>visual robot manipulation</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Leverage video generation pretraining for robot manipulation.</td>
<td nowrap><a href="https://arxiv.org/abs/2312.13139">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18179">Prediction with Action: Visual Policy Learning via Joint Denoising Process</a></td>
<td nowrap>Prediction with Action jointly denoises future visual predictions and actions for policy learning.</td>
<td nowrap>video/latent world model</td>
<td nowrap>visual prediction latents</td>
<td nowrap>joint denoising action</td>
<td nowrap>joint video-action denoising</td>
<td nowrap>visual policy learning</td>
<td nowrap>robot policy benchmarks</td>
<td nowrap>Couple future prediction with action generation.</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18179">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=3RSLW9YSgk">Dream to Manipulate: Compositional World Models Empowering Robot Imitation Learning with Imagination</a></td>
<td nowrap>Dream to Manipulate uses compositional world models to augment robot imitation learning with imagined rollouts.</td>
<td nowrap>video/latent world model</td>
<td nowrap>compositional imagined state</td>
<td nowrap>imitation action</td>
<td nowrap>world-model imagination</td>
<td nowrap>robot imitation learning</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Use imagination to improve imitation learning.</td>
<td nowrap><a href="https://openreview.net/forum?id=3RSLW9YSgk">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2024/hash/6164b6e5352c139e9ddc1a98c09e4e4a-Abstract-Conference.html">PIVOT-R: Primitive-Driven Waypoint-Aware World Model for Robotic Manipulation</a></td>
<td nowrap>PIVOT-R uses primitive-driven waypoint-aware world modeling for robot manipulation.</td>
<td nowrap>video/latent world model</td>
<td nowrap>waypoint-aware predicted state</td>
<td nowrap>primitive action interface</td>
<td nowrap>world-model manipulation planning</td>
<td nowrap>robot manipulation</td>
<td nowrap>robot manipulation benchmarks</td>
<td nowrap>Predict waypoint-aware futures for manipulation primitives.</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2024/file/6164b6e5352c139e9ddc1a98c09e4e4a-Paper-Conference.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Wang_Driving_into_the_Future_Multiview_Visual_Forecasting_and_Planning_with_CVPR_2024_paper.html">Driving into the Future: Multiview Visual Forecasting and Planning with World Model for Autonomous Driving</a></td>
<td nowrap>This work uses multiview visual forecasting as a world model for autonomous-driving planning.</td>
<td nowrap>video/latent world model</td>
<td nowrap>multiview future video</td>
<td nowrap>driving plan/action</td>
<td nowrap>visual forecasting + planning</td>
<td nowrap>autonomous driving</td>
<td nowrap>driving benchmarks</td>
<td nowrap>Use future visual prediction to support driving plans.</td>
<td nowrap><a href="https://arxiv.org/abs/2311.17918">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2023</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2023/file/d9042abf40782fbce28901c1c9c0e8d8-Paper-Conference.pdf">Video Prediction Models as Rewards for Reinforcement Learning</a></td>
<td nowrap>This paper uses video prediction models to define rewards for reinforcement learning.</td>
<td nowrap>video/latent world model</td>
<td nowrap>predicted video</td>
<td nowrap>RL reward signal</td>
<td nowrap>video-prediction reward</td>
<td nowrap>reinforcement learning</td>
<td nowrap>RL benchmarks</td>
<td nowrap>Use video prediction quality as a reward signal.</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2023/file/d9042abf40782fbce28901c1c9c0e8d8-Paper-Conference.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2024</td>
<td nowrap><a href="https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/05914.pdf">Diffusion Reward: Learning Rewards via Conditional Video Diffusion</a></td>
<td nowrap>Diffusion Reward learns reward functions through conditional video diffusion.</td>
<td nowrap>video/latent world model</td>
<td nowrap>conditional generated video</td>
<td nowrap>reward signal</td>
<td nowrap>diffusion reward learning</td>
<td nowrap>reinforcement learning</td>
<td nowrap>RL/video benchmarks</td>
<td nowrap>Learn rewards through conditional video diffusion.</td>
<td nowrap><a href="https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/05914.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2512.00961">Goal-Driven Reward by Video Diffusion Models for Reinforcement Learning</a></td>
<td nowrap>This work derives goal-driven rewards from video diffusion models for reinforcement learning.</td>
<td nowrap>video/latent world model</td>
<td nowrap>goal-conditioned video diffusion</td>
<td nowrap>reward signal</td>
<td nowrap>video diffusion reward</td>
<td nowrap>reinforcement learning</td>
<td nowrap>RL benchmarks</td>
<td nowrap>Use video diffusion models to shape goal-driven RL rewards.</td>
<td nowrap><a href="https://arxiv.org/abs/2512.00961">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2310.06114">Learning Interactive Real-World Simulators</a></td>
<td nowrap>This work learns interactive real-world simulators that can support action-conditioned prediction.</td>
<td nowrap>video/latent world model</td>
<td nowrap>interactive simulator state</td>
<td nowrap>action-conditioned simulation</td>
<td nowrap>learned world simulator</td>
<td nowrap>interactive environment modeling</td>
<td nowrap>simulation benchmarks</td>
<td nowrap>Learn action-conditioned simulators from real-world data.</td>
<td nowrap><a href="https://arxiv.org/abs/2310.06114">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2402.15391">Genie: Generative Interactive Environments</a></td>
<td nowrap>Genie learns generative interactive environments from video and supports controllable latent actions.</td>
<td nowrap>video/latent world model</td>
<td nowrap>interactive video latent state</td>
<td nowrap>latent action</td>
<td nowrap>generative interactive world model</td>
<td nowrap>interactive environment modeling</td>
<td nowrap>video/game environments</td>
<td nowrap>Build controllable interactive environments from videos.</td>
<td nowrap><a href="https://arxiv.org/abs/2402.15391">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.19842">ManiGaussian++: General Robotic Bimanual Manipulation with Hierarchical Gaussian World Model</a></td>
<td nowrap>ManiGaussian++ 用层级 Gaussian world model 建模双臂操作中的空间状态和交互动态。</td>
<td nowrap>Gaussian world model</td>
<td nowrap>hierarchical 3D Gaussian state</td>
<td nowrap>bimanual action</td>
<td nowrap>bimanual manipulation prediction</td>
<td nowrap>Sim + Real</td>
<td nowrap>-</td>
<td nowrap>用层级 3D 世界模型支持通用双臂操作。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.19842">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/April-Yz/ManiGaussian_bimanual">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=3q9vHEqsNx">FantasyWorld: Geometry-Consistent World Modeling via Unified Video and 3D Prediction</a></td>
<td nowrap>在冻结视频基础模型上加入几何分支，统一预测视频 latent 与隐式 3D 场。</td>
<td nowrap>video/latent world model</td>
<td nowrap>video latents + implicit 3D field</td>
<td nowrap>-</td>
<td nowrap>3D-aware video/world representation</td>
<td nowrap>3D reasoning benchmarks</td>
<td nowrap>-</td>
<td nowrap>解决视频世界模型缺少显式 3D grounding 和空间一致性的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=3q9vHEqsNx">paper</a></td>
<td nowrap><a href="https://fantasy-amap.github.io/fantasy-world/">project</a></td>
<td nowrap><a href="https://github.com/Fantasy-AMAP/fantasy-world">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=NQq9JLMfNN">Unified 3D Scene Understanding Through Physical World Modeling</a></td>
<td nowrap>3WM 将深度、视角合成、物体操作等 3D 任务统一成物理世界模型推理。</td>
<td nowrap>video/latent world model</td>
<td nowrap>probabilistic graph of RGB/flow/camera pose etc.</td>
<td nowrap>prompt/inference pathways</td>
<td nowrap>unified 3D understanding and interaction</td>
<td nowrap>multi-dataset 3D tasks</td>
<td nowrap>-</td>
<td nowrap>解决 3D 场景理解任务彼此割裂、难共享表示和迁移的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=NQq9JLMfNN">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=pFyzqbUiF9">Vid2World: Crafting Video Diffusion Models to Interactive World Models</a></td>
<td nowrap>Vid2World 将预训练视频扩散模型因果化并加入动作引导，转成交互式世界模型。</td>
<td nowrap>video/latent world model</td>
<td nowrap>causalized video diffusion latents</td>
<td nowrap>causal action guidance</td>
<td nowrap>interactive world modeling</td>
<td nowrap>sequential decision benchmarks</td>
<td nowrap>-</td>
<td nowrap>解决传统世界模型需大量特定领域训练且预测粗糙的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=pFyzqbUiF9">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=wcTuZG9P2o">EgoWorld: Translating Exocentric View to Egocentric View using Rich Exocentric Observations</a></td>
<td nowrap>EgoWorld 用点云、3D 手姿态和文本从第三人称观察重建第一人称视角。</td>
<td nowrap>video/latent world model</td>
<td nowrap>point cloud + 3D hand pose + text</td>
<td nowrap>-</td>
<td nowrap>egocentric view/world reconstruction for manipulation</td>
<td nowrap>AR/VR/robotics settings</td>
<td nowrap>-</td>
<td nowrap>解决 exocentric-to-egocentric 转换依赖同步多视角、相机位姿或初始 egocentric 帧的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=wcTuZG9P2o">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38905">LiDARCrafter: Dynamic 4D World Modeling from LiDAR Sequences</a></td>
<td nowrap>LiDARCrafter 用语言到自车场景图和三分支扩散模型生成可控 4D LiDAR 序列。</td>
<td nowrap>video/latent world model</td>
<td nowrap>4D LiDAR sequence/layout</td>
<td nowrap>-</td>
<td nowrap>LiDAR generation/editing/evaluation</td>
<td nowrap>nuScenes benchmark</td>
<td nowrap>-</td>
<td nowrap>解决自动驾驶 LiDAR 世界生成中的可控性、时序一致性和标准评测问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38905">paper</a></td>
<td nowrap><a href="https://lidarcrafter.github.io/">project</a></td>
<td nowrap><a href="https://github.com/worldbench/LiDARCrafter">code</a></td>
<td nowrap>nuScenes + scene/object/sequence metrics + HuggingFace weights</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65193">DreamDojo: A Generalist Robot World Model from Large-Scale Human Videos</a></td>
<td nowrap>DreamDojo 从 4.4 万小时人类第一视角视频中学习潜在动作驱动的机器人世界模型。</td>
<td nowrap>video/latent world model</td>
<td nowrap>video world model + continuous latent actions</td>
<td nowrap>-</td>
<td nowrap>teleoperation/policy evaluation/model-based planning</td>
<td nowrap>OOD robot benchmarks</td>
<td nowrap>-</td>
<td nowrap>解决机器人世界模型数据覆盖不足、动作标签稀缺和接触丰富任务难模拟的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.06949">paper</a></td>
<td nowrap><a href="https://dreamdojo-world.github.io/">project</a></td>
<td nowrap><a href="https://github.com/NVIDIA/DreamDojo">code</a></td>
<td nowrap><a href="https://huggingface.co/nvidia/DreamDojo">hf</a></td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66091">From Imagined Futures to Executable Actions: Mixture of Latent Actions for Robot Manipulation</a></td>
<td nowrap>MoLA 用多个逆动力学模型把想象视频转换成可执行的潜在动作混合表示。</td>
<td nowrap>video/latent world model</td>
<td nowrap>imagined future videos + latent actions</td>
<td nowrap>mixture of latent actions from inverse dynamics</td>
<td nowrap>video-to-action execution</td>
<td nowrap>LIBERO, CALVIN, LIBERO-Plus + Real</td>
<td nowrap>-</td>
<td nowrap>解决视频生成未来帧视觉逼真但难稳定转成控制动作的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66091">paper</a></td>
<td nowrap><a href="https://logosroboticsgroup.github.io/MoLA/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=UPHlqbZFZB">VideoVLA: Video Generators Can Be Generalizable Robot Manipulators</a></td>
<td nowrap>VideoVLA 将大视频生成模型改造成同时预测动作和未来视觉结果的机器人 VLA。</td>
<td nowrap>video/latent world model</td>
<td nowrap>video/language/action tokens</td>
<td nowrap>action sequence prediction</td>
<td nowrap>generalizable manipulation</td>
<td nowrap>Sim + Real</td>
<td nowrap>-</td>
<td nowrap>解决机器人操作泛化中视觉想象与动作预测未充分联合的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=UPHlqbZFZB">paper</a></td>
<td nowrap><a href="https://videovla-nips2025.github.io/">project</a></td>
<td nowrap><a href="https://github.com/VideoVLA-Project/VideoVLA">code</a></td>
<td nowrap>SIMPLER, OXE, Realman real-world eval</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.01895">EnerVerse: Envisioning Embodied Future Space for Robotics Manipulation</a></td>
<td nowrap>EnerVerse 用多视角视频扩散和 4D 数据引擎预测 embodied future space 并转成动作。</td>
<td nowrap>video/latent world model</td>
<td nowrap>multi-view video/4D world representations</td>
<td nowrap>EnerVerse-A policy head/action chunks</td>
<td nowrap>robot manipulation foundation model</td>
<td nowrap>Sim + Real</td>
<td nowrap>-</td>
<td nowrap>解决机器人操作中长时未来空间建模、3D grounding 和 sim-to-real 差距问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2501.01895">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/enerverse">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.04447">DreamVLA: A Vision-Language-Action Model Dreamed with Comprehensive World Knowledge</a></td>
<td nowrap>DreamVLA 预测动态、空间和语义世界知识，再用逆动力学生成动作。</td>
<td nowrap>video/latent world model</td>
<td nowrap>dynamic/spatial/semantic world knowledge</td>
<td nowrap>diffusion transformer action prediction</td>
<td nowrap>VLA manipulation</td>
<td nowrap>CALVIN + Real</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 只做图像预测信息冗余、缺少关键世界知识的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.04447">paper</a></td>
<td nowrap><a href="https://zhangwenyao1.github.io/DreamVLA/index.html">project</a></td>
<td nowrap><a href="https://github.com/Zhangwenyao1/DreamVLA">code</a></td>
<td nowrap><a href="https://huggingface.co/WenyaoZhang/DreamVLA">hf</a></td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.14803">Video Prediction Policy: A Generalist Robot Policy with Predictive Visual Representations</a></td>
<td nowrap>VPP 利用视频扩散模型内部未来表征学习隐式逆动力学策略。</td>
<td nowrap>video/latent world model</td>
<td nowrap>predictive visual representations from VDM</td>
<td nowrap>implicit inverse dynamics</td>
<td nowrap>generalist robot policy</td>
<td nowrap>CALVIN + real dexterous tasks</td>
<td nowrap>-</td>
<td nowrap>解决静态视觉编码器忽略 embodied task 所需动态信息的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.14803">paper</a></td>
<td nowrap><a href="https://video-prediction-policy.github.io/">project</a></td>
<td nowrap><a href="https://github.com/roboterax/video-prediction-policy">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11423">TASTE-Rob: Advancing Video Generation of Task-Oriented Hand-Object Interaction for Generalizable Robotic Manipulation</a></td>
<td nowrap>TASTE-Rob 提供对齐语言指令的第一视角手物交互视频数据，并用姿态细化提升视频生成。</td>
<td nowrap>video/latent world model</td>
<td nowrap>egocentric hand-object videos</td>
<td nowrap>video demonstrations for imitation</td>
<td nowrap>task-oriented video generation/manipulation</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决手物交互视频数据视角不一致、交互错位导致机器人模仿学习质量不足的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11423">paper</a></td>
<td nowrap><a href="https://taste-rob.github.io/">project</a></td>
<td nowrap><a href="https://github.com/GAP-LAB-CUHK-SZ/TASTE-Rob">code</a></td>
<td nowrap>TASTE-Rob 100,856 videos</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/34942">GraphMimic: Graph-to-Graphs Generative Modeling from Videos for Policy Learning</a></td>
<td nowrap>GraphMimic 将视频帧抽象成对象和视觉动作图，并生成未来图作为策略条件。</td>
<td nowrap>video/latent world model</td>
<td nowrap>object/action graphs</td>
<td nowrap>policy conditioned on generated future graphs</td>
<td nowrap>policy learning from videos</td>
<td nowrap>Sim + Real + cross-embodiment</td>
<td nowrap>-</td>
<td nowrap>解决动作标注机器人数据昂贵、难从跨 embodiment 视频中学技能的问题。</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/34942">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### world model for VLA

共 10 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>WAM 类型</th>
<th nowrap>状态表示</th>
<th nowrap>动作接口</th>
<th nowrap>用途</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ECCV 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2602.10098">VLA-JEPA: Enhancing Vision-Language-Action Model with Latent World Model</a></td>
<td nowrap>VLA-JEPA 用 JEPA 式潜在未来状态预测预训练 VLA，避免把未来帧泄漏进输入。</td>
<td nowrap>latent world model for VLA</td>
<td nowrap>future-frame latent targets</td>
<td nowrap>latent action tokens + action-head fine-tuning</td>
<td nowrap>VLA pretraining/generalization</td>
<td nowrap>LIBERO, LIBERO-Plus, SimplerEnv, real Franka</td>
<td nowrap>解决视频预训练 VLA 中外观偏置、无关运动和信息泄漏问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.10098">paper</a></td>
<td nowrap><a href="https://ginwind.github.io/VLA-JEPA/">project</a></td>
<td nowrap><a href="https://github.com/ginwind/VLA-JEPA">code</a></td>
<td nowrap><a href="https://huggingface.co/ginwind/VLA-JEPA">hf</a></td>
</tr>
<tr>
<td nowrap>ICRA 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2509.22643">VLA-Reasoner: Reinforcing Robotic Reasoning and Generalization with World Model</a></td>
<td nowrap>VLA-Reasoner 用世界模型 rollout 和在线 MCTS 为现有 VLA 加入测试时长程推理。</td>
<td nowrap>world model for VLA</td>
<td nowrap>predicted future states</td>
<td nowrap>VLA action candidates</td>
<td nowrap>test-time search and verification</td>
<td nowrap>Sim + Real</td>
<td nowrap>在动作执行前通过世界模型搜索未来结果。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.22643">paper</a></td>
<td nowrap><a href="https://vla-reasoner.github.io/">project</a></td>
<td nowrap><a href="https://github.com/wkguo/VLA-Reasoner">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.10370">LUMOS: Language-Conditioned Imitation Learning with World Models</a></td>
<td nowrap>LUMOS 在 learned world model latent space 中离线练习语言条件长时程 manipulation，再迁移到真机。</td>
<td nowrap>world model for VLA</td>
<td nowrap>latent world state</td>
<td nowrap>language-conditioned action</td>
<td nowrap>offline practice / imitation learning</td>
<td nowrap>Sim + Real</td>
<td nowrap>用世界模型练习降低真实机器人数据需求。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.10370">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=fHLtSxDFKC">Genie Envisioner: A Unified World Foundation Platform for Robotic Manipulation</a></td>
<td nowrap>GE 在视频生成框架内联合学习视觉表示和动作策略，支持跨 embodiment 操作。</td>
<td nowrap>world model for VLA</td>
<td nowrap>structured video latent</td>
<td nowrap>GE-Act flow-matching decoder/action trajectories</td>
<td nowrap>world foundation platform + policy inference</td>
<td nowrap>-</td>
<td nowrap>解决机器人操作中世界建模和动作策略分离、泛化监督成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=fHLtSxDFKC">paper</a></td>
<td nowrap><a href="https://genie-envisioner.github.io/">project</a></td>
<td nowrap><a href="https://github.com/AgibotTech/Genie-Envisioner-V1">code</a></td>
<td nowrap>&gt;1M manipulation episodes + released benchmarks</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=LQv9LU2Ufg">RIG: Synergizing Reasoning and Imagination in End-to-End Generalist Policy</a></td>
<td nowrap>RIG 在端到端通用策略中联合学习推理、动作和下一图像想象。</td>
<td nowrap>world model for VLA</td>
<td nowrap>reasoning + next-image/world dynamics</td>
<td nowrap>reason-then-act with imagined outcome</td>
<td nowrap>self-correction/test-time scaling</td>
<td nowrap>generalist embodied policy benchmarks</td>
<td nowrap>解决 embodied agent 只具备推理或想象单一能力、系统式组合效率低的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=LQv9LU2Ufg">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=qE2FyvRvuF">WMPO: World Model-based Policy Optimization for Vision-Language-Action Models</a></td>
<td nowrap>WMPO 用像素级世界模型在想象中对 VLA 做 on-policy GRPO。</td>
<td nowrap>world model for VLA</td>
<td nowrap>pixel-based imagined trajectories</td>
<td nowrap>VLA policy actions/GRPO</td>
<td nowrap>imagination-only policy optimization</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决 VLA 依赖专家示范、真实机器人 RL 采样成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=qE2FyvRvuF">paper</a></td>
<td nowrap><a href="https://wm-po.github.io/">project</a></td>
<td nowrap><a href="https://github.com/WM-PO/WMPO">code</a></td>
<td nowrap><a href="https://huggingface.co/fangqi/WMPO">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=wPEIStHxYH">Cosmos Policy: Fine-Tuning Video Models for Visuomotor Control and Planning</a></td>
<td nowrap>Cosmos Policy 单阶段微调预训练视频模型，使其生成动作、未来状态和值以支持规划。</td>
<td nowrap>world model for VLA / video-policy world model</td>
<td nowrap>video model latent frames for actions/states/values</td>
<td nowrap>latent-frame action generation + planning</td>
<td nowrap>visuomotor control/planning</td>
<td nowrap>-</td>
<td nowrap>解决视频模型用于机器人策略时需要复杂多阶段训练和额外动作架构的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=wPEIStHxYH">paper</a></td>
<td nowrap><a href="https://research.nvidia.com/labs/dir/cosmos-policy/cosmos_policy_index.html">project</a></td>
<td nowrap><a href="https://github.com/nvlabs/cosmos-policy">code</a></td>
<td nowrap>LIBERO, RoboCasa, real bimanual tasks</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38925">WorldAgen: Unified State-Action Prediction with Test-Time World Model Training</a></td>
<td nowrap>WorldAgen 用共享 Transformer 同时预测未来状态和动作，并在测试时训练世界模型适应新环境。</td>
<td nowrap>world model for VLA</td>
<td nowrap>past state-action trajectories</td>
<td nowrap>agent-model action head + exploratory actions</td>
<td nowrap>test-time adaptation for VLA</td>
<td nowrap>Sim/Benchmark</td>
<td nowrap>解决 VLA 部署到新物体配置或动力学环境时静态预训练难泛化的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38925">paper</a></td>
<td nowrap><a href="https://worldagen.github.io/">project</a></td>
<td nowrap><a href="https://github.com/mll-lab-nu/WorldAgen">code</a></td>
<td nowrap>CALVIN, LIBERO</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66169">VLAW: Iterative Co-Improvement of Vision-Language-Action Policy and World Model</a></td>
<td nowrap>VLAW 用真实 rollout 迭代提升动作条件视频世界模型，再生成合成数据改进 VLA。</td>
<td nowrap>world model for VLA</td>
<td nowrap>action-conditioned video world model</td>
<td nowrap>VLA actions + generated rollouts</td>
<td nowrap>iterative VLA/world-model co-improvement</td>
<td nowrap>Real + synthetic rollouts</td>
<td nowrap>解决真实 rollout 昂贵且现有世界模型物理保真度不足以直接改进策略的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66169">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/vla-w">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2603.03195">Chain of World: World Model Thinking in Latent Motion</a></td>
<td nowrap>CoWVLA 用视频 VAE 提取连续潜在运动链，并与离散动作预测联合微调。</td>
<td nowrap>world model for VLA / latent motion</td>
<td nowrap>structure and motion latents</td>
<td nowrap>autoregressive action sequence decoder</td>
<td nowrap>VLA pretraining/fine-tuning</td>
<td nowrap>robot simulation benchmarks</td>
<td nowrap>解决 world-model VLA 重建冗余背景、latent-action VLA 缺少连续时序动力学的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2603.03195">paper</a></td>
<td nowrap><a href="https://fx-hit.github.io/cowvla-io/">project</a></td>
<td nowrap><a href="https://github.com/fx-hit/CoWVLA">code</a></td>
<td nowrap><a href="https://huggingface.co/hitfx/CoWVLA">hf</a></td>
</tr>
</tbody>
</table>

### Agentic Planning / 推理规划

这一方向强调任务分解、记忆、失败监控、约束/affordance planning 和自改进规划。它最贴近“agent 规划，小模型或传统方法执行”的系统路线。

子方向：任务分解、memory、failure monitor、constraint / affordance planning、self-improving planning。

共 98 篇。

<table>
<thead>
<tr>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>观察重点</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>任务分解</td>
<td nowrap>36</td>
<td nowrap>看高层指令如何拆成可执行步骤。</td>
</tr>
<tr>
<td nowrap>memory</td>
<td nowrap>11</td>
<td nowrap>看长期记忆、经验复用和环境状态保持。</td>
</tr>
<tr>
<td nowrap>failure monitor</td>
<td nowrap>9</td>
<td nowrap>看失败检测、恢复和闭环修正。</td>
</tr>
<tr>
<td nowrap>constraint / affordance planning</td>
<td nowrap>10</td>
<td nowrap>看约束、可供性和物理可执行性。</td>
</tr>
<tr>
<td nowrap>self-improving planning</td>
<td nowrap>32</td>
<td nowrap>看自我改进、测试时优化和经验沉淀。</td>
</tr>
</tbody>
</table>

#### 任务分解

共 36 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>规划粒度</th>
<th nowrap>工具/记忆</th>
<th nowrap>反馈/自改进</th>
<th nowrap>执行接口</th>
<th nowrap>验证环境</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/html/Yang_Magma_A_Foundation_Model_for_Multimodal_AI_Agents_CVPR_2025_paper.html">Magma: A Foundation Model for Multimodal AI Agents</a></td>
<td nowrap>Magma provides a multimodal foundation model for agents that need perception, reasoning, and action.</td>
<td nowrap>Task Decomposition</td>
<td nowrap>multimodal foundation model</td>
<td nowrap>agent feedback</td>
<td nowrap>agent action interface</td>
<td nowrap>multimodal agent benchmarks</td>
<td nowrap>Build a foundation model for multimodal agent tasks.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Yang_Magma_A_Foundation_Model_for_Multimodal_AI_Agents_CVPR_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/huang24ae.html">LEO: Embodied Generalist Agent in 3D World</a></td>
<td nowrap>LEO is an embodied generalist agent for 3D-world understanding, reasoning, and task execution.</td>
<td nowrap>Task Decomposition</td>
<td nowrap>3D embodied memory</td>
<td nowrap>instruction feedback</td>
<td nowrap>embodied agent action</td>
<td nowrap>3D embodied benchmarks</td>
<td nowrap>Unify 3D perception and embodied instruction following.</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/huang24ae/huang24ae.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Majumdar_OpenEQA_Embodied_Question_Answering_in_the_Era_of_Foundation_Models_CVPR_2024_paper.html">OpenEQA: Embodied Question Answering in the Era of Foundation Models</a></td>
<td nowrap>OpenEQA benchmarks embodied question answering with foundation models in real and simulated scenes.</td>
<td nowrap>Task Decomposition</td>
<td nowrap>scene memory + QA context</td>
<td nowrap>benchmark feedback</td>
<td nowrap>embodied QA interface</td>
<td nowrap>OpenEQA benchmark</td>
<td nowrap>Evaluate foundation models on embodied scene questions.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Majumdar_OpenEQA_Embodied_Question_Answering_in_the_Era_of_Foundation_Models_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>EMNLP 2025</td>
<td nowrap><a href="https://aclanthology.org/2025.emnlp-industry.149/">VestaBench: An Embodied Benchmark for Safe Long-Horizon Planning Under Multi-Constraint and Adversarial Settings</a></td>
<td nowrap>VestaBench evaluates safe long-horizon embodied planning under constraints and adversarial settings.</td>
<td nowrap>Task Decomposition</td>
<td nowrap>constraint-aware benchmark state</td>
<td nowrap>safety feedback</td>
<td nowrap>planner action interface</td>
<td nowrap>VestaBench</td>
<td nowrap>Benchmark safe long-horizon planning with multiple constraints.</td>
<td nowrap><a href="https://aclanthology.org/2025.emnlp-industry.149.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://openreview.net/forum?id=iSwK1YqO7v">Embodied Agent Interface: Benchmarking LLMs for Embodied Decision Making</a></td>
<td nowrap>EAI benchmarks LLM decision making through a standardized embodied-agent interface.</td>
<td nowrap>Task Decomposition</td>
<td nowrap>agent interface context</td>
<td nowrap>benchmark feedback</td>
<td nowrap>embodied decision interface</td>
<td nowrap>EAI benchmark</td>
<td nowrap>Measure how LLMs make embodied decisions through a common interface.</td>
<td nowrap><a href="https://openreview.net/forum?id=iSwK1YqO7v">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2406.11818">Embodied Instruction Following in Unknown Environments</a></td>
<td nowrap>EIF 在未知家庭环境中把自然语言任务分解为可探索、可执行的高层计划。</td>
<td nowrap>Task Decomposition</td>
<td nowrap>multimodal LLM planner</td>
<td nowrap>visual feedback + exploration</td>
<td nowrap>navigation and interaction policy</td>
<td nowrap>house-level scenes</td>
<td nowrap>未知环境下的长程具身指令跟随。</td>
<td nowrap><a href="https://arxiv.org/abs/2406.11818">paper</a></td>
<td nowrap><a href="https://gary3410.github.io/eif_unknown/">project</a></td>
<td nowrap><a href="https://github.com/Gary3410/eif_unknown">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=8xTDnj39Ti">Vlaser: Vision-Language-Action Model with Synergistic Embodied Reasoning</a></td>
<td nowrap>提出 Vlaser，把上游具身推理与下游 VLA 策略学习结合。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>空间推理、具身grounding、QA、任务规划等基准</td>
<td nowrap>桥接具身推理与VLA策略学习</td>
<td nowrap><a href="https://openreview.net/forum?id=8xTDnj39Ti">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=tWMfhoP3as">OneTwoVLA: A Unified Vision-Language-Action Model with Adaptive Reasoning</a></td>
<td nowrap>统一 System One 行动和 System Two 推理，并按执行阶段自适应切换。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>unified VLA/action</td>
<td nowrap>-</td>
<td nowrap>统一VLA中的快速行动与关键时刻显式推理</td>
<td nowrap><a href="https://openreview.net/forum?id=tWMfhoP3as">paper</a> / <a href="https://arxiv.org/abs/2506.19850">paper</a></td>
<td nowrap><a href="https://robertwyq.github.io/univla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/baaivision/UniVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=yngvAamNQi">From Seeing to Doing: Bridging Reasoning and Decision for Robotic Manipulation</a></td>
<td nowrap>通过空间关系推理生成中间表示，指导机器人操作决策。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>用空间关系推理桥接视觉理解与操作决策</td>
<td nowrap><a href="https://openreview.net/forum?id=yngvAamNQi">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=nESyz4PvJL">VLMgineer: Vision-Language Models as Robotic Toolsmiths</a></td>
<td nowrap>自动让 VLM 设计并使用工具，把控制难题转移到工具几何设计上。</td>
<td nowrap>任务分解</td>
<td nowrap>tool design/use</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>用VLM自动生成机器人可用工具</td>
<td nowrap><a href="https://openreview.net/forum?id=nESyz4PvJL">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=3eTr9dGwJv">MomaGraph: State-Aware Unified Scene Graphs with Vision-Language Models for Embodied Task Planning</a></td>
<td nowrap>构建包含空间、功能、部件和状态的统一场景图用于具身任务规划。</td>
<td nowrap>任务分解</td>
<td nowrap>state-aware scene graph</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>用统一场景图支持导航-操作规划</td>
<td nowrap><a href="https://openreview.net/forum?id=3eTr9dGwJv">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=8iPwqr6Adk">Theory of Space: Can Foundation Models Construct Spatial Beliefs through Active Exploration?</a></td>
<td nowrap>提出 Theory of Space，评测模型能否主动探索并维护空间信念。</td>
<td nowrap>主动探索/空间信念</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>评测主动构建和修正空间信念</td>
<td nowrap><a href="https://openreview.net/forum?id=8iPwqr6Adk">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=EEONns7ae4">Compositional Visual Planning via Inference-Time Diffusion Scaling</a></td>
<td nowrap>在推理时用扩散组合缩放生成稳定长程视觉计划。</td>
<td nowrap>长程视觉计划</td>
<td nowrap>-</td>
<td nowrap>inference-time scaling</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决扩散策略长程规划中片段拼接不稳定的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=EEONns7ae4">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Y1VgLHbzCC">One Demo Is All It Takes: Planning Domain Derivation with LLMs from A Single Demonstration</a></td>
<td nowrap>用单个示范轨迹和 LLM 自动归纳 PDDL 谓词与动作。</td>
<td nowrap>任务分解</td>
<td nowrap>LLM + PDDL domain induction</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>从单示范自动派生符号规划域</td>
<td nowrap><a href="https://openreview.net/forum?id=Y1VgLHbzCC">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=tkEmIJv1tB">OmniEVA: Embodied Versatile Planner via Task-Adaptive 3D-Grounded and Embodiment-aware Reasoning</a></td>
<td nowrap>通过任务自适应 3D grounding 和本体约束推理构建通用具身规划器。</td>
<td nowrap>3D-grounded embodied planning</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planner with embodiment constraints</td>
<td nowrap>-</td>
<td nowrap>解决 MLLM 规划缺少几何适应性和机器人本体约束的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=tkEmIJv1tB">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=3u6AkbWEls">ManipEvalAgent: Promptable and Efficient Evaluation Framework for Robotic Manipulation Policies</a></td>
<td nowrap>用少量多轮执行快速、可提示地评估操作策略。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>高效评估机器人操作策略</td>
<td nowrap><a href="https://openreview.net/forum?id=3u6AkbWEls">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=9AA27en4go">Difference-Aware Retrieval Policies for Imitation Learning</a></td>
<td nowrap>提出 DARP，用差异感知检索缓解行为克隆分布外泛化问题。</td>
<td nowrap>任务分解</td>
<td nowrap>retrieval policy</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决模仿学习部署时状态偏移和累积误差。</td>
<td nowrap><a href="https://openreview.net/forum?id=9AA27en4go">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=d1wuA8oIH0">EquAct: An SE(3)-Equivariant Multi-Task Transformer for 3D Robotic Manipulation</a></td>
<td nowrap>用 SE(3) 等变 Transformer 提升 3D 多任务操作对物体位姿变化的泛化。</td>
<td nowrap>3D manipulation policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>SE(3)等变多任务操作泛化</td>
<td nowrap><a href="https://openreview.net/forum?id=d1wuA8oIH0">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=jXDZJAfRZB">Seeing Across Views: Benchmarking Spatial Reasoning of Vision-Language Models in Robotic Scenes</a></td>
<td nowrap>提出 MV-RoboBench 评测 VLM 多视角机器人空间推理。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>评估 VLM 是否能融合多相机视角完成机器人空间推理。</td>
<td nowrap><a href="https://openreview.net/forum?id=jXDZJAfRZB">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>MV-RoboBench</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=vmBIF25KLf">REI-Bench: Can Embodied Agents Understand Vague Human Instructions in Task Planning?</a></td>
<td nowrap>构建 REI-Bench 评测具身代理理解含糊指代表达并规划任务的能力。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>模糊人类指令下的具身任务规划</td>
<td nowrap><a href="https://openreview.net/forum?id=vmBIF25KLf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>REI-Bench</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=aCVfhY4Qen">PhyScensis: Physics-Augmented LLM Agents for Complex Physical Scene Arrangement</a></td>
<td nowrap>自动生成交互式 3D 场景布置，并引入物理增强 LLM agent。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>物理增强的复杂场景布置规划</td>
<td nowrap><a href="https://openreview.net/forum?id=aCVfhY4Qen">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=oJAIjUDxkZ">OmniActor: A Generalist GUI and Embodied Agent for 2D&amp;3D Worlds</a></td>
<td nowrap>用分层异构 MoE 统一 GUI 与具身任务的 2D/3D agent。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>任务分解</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>统一2D GUI与3D具身任务执行</td>
<td nowrap><a href="https://arxiv.org/abs/2509.02322">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/UITron-hub/OmniActor">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38896">GraphCoT-VLA: A 3D Spatial-Aware Reasoning Vision-Language-Action Model for Robotic Manipulation with Ambiguous Instructions</a></td>
<td nowrap>用 3D 空间图 Chain-of-Thought 推理，把歧义操作指令转化为稳健的 VLA 动作。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>歧义指令下的3D空间推理VLA</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38896">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38900">PhyPlan: Learning to Plan Tasks with Generalizable and Rapid Physical Reasoning for Embodied Manipulation</a></td>
<td nowrap>学习快速且可泛化的物理推理，用于规划多步具身操作任务。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>物理推理驱动的操作任务规划</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38900">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38906">Cook and Clean Together: Teaching Embodied Agents for Parallel Task Execution</a></td>
<td nowrap>训练具身智能体调度并协同并行子任务，以更快完成家务场景任务。</td>
<td nowrap>parallel task execution</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>并行任务执行规划</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38906">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38911">FoAM: Foresight-Augmented Multi-Task Imitation Policy for Robotic Manipulation</a></td>
<td nowrap>为多任务模仿策略加入未来状态前瞻，提高机器人操作可靠性。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>foresight augmentation</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>前瞻增强的多任务操作模仿</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38911">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38936">Zero-Shot Robotic Manipulation via 3D Gaussian Splatting-Enhanced Multimodal Retrieval-Augmented Generation</a></td>
<td nowrap>结合多模态检索与 3D Gaussian Splatting 场景表示，支撑零样本机器人操作。</td>
<td nowrap>任务分解</td>
<td nowrap>3D Gaussian Splatting + multimodal RAG</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>用 3DGS 增强多模态 RAG 支持零样本机器人操作。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38936">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38958">H-GAR: A Hierarchical Interaction Framework via Goal-Driven Observation-Action Refinement for Robotic Manipulation</a></td>
<td nowrap>从目标线索出发层级细化观测与动作，生成时间上连贯的操作行为。</td>
<td nowrap>hierarchical observation-action refinement</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>通过目标驱动的观测-动作细化做层级操作交互。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38958">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60500">TapSampling: Inference-Time Sampling with a Task-Progress-Understanding Verifier for Robotic Manipulation</a></td>
<td nowrap>用任务进度理解 verifier 筛选推理时动作采样，选择更可能成功的操作轨迹。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>inference-time verifier</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>用理解任务进度的 verifier 在推理时筛选操作采样。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60500">paper</a></td>
<td nowrap><a href="https://aipixel.github.io/TapSampling/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63250">Decompose and Recompose: Reasoning New Skills from Existing Abilities for Cross-Task Robotic Manipulation</a></td>
<td nowrap>把已有能力分解为可复用单元，再重组以完成未见过的跨任务目标。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>从已有技能推理组合新操作技能</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63250">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63250">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.09937">SAFE: Multitask Failure Detection for Vision-Language-Action Models</a></td>
<td nowrap>提出多任务失败检测器 SAFE，让 VLA 在新任务中及时发现失败。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>失败监控</td>
<td nowrap>VLA/action</td>
<td nowrap>LIBERO, SimplerEnv, real-world Franka/WidowX rollouts</td>
<td nowrap>多任务VLA失败检测</td>
<td nowrap><a href="https://arxiv.org/abs/2506.09937">paper</a></td>
<td nowrap><a href="https://vla-safe.github.io/">project</a></td>
<td nowrap><a href="https://github.com/vla-safe/SAFE">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.21302">Towards Reliable Code-as-Policies: A Neuro-Symbolic Framework for Embodied Task Planning</a></td>
<td nowrap>在 code-as-policies 生成中加入符号验证和交互式校验。</td>
<td nowrap>任务分解</td>
<td nowrap>neuro-symbolic verification</td>
<td nowrap>interactive validation</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决动态/部分可观测环境中 LLM 生成控制代码 grounding 不足。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.21302">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.14968">RDD: Retrieval-Based Demonstration Decomposer for Planner Alignment in Long-Horizon Tasks</a></td>
<td nowrap>用检索式示范分解器自动生成与低层策略对齐的子任务。</td>
<td nowrap>任务分解</td>
<td nowrap>retrieval-based demonstration decomposition</td>
<td nowrap>-</td>
<td nowrap>agent planner / planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决长程 VLA 规划器子任务分解和执行策略不匹配。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.14968">paper</a></td>
<td nowrap><a href="https://rdd-neurips.github.io/">project</a></td>
<td nowrap><a href="https://github.com/tasl-lab/Retrieval-Demonstration-Decomposer">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.21545">UniDomain: Pretraining a Unified PDDL Domain from Real-World Demonstrations for Generalizable Robot Task Planning</a></td>
<td nowrap>从 12,393 个操作视频预训练统一 PDDL 域用于在线任务规划。</td>
<td nowrap>任务分解</td>
<td nowrap>unified PDDL domain</td>
<td nowrap>任务分解</td>
<td nowrap>planning / reasoning / RL</td>
<td nowrap>真实操作示范视频与在线规划</td>
<td nowrap>解决符号规划依赖手工窄域、难泛化的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.21545">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.21230">World-aware Planning Narratives Enhance Large Vision-Language Model Planner</a></td>
<td nowrap>用世界感知规划叙事把环境上下文注入 LVLM 规划器。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>world-aware planning narrative enhancement</td>
<td nowrap>agent planner / planning / RL</td>
<td nowrap>-</td>
<td nowrap>解决长程交互中模型对环境上下文和多步目标理解不足。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.21230">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.18194">VLABench: A Large-Scale Benchmark for Language-Conditioned Robotics Manipulation with Long-Horizon Reasoning Tasks</a></td>
<td nowrap>提供面向长程推理语言条件操作的 VLA 基准。</td>
<td nowrap>任务分解</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>100-task VLABench; interactive VLA/workflow + non-interactive VLM evaluation</td>
<td nowrap>评测通用 VLA 在长程语言条件操作任务上的能力。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.18194">paper</a> / <a href="https://arxiv.org/pdf/2412.18194">paper</a></td>
<td nowrap><a href="https://vlabench.github.io/">project</a></td>
<td nowrap><a href="https://github.com/OpenMOSS/VLABench">code</a></td>
<td nowrap>VLABench HF</td>
</tr>
</tbody>
</table>

#### memory

共 11 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>规划粒度</th>
<th nowrap>工具/记忆</th>
<th nowrap>反馈/自改进</th>
<th nowrap>执行接口</th>
<th nowrap>验证环境</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2410.11989">Dynamic Open-Vocabulary 3D Scene Graphs for Long-Term Language-Guided Mobile Manipulation</a></td>
<td nowrap>DovSG 用动态开放词汇 3D scene graph 支撑长期语言任务、环境更新和移动操作。</td>
<td nowrap>Memory Planning</td>
<td nowrap>dynamic 3D scene graph</td>
<td nowrap>long-term scene updates</td>
<td nowrap>mobile manipulation planner</td>
<td nowrap>Real robot</td>
<td nowrap>用开放词汇场景图维护长期任务记忆。</td>
<td nowrap><a href="https://arxiv.org/abs/2410.11989">paper</a></td>
<td nowrap><a href="https://bjhyzj.github.io/dovsg-web/">project</a></td>
<td nowrap><a href="https://github.com/BJHYZJ/DovSG">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=1dH4ARGdwD">Scaling up Memory for Robotic Control via Experience Retrieval</a></td>
<td nowrap>MemER 微调 VLM 检索任务相关关键帧，让 VLA 处理分钟级长程记忆任务。</td>
<td nowrap>记忆规划</td>
<td nowrap>experience retrieval/keyframe memory</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决机器人控制中长时间经验记忆检索与复用。</td>
<td nowrap><a href="https://openreview.net/forum?id=1dH4ARGdwD">paper</a></td>
<td nowrap><a href="https://jen-pan.github.io/memer/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=79BOATBal9">Planning with an Embodied Learnable Memory</a></td>
<td nowrap>EPM 用 VLM 通过增删改维护文本化场景记忆供 LLM 规划。</td>
<td nowrap>记忆规划</td>
<td nowrap>Embodied Perception Memory</td>
<td nowrap>-</td>
<td nowrap>memory</td>
<td nowrap>PARTNR/动态室内移动操作</td>
<td nowrap>解决动态家庭移动操作中记忆更新和规划器读取环境状态的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=79BOATBal9">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=9cLPurIZMj">Memory, Benchmark &amp; Robots: A Benchmark for Solving Complex Tasks with Reinforcement Learning</a></td>
<td nowrap>提出 MIKASA/MIKASA-Robo 评测 RL agent 的记忆密集任务能力。</td>
<td nowrap>记忆规划</td>
<td nowrap>记忆规划</td>
<td nowrap>-</td>
<td nowrap>memory</td>
<td nowrap>-</td>
<td nowrap>提供机器人操作中记忆能力的标准化评测。</td>
<td nowrap><a href="https://openreview.net/forum?id=9cLPurIZMj">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/memorybenchrobots/">project</a></td>
<td nowrap><a href="https://github.com/CognitiveAISystems/MIKASA-Robo">code</a></td>
<td nowrap>MIKASA/MIKASA-Robo</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=E5L43l5EIu">Embodied Agents Meet Personalization: Investigating Challenges and Solutions Through the Lens of Memory Utilization</a></td>
<td nowrap>研究记忆如何支撑个性化具身助手，并组织用户偏好与日常习惯以服务后续任务。</td>
<td nowrap>记忆规划</td>
<td nowrap>记忆规划</td>
<td nowrap>-</td>
<td nowrap>memory</td>
<td nowrap>-</td>
<td nowrap>增强长期任务记忆</td>
<td nowrap><a href="https://openreview.net/forum?id=E5L43l5EIu">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60897">HiMe: Hierarchical Embodied Memory for Long-Horizon Vision-Language-Action Control</a></td>
<td nowrap>用层级具身记忆协调规划、监控与执行，支撑长程 VLA 控制。</td>
<td nowrap>记忆规划</td>
<td nowrap>记忆规划</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60897">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66214">Spatial Memory for Out-of-Vision Manipulation in Vision-Language-Action</a></td>
<td nowrap>维护视野外物体的空间语义记忆，使 VLA 策略能操作当前不可见目标。</td>
<td nowrap>记忆规划</td>
<td nowrap>记忆规划</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66214">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2602.20200">Global Prior Meets Local Consistency: Dual-Memory Augmented Vision-Language-Action Model for Efficient Robotic Manipulation</a></td>
<td nowrap>用全局先验记忆和局部行为记忆提升 VLA 动作生成效率与鲁棒性。</td>
<td nowrap>记忆规划</td>
<td nowrap>dual memory</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 动作生成低效和条件不稳的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.20200">paper</a></td>
<td nowrap><a href="https://cybertronagent.github.io/OptimusVLA.github.io/">project</a></td>
<td nowrap><a href="https://github.com/iLearn-Lab/CVPR26-OptimusVLA">code</a></td>
<td nowrap><a href="https://huggingface.co/iLearn-Lab/OptimusVLA_Memory">hf</a></td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.00358">Embodied VideoAgent: Persistent Memory from Egocentric Videos and Embodied Sensors Enables Dynamic Scene Understanding</a></td>
<td nowrap>从第一视角视频、深度和位姿构建持久场景记忆。</td>
<td nowrap>记忆规划</td>
<td nowrap>persistent object memory + tool queries</td>
<td nowrap>-</td>
<td nowrap>LLM tool calls + embodied action primitives</td>
<td nowrap>Ego4D-VQ3D, OpenEQA, EnvQA, real-world Franka demo</td>
<td nowrap>解决动态 3D 场景理解中长期记忆和对象状态更新。</td>
<td nowrap><a href="https://arxiv.org/abs/2501.00358">paper</a></td>
<td nowrap><a href="https://embodied-videoagent.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Embodied-VideoAgent/embodied-videoagent">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1915">Towards Long-Horizon Vision-Language-Action System: Reasoning, Acting and Memory</a></td>
<td nowrap>连接推理、动作执行与记忆，支撑动态环境中的长程 VLA 行为。</td>
<td nowrap>记忆规划</td>
<td nowrap>记忆规划</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1915">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.18564">SAM2Act: Integrating Visual Foundation Model with a Memory Architecture for Robotic Manipulation</a></td>
<td nowrap>SAM2Act 结合视觉基础模型和记忆架构提升多任务操作泛化。</td>
<td nowrap>记忆规划</td>
<td nowrap>记忆规划</td>
<td nowrap>-</td>
<td nowrap>memory</td>
<td nowrap>-</td>
<td nowrap>解决动态环境中操作策略的泛化和空间记忆不足。</td>
<td nowrap><a href="https://arxiv.org/abs/2501.18564">paper</a></td>
<td nowrap><a href="https://sam2act.github.io">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### failure monitor

共 9 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>规划粒度</th>
<th nowrap>工具/记忆</th>
<th nowrap>反馈/自改进</th>
<th nowrap>执行接口</th>
<th nowrap>验证环境</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICRA 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2510.16281">Do What You Say: Grounding Language-Conditioned Robotic Actions with Vision-Language Models</a></td>
<td nowrap>该方法运行时检查 VLA 文本推理和动作结果是否一致，再选择是否执行动作。</td>
<td nowrap>Failure Monitor</td>
<td nowrap>VLM reasoning checker</td>
<td nowrap>reasoning-action consistency</td>
<td nowrap>VLA action selection</td>
<td nowrap>Real robot manipulation</td>
<td nowrap>检测“说的计划”和“做的动作”是否一致。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.16281">paper</a></td>
<td nowrap><a href="https://yilin-wu98.github.io/steering-reasoning-vla/">project</a></td>
<td nowrap><a href="https://github.com/NVlabs/actalign">code</a></td>
<td nowrap><a href="https://github.com/NVlabs/actalign">data</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=N22lDHYrXe">Experience-based Knowledge Correction for Robust Planning in Minecraft</a></td>
<td nowrap>XENON 从经验中修正依赖图和行动知识，提高 Minecraft 长程规划鲁棒性。</td>
<td nowrap>失败监控</td>
<td nowrap>experience-based knowledge correction</td>
<td nowrap>失败监控</td>
<td nowrap>failure monitor</td>
<td nowrap>Minecraft</td>
<td nowrap>解决 LLM 初始知识错误且难通过反馈修正的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=N22lDHYrXe">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=WC6MJ5r5Bj">ReCAPA: Hierarchical Predictive Correction to Mitigate Cascading Failures</a></td>
<td nowrap>ReCAPA 在动作、子目标、轨迹三层预测并校正偏差以抑制级联失败。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>hierarchical predictive correction</td>
<td nowrap>failure monitor</td>
<td nowrap>-</td>
<td nowrap>解决多步 VLA 执行中局部错误向后传播的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2604.21232">paper</a></td>
<td nowrap><a href="https://sunandreas0437-svg.github.io/recapa-project-page/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=jr9hGWQioP">Self-Refining Vision Language Model for Robotic Failure Detection and Reasoning</a></td>
<td nowrap>ARMOR 将失败检测和自然语言原因解释建模为多轮自细化任务。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>self-refinement</td>
<td nowrap>failure monitor</td>
<td nowrap>-</td>
<td nowrap>解决真实机器人失败微妙、组合多且标注稀缺的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.12405">paper</a></td>
<td nowrap><a href="https://sites.google.com/utexas.edu/armor">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61750">Sentinel-VLA: A Metacognitive VLA Model with Active Status Monitoring for Dynamic Reasoning and Error Recovery</a></td>
<td nowrap>加入主动状态监控，使 VLA 模型能发现执行问题并触发恢复推理。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>失败监控</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>发现并修复执行失败</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61750">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63650">NeurVLA: Unleashing Failure-Handling Capability of Vision-Language-Action Models via Neural-Symbolic Reasoning</a></td>
<td nowrap>用神经符号推理诊断失败，并提升 VLA 操作策略的恢复能力。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>失败监控</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63650">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64203">Can VLMs Diagnose and Recover from VLA Manipulation Faults?</a></td>
<td nowrap>评估 VLM 是否能诊断操作故障，并为失败的 VLA 执行提供恢复指导。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>失败监控</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64203">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.09459">Failure Prediction at Runtime for Generative Robot Policies</a></td>
<td nowrap>FIPER 在无需失败数据的情况下预测生成式模仿策略运行时失败。</td>
<td nowrap>失败监控</td>
<td nowrap>-</td>
<td nowrap>runtime failure prediction</td>
<td nowrap>failure monitor</td>
<td nowrap>-</td>
<td nowrap>解决扩散/flow 操作策略部署时早期失败预测。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.09459">paper</a></td>
<td nowrap><a href="https://tum-lsy.github.io/fiper_website">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04455">Code-as-Monitor: Constraint-aware Visual Programming for Reactive and Proactive Robotic Failure Detection</a></td>
<td nowrap>用 VLM 生成约束监控代码，同时做反应式和预防式失败检测。</td>
<td nowrap>失败监控</td>
<td nowrap>VLM-generated monitor code + constraint elements</td>
<td nowrap>失败监控</td>
<td nowrap>closed-loop monitor over open-loop policy</td>
<td nowrap>CLIPort, OmniGibson, real-world</td>
<td nowrap>解决开集机器人失败的实时检测和预防。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.04455">paper</a></td>
<td nowrap><a href="https://zhoues.github.io/Code-as-Monitor/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### constraint / affordance planning

共 10 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>规划粒度</th>
<th nowrap>工具/记忆</th>
<th nowrap>反馈/自改进</th>
<th nowrap>执行接口</th>
<th nowrap>验证环境</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2408.14769">Points2Plans: From Point Clouds to Long-Horizon Plans with Composable Relational Dynamics</a></td>
<td nowrap>Points2Plans 从点云和语言指令出发，用关系动力学连接高层计划和连续参数规划。</td>
<td nowrap>Constraint / Affordance Planning</td>
<td nowrap>point-cloud relational dynamics</td>
<td nowrap>composable planning feedback</td>
<td nowrap>continuous parameter planner</td>
<td nowrap>Sim + Real</td>
<td nowrap>把语言计划落到可执行的 3D 关系动力学约束。</td>
<td nowrap><a href="https://arxiv.org/abs/2408.14769">paper</a></td>
<td nowrap><a href="https://sites.google.com/stanford.edu/points2plans">project</a></td>
<td nowrap><a href="https://github.com/yixuanhuang98/Points2Plans">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=enprG5H9aD">SLAP: Shortcut Learning for Abstract Planning</a></td>
<td nowrap>SLAP 从已有 TAMP 选项中自动发现低层 shortcut option。</td>
<td nowrap>TAMP option/shortcut learning</td>
<td nowrap>-</td>
<td nowrap>约束/affordance</td>
<td nowrap>planning / affordance</td>
<td nowrap>-</td>
<td nowrap>解决 TAMP 抽象动作依赖人工定义、行为空间受限的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=enprG5H9aD">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=kWCNhRdcDI">Natural Language PDDL (NL-PDDL) for Open-world Goal-oriented Commonsense Regression Planning in Embodied AI</a></td>
<td nowrap>用自然语言 PDDL 做开放世界目标回归规划。</td>
<td nowrap>commonsense regression planning</td>
<td nowrap>NL-PDDL</td>
<td nowrap>约束/affordance</td>
<td nowrap>planning / affordance</td>
<td nowrap>-</td>
<td nowrap>解决开放世界中部分可观测和知识不完整下的长程因果规划。</td>
<td nowrap><a href="https://openreview.net/forum?id=kWCNhRdcDI">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=refcXHU1Nh">SafeFlowMatcher: Safe and Fast Planning using Flow Matching with Control Barrier Functions</a></td>
<td nowrap>将 flow matching 规划器与控制屏障函数结合，保证快速且安全。</td>
<td nowrap>约束/affordance</td>
<td nowrap>CBF safety constraints</td>
<td nowrap>prediction-correction integrator</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决生成式路径规划缺少形式化安全约束的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=refcXHU1Nh">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=bGPDviEtZ1">MoMaGen: Generating Demonstrations under Soft and Hard Constraints for Multi-Step Bimanual Mobile Manipulation</a></td>
<td nowrap>在软硬约束下自动生成多步双臂移动操作示范。</td>
<td nowrap>constraint-conditioned demonstration generation</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / affordance</td>
<td nowrap>-</td>
<td nowrap>解决多步双臂移动操作示范采集成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=bGPDviEtZ1">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38907">A3D: Adaptive Affordance Assembly with Dual-Arm Manipulation</a></td>
<td nowrap>学习双臂装配中的自适应 affordance，并随物体和任务状态变化更新操作选择。</td>
<td nowrap>约束/affordance</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>planning / affordance</td>
<td nowrap>-</td>
<td nowrap>dual-arm adaptive affordance assembly</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38907">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38909">Affordance-Guided Coarse-to-Fine Exploration for Base Placement in Open-Vocabulary Mobile Manipulation</a></td>
<td nowrap>用 affordance 先验引导移动操作底座放置，再通过由粗到细的可行性细化确定位置。</td>
<td nowrap>coarse-to-fine base placement</td>
<td nowrap>affordance guidance</td>
<td nowrap>-</td>
<td nowrap>planning / affordance</td>
<td nowrap>-</td>
<td nowrap>用 affordance 指导开放词汇移动操作中的底盘放置探索。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38909">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38955">Gentle Manipulation Policy Learning via Demonstrations from VLM Planned Atomic Skills</a></td>
<td nowrap>用 VLM 规划的原子技能作为示范，学习温和的长程操作策略。</td>
<td nowrap>约束/affordance</td>
<td nowrap>VLM-planned atomic skills</td>
<td nowrap>-</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>gentle manipulation policy learning</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38955">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=wr47LsSUjH">InstructFlow: Adaptive Symbolic Constraint-Guided Code Generation for Long-Horizon Planning</a></td>
<td nowrap>InstructFlow 用符号反馈流把失败诱导出的约束注入指令图和代码生成。</td>
<td nowrap>约束/affordance</td>
<td nowrap>约束/affordance</td>
<td nowrap>failure diagnosis + symbolic constraints</td>
<td nowrap>flow matching / planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决 LLM 长程规划代码幻觉、物理不可行和失败恢复差的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=wr47LsSUjH">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/chiht21/InstructFlow">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/542">CoA-VLA: Improving Vision-Language-Action Models via Visual-Text Chain-of-Affordance</a></td>
<td nowrap>用视觉-文本可供性链在测试时增强 VLA 推理。</td>
<td nowrap>约束/affordance</td>
<td nowrap>-</td>
<td nowrap>test-time affordance reasoning</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 自驱动 affordance 推理和鲁棒行动不足。</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2025/papers/Li_CoA-VLA_Improving_Vision-Language-Action_Models_via_Visual-Text_Chain-of-Affordance_ICCV_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### self-improving planning

共 32 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>规划粒度</th>
<th nowrap>工具/记忆</th>
<th nowrap>反馈/自改进</th>
<th nowrap>执行接口</th>
<th nowrap>验证环境</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=SzUgx5r3wy">Self-Improving Loops for Visual Robotic Planning</a></td>
<td nowrap>让视觉机器人规划器通过在线自收集行为持续改进。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>self-improving online loop</td>
<td nowrap>planning / reasoning / RL</td>
<td nowrap>-</td>
<td nowrap>解决视觉生成规划器对未见任务泛化不足的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=SzUgx5r3wy">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Vsy3nAnaX6">BOLT: Decision‑Aligned Distillation and Budget-Aware Routing for Constrained Multimodal QA on Robots</a></td>
<td nowrap>通过决策对齐蒸馏和预算感知路由满足机器人多模态 QA 约束。</td>
<td nowrap>constrained multimodal QA routing</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning / RL</td>
<td nowrap>-</td>
<td nowrap>机器人约束下决策质量与效率</td>
<td nowrap><a href="https://openreview.net/forum?id=Vsy3nAnaX6">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=eJcCW9oNfH">EVLP: Learning Unified Embodied Vision-Language Planner with Reinforced Supervised Fine-Tuning</a></td>
<td nowrap>EVLP 统一生成语言推理和视觉想象，并用强化监督微调学习规划。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>reinforced supervised fine-tuning</td>
<td nowrap>embodied vision-language planner</td>
<td nowrap>-</td>
<td nowrap>解决长程操作中语言逻辑和视觉空间规划不一致。</td>
<td nowrap><a href="https://openreview.net/forum?id=eJcCW9oNfH">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=i5wlozMFsQ">Embodied-R1: Reinforced Embodied Reasoning for General Robotic Manipulation</a></td>
<td nowrap>用 pointing 作为本体无关中间表示训练 3B 具身推理 VLM。</td>
<td nowrap>embodied reasoning/pointing</td>
<td nowrap>-</td>
<td nowrap>reinforced reasoning</td>
<td nowrap>planning / reasoning / RL</td>
<td nowrap>-</td>
<td nowrap>解决高层视觉语言理解与低层动作原语之间的 seeing-to-doing gap。</td>
<td nowrap><a href="https://openreview.net/forum?id=i5wlozMFsQ">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38922">ManipLVM-R1: Reinforcement Learning for Reasoning in Embodied Manipulation with Large Vision-Language Models</a></td>
<td nowrap>用强化学习提升大视觉语言模型的 affordance 推理和具身操作规划能力。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>RL for embodied manipulation reasoning</td>
<td nowrap>planning / reasoning / RL</td>
<td nowrap>-</td>
<td nowrap>用强化学习提升大视觉语言模型的具身操作推理。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38922">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61922">HALO: A Unified Vision-Language-Action Model for Embodied Multimodal Chain-of-Thought Reasoning</a></td>
<td nowrap>把语言推理、视觉预测与动作生成统一为具身 VLA 控制中的多模态 Chain-of-Thought。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61922">paper</a> / <a href="https://arxiv.org/abs/2506.19850">paper</a></td>
<td nowrap><a href="https://robertwyq.github.io/univla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/baaivision/UniVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64290">Latent Reasoning VLA: Latent Thinking and Prediction for Vision-Language-Action Models</a></td>
<td nowrap>LaRA-VLA 把多模态 CoT 内化为连续潜变量，降低推理延迟。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决显式 CoT 推理开销大且离散表示不适合连续控制的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.01166">paper</a></td>
<td nowrap><a href="https://loveju1y.github.io/Latent-Reasoning-VLA/">project</a></td>
<td nowrap><a href="https://github.com/LoveJu1y/LaRA-VLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61887">LaST0: Latent Spatio-Temporal Chain-of-Thought for Robotic Vision-Language-Action Model</a></td>
<td nowrap>把推理表示为潜在时空 Chain-of-Thought，以较低显式推理成本提升机器人 VLA 规划。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>用潜在时空 CoT 支持机器人 VLA 推理。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61887">paper</a></td>
<td nowrap><a href="https://vla-last0.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60801">LAGEA: Language Guided Embodied Agents for Robotic Manipulation</a></td>
<td nowrap>用语言指导和反馈，让具身操作智能体在不同任务间自适应。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60801">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64055">Drift is a Sampling Error: SNR-Aware Power Distributions for Long-Horizon Robotic Planning</a></td>
<td nowrap>将规划漂移视为推理时采样问题，并用 SNR 感知的幂分布支持长程规划。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>通过反馈自我改进规划</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64055">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2601.11404">ACoT-VLA: Action Chain-of-Thought for Vision-Language-Action Models</a></td>
<td nowrap>提出 Action CoT，把细粒度动作推理直接作为 VLA 中间表示。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决语言/视觉中间推理不能充分传达精细动作信息的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2601.11404">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>Reasoning2Action-Sim</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2601.09708">Fast-ThinkAct: Efficient Vision-Language-Action Reasoning via Verbalizable Latent Planning</a></td>
<td nowrap>用可语言化潜在规划蒸馏显式 CoT，在保持性能时降低延迟。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决推理型 VLA 的显式 CoT 过长导致执行慢的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2601.09708">paper</a></td>
<td nowrap><a href="https://jasper0314-huang.github.io/fast-thinkact/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.01953">Fast-in-Slow: A Dual-System VLA Model Unifying Fast Manipulation within Slow Reasoning</a></td>
<td nowrap>用慢速 VLM 推理和高速动作模块组成双系统 VLA。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>dual-system VLA: slow reasoning + high-frequency action module</td>
<td nowrap>RLBench + AlphaBot/Agilex实机</td>
<td nowrap>解决复杂操作中高层推理和高频控制难兼顾的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.01953">paper</a></td>
<td nowrap><a href="https://fast-in-slow.github.io/">project</a></td>
<td nowrap><a href="https://github.com/CHEN-H01/Fast-in-Slow">code</a></td>
<td nowrap><a href="https://huggingface.co/chenhao01/fisvla/tree/main">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.21906">ChatVLA-2: Vision-Language-Action Model with Open-World Embodied Reasoning from Pretrained Knowledge</a></td>
<td nowrap>保留预训练 VLM 的开放世界知识并转化为可执行动作。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 微调后丢失开放世界推理能力的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.21906">paper</a></td>
<td nowrap><a href="https://chatvla-2.github.io/">project</a></td>
<td nowrap><a href="https://github.com/tutujingyugang1/ChatVLA_public">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.17561">VLA-OS: Structuring and Dissecting Planning Representations and Paradigms in Vision-Language-Action Models</a></td>
<td nowrap>系统比较 VLA 中任务规划表示、范式和数据来源对性能的影响。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>LIBERO、Colosseum、FurnitureBench、DexArt等</td>
<td nowrap>解决 VLA 规划改进来源难以归因的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.17561">paper</a></td>
<td nowrap><a href="https://nus-lins-lab.github.io/vlaos/">project</a></td>
<td nowrap><a href="https://github.com/HeegerGao/VLA-OS">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/Linslab/VLA-OS-Dataset">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.16815">ThinkAct: Vision-Language-Action Reasoning via Reinforced Visual Latent Planning</a></td>
<td nowrap>用动作对齐视觉奖励强化高层视觉潜在规划。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>reinforced visual latent planning</td>
<td nowrap>VLA/action</td>
<td nowrap>SimplerEnv, LIBERO, EgoPlan-Bench2, RoboVQA, OpenEQA</td>
<td nowrap>解决 VLA 缺少显式多步推理和复杂任务适应能力的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.16815">paper</a> / <a href="https://neurips.cc/virtual/2025/loc/san-diego/poster/119747">paper</a></td>
<td nowrap><a href="https://jasper0314-huang.github.io/thinkact-vla/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.15155">Self-Improving Embodied Foundation Models</a></td>
<td nowrap>用 steps-to-go 预测产生奖励和成功检测器，让机器人自我练习改进。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>online RL with self-predicted reward + success detector</td>
<td nowrap>VLA/action</td>
<td nowrap>Simulated/Real-World LanguageTable, Aloha, BananaTable/Real2Sim</td>
<td nowrap>解决具身基础模型低层控制主要依赖行为克隆的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.15155">paper</a> / <a href="https://arxiv.org/pdf/2509.15155">paper</a> / <a href="https://neurips.cc/virtual/2025/loc/san-diego/poster/118633">paper</a></td>
<td nowrap><a href="https://self-improving-efms.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.09990">Chain-of-Action: Trajectory Autoregressive Modeling for Robotic Manipulation</a></td>
<td nowrap>通过反向动作级 CoT 自回归生成完整操作轨迹。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>action-level CoT/backward trajectory reasoning</td>
<td nowrap>closed-loop reverse autoregressive trajectory generation</td>
<td nowrap>需补</td>
<td nowrap>解决直接前向预测动作缺少全局目标约束的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.09990">paper</a></td>
<td nowrap><a href="https://chain-of-action.github.io/">project</a></td>
<td nowrap><a href="https://github.com/ByteDance-Seed/Chain-of-Action">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/Solomonz/Chain-of-Action">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.08044">Towards Reliable LLM-based Robot Planning via Combined Uncertainty Estimation</a></td>
<td nowrap>CURE 分解认知和内在不确定性，提高 LLM 机器人规划可靠性。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>combined uncertainty estimation</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决 LLM 幻觉导致的过度自信、不安全计划。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.08044">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.00833">HumanoidGen: Data Generation for Bimanual Dexterous Manipulation via LLM Reasoning</a></td>
<td nowrap>用原子灵巧操作和 LLM 推理自动生成双臂灵巧操作任务与示范。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>reasoning</td>
<td nowrap>20 tabletop bimanual dexterous tasks; DP/DP3 deployment</td>
<td nowrap>解决人形双臂灵巧操作仿真任务和高质量数据缺乏。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.00833">paper</a> / <a href="https://arxiv.org/pdf/2507.00833">paper</a></td>
<td nowrap><a href="https://openhumanoidgen.github.io/">project</a></td>
<td nowrap><a href="https://github.com/TeleHuman/HumanoidGen">code</a></td>
<td nowrap>humanoidgen_dataset/model</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.23829">DexFlyWheel: A Scalable and Self-improving Data Generation Framework for Dexterous Manipulation</a></td>
<td nowrap>用 IL、RL 和数据筛选闭环持续扩展灵巧操作数据。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>self-improving data generation flywheel</td>
<td nowrap>self-improving planner</td>
<td nowrap>-</td>
<td nowrap>解决灵巧操作数据规模、多样性和泛化不足。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.23829">paper</a></td>
<td nowrap><a href="https://dexflywheel.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.18276">Adaptive Articulated Object Manipulation On The Fly with Foundation Model Reasoning and Part Grounding</a></td>
<td nowrap>AdaRPG 结合基础模型推理和部件 grounding 自适应操作关节物体。</td>
<td nowrap>adaptive articulated object manipulation</td>
<td nowrap>foundation reasoning + part grounding</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决关节物体结构不可见、功能机制差异大的自适应操作。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.18276">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.01709">RoBridge: A Hierarchical Architecture Bridging Cognition and Execution for General Robotic Manipulation</a></td>
<td nowrap>RoBridge 用高层认知规划器和低层执行模块桥接开放环境操作。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning</td>
<td nowrap>-</td>
<td nowrap>解决通用操作中认知能力和执行技能难兼顾的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.01709">paper</a></td>
<td nowrap><a href="https://abliao.github.io/RoBridge/">project</a></td>
<td nowrap><a href="https://github.com/abliao/RoBridge">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.06861">Efficient Robotic Policy Learning via Latent Space Backward Planning</a></td>
<td nowrap>在潜空间反向规划粗粒度子目标，提高策略学习效率和准确性。</td>
<td nowrap>latent-space backward planning</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决像素级世界模型规划计算贵且误差累积的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.06861">paper</a></td>
<td nowrap><a href="https://lbp-authors.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Dstate/LBP">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2410.01440">Closed-Loop Long-Horizon Robotic Planning via Equilibrium Sequence Modeling</a></td>
<td nowrap>用 equilibrium sequence modeling 在反馈下迭代细化计划，实现闭环长程机器人规划。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>用 equilibrium sequence modeling 做闭环长程机器人规划。</td>
<td nowrap><a href="https://arxiv.org/abs/2410.01440">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/Singularity0104/equilibrium-planner">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2407.04281">WOMD-Reasoning: A Large-Scale Dataset for Interaction Reasoning in Driving</a></td>
<td nowrap>基于 Waymo Open Motion Dataset 构建交通交互推理 QA 数据集。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>Sim/Benchmark</td>
<td nowrap>解决自动驾驶场景中规则触发交互推理数据缺乏。</td>
<td nowrap><a href="https://arxiv.org/abs/2407.04281">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/yhli123/WOMD-Reasoning">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/33233">CoT-VLA: Visual Chain-of-Thought Reasoning for Vision-Language-Action Models</a></td>
<td nowrap>在动作前预测视觉 Chain-of-Thought 子目标，提升 VLA 模型的时序推理与泛化。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>Franka-Tabletop、LIBERO、Bridge V2确认</td>
<td nowrap>用视觉 CoT 提升 VLA 的操作泛化和长程推理。</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/33233">paper</a></td>
<td nowrap><a href="https://cot-vla.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18562">DexHandDiff: Interaction-aware Diffusion Planning for Adaptive Dexterous Manipulation</a></td>
<td nowrap>用交互感知双阶段扩散规划建模接触前对齐和接触后控制。</td>
<td nowrap>interaction-aware diffusion planning</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>VLA/action</td>
<td nowrap>-</td>
<td nowrap>解决灵巧操作扩散规划中的 ghost state 和复杂接触适应性。</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18562">paper</a></td>
<td nowrap><a href="https://dexdiffuser.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2502.21257">RoboBrain: A Unified Brain Model for Robotic Manipulation from Abstract to Concrete</a></td>
<td nowrap>RoboBrain 统一规划、affordance 感知和轨迹预测三类机器人脑能力。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决 MLLM 在长程操作中缺少抽象到具体的机器人能力。</td>
<td nowrap><a href="https://arxiv.org/abs/2502.21257">paper</a></td>
<td nowrap><a href="https://superrobobrain.github.io/robobrainv1/index.html">project</a></td>
<td nowrap><a href="https://github.com/FlagOpen/RoboBrain">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/BAAI/ShareRobot">hf</a></td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08481">PhysVLM: Enabling Visual Language Models to Understand Robotic Physical Reachability</a></td>
<td nowrap>用 S-P Map 把不同机器人可达性编码进 VLM 视觉推理。</td>
<td nowrap>physical reachability reasoning</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>机器人可达性理解</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08481">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.16537">RoboSpatial: Teaching Spatial Understanding to 2D and 3D Vision-Language Models for Robotics</a></td>
<td nowrap>构建 RoboSpatial 训练/评测 2D 和 3D VLM 的机器人空间理解。</td>
<td nowrap>robot spatial understanding</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning / 3D representation</td>
<td nowrap>-</td>
<td nowrap>解决通用视觉语言数据缺少机器人所需空间推理。</td>
<td nowrap><a href="https://arxiv.org/abs/2411.16537">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>RoboSpatial</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_Tartan_IMU_A_Light_Foundation_Model_for_Inertial_Positioning_in_CVPR_2025_paper.pdf">Tartan IMU: A Light Foundation Model for Inertial Positioning in Robotics</a></td>
<td nowrap>预训练轻量 IMU 基础模型并通过适配器用于惯性定位。</td>
<td nowrap>自改进规划</td>
<td nowrap>-</td>
<td nowrap>自改进规划</td>
<td nowrap>planning / reasoning</td>
<td nowrap>-</td>
<td nowrap>解决机器人惯性定位中跨运动主体和场景泛化不足。</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_Tartan_IMU_A_Light_Foundation_Model_for_Inertial_Positioning_in_CVPR_2025_paper.pdf">paper</a></td>
<td nowrap><a href="https://superodometry.com/tartanimu">project</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://huggingface.co/datasets/raphael-blanchard/TartanIMU">hf</a></td>
</tr>
</tbody>
</table>

### 本体扩展 / 灵巧操作

本体扩展决定具身智能是否能从单机械臂走向人形、双臂、灵巧手和触觉接触任务。表中论文体现了动作空间、传感方式和控制目标随本体变化而复杂化。

子方向：humanoid、bimanual、dexterous hand、tactile/contact-rich、grasp。

共 89 篇。

<table>
<thead>
<tr>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>观察重点</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>humanoid</td>
<td nowrap>32</td>
<td nowrap>看全身控制、移动操作和人形本体泛化。</td>
</tr>
<tr>
<td nowrap>bimanual</td>
<td nowrap>13</td>
<td nowrap>看双臂协同、长程操作和协调控制。</td>
</tr>
<tr>
<td nowrap>dexterous hand</td>
<td nowrap>31</td>
<td nowrap>看灵巧手动作空间和抓取迁移。</td>
</tr>
<tr>
<td nowrap>tactile/contact-rich</td>
<td nowrap>13</td>
<td nowrap>看触觉、接触动力学和精细反馈。</td>
</tr>
</tbody>
</table>

#### humanoid

共 32 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>本体类型</th>
<th nowrap>传感/接触</th>
<th nowrap>控制接口</th>
<th nowrap>训练方式</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/html/Pan_TokenHSI_Unified_Synthesis_of_Physical_Human-Scene_Interactions_through_Task_Tokenization_CVPR_2025_paper.html">TokenHSI: Unified Synthesis of Physical Human-Scene Interactions through Task Tokenization</a></td>
<td nowrap>TokenHSI synthesizes physical human-scene interactions through task tokenization.</td>
<td nowrap>Humanoid / human-scene interaction</td>
<td nowrap>body-scene contact</td>
<td nowrap>whole-body motion</td>
<td nowrap>task-tokenized motion synthesis</td>
<td nowrap>Simulation</td>
<td nowrap>Synthesize task-conditioned physical human-scene interaction.</td>
<td nowrap><a href="https://arxiv.org/abs/2503.19901">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Xu_InterMimic_Towards_Universal_Whole-Body_Control_for_Physics-Based_Human-Object_Interactions_CVPR_2025_paper.pdf">InterMimic: Towards Universal Whole-Body Control for Physics-Based Human-Object Interactions</a></td>
<td nowrap>InterMimic studies universal whole-body control for physics-based human-object interaction.</td>
<td nowrap>Humanoid / whole-body control</td>
<td nowrap>body-object contact</td>
<td nowrap>whole-body controller</td>
<td nowrap>physics-based imitation</td>
<td nowrap>Simulation</td>
<td nowrap>Control human-object interactions with whole-body dynamics.</td>
<td nowrap><a href="https://arxiv.org/abs/2502.20390">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=pZISppZSTv">CLoSD: Closing the Loop between Simulation and Diffusion for multi-task character control</a></td>
<td nowrap>CLoSD closes the loop between simulation and diffusion models for multitask character control.</td>
<td nowrap>Humanoid / character control</td>
<td nowrap>whole-body state</td>
<td nowrap>diffusion control</td>
<td nowrap>simulation + diffusion</td>
<td nowrap>Simulation</td>
<td nowrap>Use diffusion and simulation together for multitask whole-body control.</td>
<td nowrap><a href="https://arxiv.org/abs/2410.03441">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://openreview.net/forum?id=1vCnDyQkjg">Unified Human-Scene Interaction via Prompted Chain-of-Contacts</a></td>
<td nowrap>This work models human-scene interaction through prompted chains of contact states.</td>
<td nowrap>Humanoid / human-scene interaction</td>
<td nowrap>contact sequence</td>
<td nowrap>whole-body motion</td>
<td nowrap>prompted contact planning</td>
<td nowrap>Simulation</td>
<td nowrap>Generate human-scene interaction from contact chains.</td>
<td nowrap><a href="https://arxiv.org/abs/2309.07918">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2024</td>
<td nowrap><a href="https://proceedings.iclr.cc/paper_files/paper/2024/hash/7827290f07f63485b849b66cfa3e5dd0-Abstract-Conference.html">OmniControl: Control Any Joint at Any Time for Human Motion Generation</a></td>
<td nowrap>OmniControl controls arbitrary joints at arbitrary times for human motion generation.</td>
<td nowrap>Humanoid / motion control</td>
<td nowrap>joint constraints</td>
<td nowrap>joint-level motion control</td>
<td nowrap>controllable motion generation</td>
<td nowrap>Motion benchmarks</td>
<td nowrap>Generate controllable whole-body motion from sparse joint constraints.</td>
<td nowrap><a href="https://arxiv.org/abs/2310.08580">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2023</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2023/html/Karunratanakul_Guided_Motion_Diffusion_for_Controllable_Human_Motion_Synthesis_ICCV_2023_paper.html">Guided Motion Diffusion for Controllable Human Motion Synthesis</a></td>
<td nowrap>Guided Motion Diffusion enables controllable human motion synthesis through diffusion guidance.</td>
<td nowrap>Humanoid / motion generation</td>
<td nowrap>whole-body motion</td>
<td nowrap>guided motion diffusion</td>
<td nowrap>diffusion synthesis</td>
<td nowrap>Motion benchmarks</td>
<td nowrap>Control generated human motion through guidance signals.</td>
<td nowrap><a href="https://arxiv.org/abs/2305.12577">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2023</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2023/html/Yuan_PhysDiff_Physics-Guided_Human_Motion_Diffusion_Model_ICCV_2023_paper.html">PhysDiff: Physics-Guided Human Motion Diffusion Model</a></td>
<td nowrap>PhysDiff adds physics guidance to human motion diffusion for more plausible motion.</td>
<td nowrap>Humanoid / motion generation</td>
<td nowrap>physics constraints</td>
<td nowrap>motion diffusion</td>
<td nowrap>physics-guided generation</td>
<td nowrap>Motion benchmarks</td>
<td nowrap>Improve physical plausibility of generated whole-body motion.</td>
<td nowrap><a href="https://arxiv.org/abs/2212.02500">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2024</td>
<td nowrap><a href="https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/00194.pdf">MANIKIN: Biomechanically Accurate Neural Inverse Kinematics for Human Motion Estimation</a></td>
<td nowrap>MANIKIN estimates human motion with biomechanically accurate neural inverse kinematics.</td>
<td nowrap>Humanoid / motion estimation</td>
<td nowrap>body kinematics</td>
<td nowrap>inverse kinematics</td>
<td nowrap>neural IK</td>
<td nowrap>Motion benchmarks</td>
<td nowrap>Estimate physically plausible human motion from sparse observations.</td>
<td nowrap><a href="https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/00194.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2308.06493">EgoPoser: Robust Real-Time Egocentric Pose Estimation from Sparse and Intermittent Observations Everywhere</a></td>
<td nowrap>EgoPoser performs robust real-time egocentric pose estimation from sparse intermittent observations.</td>
<td nowrap>Humanoid / pose estimation</td>
<td nowrap>egocentric sparse sensing</td>
<td nowrap>pose estimation</td>
<td nowrap>real-time egocentric inference</td>
<td nowrap>Motion benchmarks</td>
<td nowrap>Recover whole-body pose from sparse egocentric observations.</td>
<td nowrap><a href="https://arxiv.org/abs/2308.06493">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2022</td>
<td nowrap><a href="https://arxiv.org/abs/2207.13784">AvatarPoser: Articulated Full-Body Pose Tracking from Sparse Motion Sensing</a></td>
<td nowrap>AvatarPoser tracks full-body articulated pose from sparse motion sensors.</td>
<td nowrap>Humanoid / pose tracking</td>
<td nowrap>sparse motion sensors</td>
<td nowrap>full-body pose tracking</td>
<td nowrap>sparse-sensing inference</td>
<td nowrap>Motion benchmarks</td>
<td nowrap>Track full-body pose from sparse wearable sensing.</td>
<td nowrap><a href="https://arxiv.org/abs/2207.13784">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2510.08807">Humanoid Everyday: A Comprehensive Robotic Dataset for Open-World Humanoid Manipulation</a></td>
<td nowrap>Humanoid Everyday 提供 260 类开放世界人形操作任务，覆盖移动、交互、操作和多模态传感。</td>
<td nowrap>Humanoid</td>
<td nowrap>RGB-D / LiDAR / tactile / language</td>
<td nowrap>whole-body manipulation</td>
<td nowrap>large-scale dataset / benchmark</td>
<td nowrap>Real</td>
<td nowrap>补足人形机器人开放世界操作数据和评测。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.08807">paper</a></td>
<td nowrap><a href="https://humanoideveryday.github.io/">project</a></td>
<td nowrap><a href="https://github.com/physical-superintelligence-lab/Humanoid-Everyday">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/USC-PSI-Lab/humanoid-everyday">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=OCJmVjyzN7">WholeBodyVLA: Towards Unified Latent VLA for Whole-body Loco-manipulation Control</a></td>
<td nowrap>从自我中心视频学习统一潜变量 VLA，让人形机器人执行大空间视觉语言全身移动操作。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>视觉+语言+本体状态</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>action-free egocentric video latent VLA + RL controller</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决人形 loco-manipulation 中操作感知移动、数据稀缺和低层控制不稳的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=OCJmVjyzN7">paper</a></td>
<td nowrap><a href="https://opendrivelab.com/WholeBodyVLA/">project</a></td>
<td nowrap><a href="https://github.com/OpenDriveLab/WholebodyVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=aQWSEjcN9V">Endowing GPT-4 with a Humanoid Body: Building the Bridge Between Off-the-Shelf VLMs and the Physical World</a></td>
<td nowrap>BiBo 用现成 VLM 将高层指令编译为低层控制参数，并用扩散运动执行器驱动人形体。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>视觉+语言+物理反馈</td>
<td nowrap>VLM instruction compiler + diffusion motion executor</td>
<td nowrap>off-the-shelf VLM + diffusion executor</td>
<td nowrap>-</td>
<td nowrap>解决无需额外微调数据时如何让 GPT-4/VLM 控制人形智能体。</td>
<td nowrap><a href="https://openreview.net/forum?id=aQWSEjcN9V">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=3UE3Aatcjy">HWC-Loco: A Hierarchical Whole-Body Control Approach to Robust Humanoid Locomotion</a></td>
<td nowrap>HWC-Loco 将人形运动控制建模为鲁棒优化，并用层级策略在安全恢复和目标跟踪间动态权衡。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>hierarchical robust whole-body RL/control</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决训练部署差异下人形机器人鲁棒全身行走控制问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=3UE3Aatcjy">paper</a></td>
<td nowrap><a href="https://simonlinsx.github.io/HWC_Loco/">project</a></td>
<td nowrap><a href="https://github.com/EDEM-AI/HWC_Loco">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=6T3wJQhvc3">Task Tokens: A Flexible Approach to Adapting Behavior Foundation Models</a></td>
<td nowrap>Task Tokens 冻结行为基础模型，仅训练任务 tokenizer/token 来低参数适配特定人形任务。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>-</td>
<td nowrap>task-token-conditioned behavior foundation model</td>
<td nowrap>frozen BFM + task-specific tokenizer</td>
<td nowrap>-</td>
<td nowrap>解决 BFM 对新任务依赖提示工程且适配效率低的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=6T3wJQhvc3">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=jkhl2oI0g5">BFM-Zero: A Promptable Behavioral Foundation Model for Humanoid Control Using Unsupervised Reinforcement Learning</a></td>
<td nowrap>BFM-Zero 通过无监督 RL 学共享潜空间，使单一人形策略可被运动、目标或奖励提示。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>本体状态/目标/奖励提示</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>unsupervised RL + Forward-Backward latent model</td>
<td nowrap>Sim + Real / Unitree G1</td>
<td nowrap>解决人形多任务全身控制中无需重训的 promptable generalist policy 问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=jkhl2oI0g5">paper</a></td>
<td nowrap><a href="https://lecar-lab.github.io/BFM-Zero/">project</a></td>
<td nowrap><a href="https://github.com/LeCAR-Lab/BFM-Zero">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=k3Cyx3Uets">From Language to Locomotion: Retargeting-free Humanoid Control via Motion Latent Guidance</a></td>
<td nowrap>RoboGhost 绕过人体动作解码和重定向，直接用语言条件运动潜变量生成可执行人形动作。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>-</td>
<td nowrap>language-conditioned motion latent + diffusion policy</td>
<td nowrap>retargeting-free diffusion action policy</td>
<td nowrap>-</td>
<td nowrap>解决自然语言到人形运动控制链路中重定向误差、高延迟和语义控制弱耦合问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=k3Cyx3Uets">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/gentlefress/RoboGhost">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=NEOTsyyYH7">Towards Bridging the Gap between Large-Scale Pretraining and Efficient Finetuning for Humanoid Control</a></td>
<td nowrap>LIFT 用大批量 SAC 做人形大规模预训练，再用模型辅助微调实现样本高效适配。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>off-policy SAC pretraining + model-based fine-tuning</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决人形控制中大规模预训练与新环境高效微调之间的断层。</td>
<td nowrap><a href="https://openreview.net/forum?id=NEOTsyyYH7">paper</a></td>
<td nowrap><a href="https://lift-humanoid.github.io/">project</a></td>
<td nowrap><a href="https://github.com/bigai-ai/LIFT-humanoid">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=eSkDNIGbcd">Hierarchical Value-Decomposed Offline Reinforcement Learning for Whole-Body Control</a></td>
<td nowrap>该文将全身控制分解为层级价值组件，使离线强化学习能够协调复杂的人形和足式机器人行为。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>触觉/接触</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>humanoid control</td>
<td nowrap>-</td>
<td nowrap>提升复杂本体控制</td>
<td nowrap><a href="https://openreview.net/forum?id=eSkDNIGbcd">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38908">Whole-Body Coordination for Dynamic Object Grasping with Legged Manipulators</a></td>
<td nowrap>该文协调移动与机械臂控制，使足式移动机械臂能够在动态场景中跟踪并抓取运动物体。</td>
<td nowrap>四足/足式移动底盘+机械臂</td>
<td nowrap>-</td>
<td nowrap>whole-body coordination for dynamic grasping</td>
<td nowrap>humanoid control</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决足式移动机械臂动态目标抓取时移动底盘和机械臂的全身协调问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38908">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38918">Coordinated Humanoid Robot Locomotion with Symmetry Equivariant Reinforcement Learning Policy</a></td>
<td nowrap>该文将对称等变性引入强化学习策略，以学习协调且可迁移的人形机器人行走控制。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>本体状态+足端接触</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>symmetry-equivariant DRL</td>
<td nowrap>Sim + Real / Unitree G1</td>
<td nowrap>解决人形机器人利用对称等变结构学习协调步态的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38918">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38924">FARM: Frame-Accelerated Augmentation and Residual Mixture-of-Experts for Physics-Based High-Dynamic Humanoid Control</a></td>
<td nowrap>FARM 结合帧加速动作增强和残差混合专家策略，用于训练物理仿真的高动态人形技能。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>frame-accelerated augmentation + residual MoE</td>
<td nowrap>-</td>
<td nowrap>解决物理仿真人形高动态技能控制中的数据增强和专家残差融合问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38924">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/Colin-Jing/FARM">code</a></td>
<td nowrap>HDHM data</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38927">ODYSSEY: Open-World Quadrupeds Exploration and Manipulation for Long-Horizon Tasks</a></td>
<td nowrap>ODYSSEY 面向开放世界长程四足任务，将探索与带臂足式机器人的操作能力结合起来。</td>
<td nowrap>四足机器人+机械臂</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>humanoid control</td>
<td nowrap>-</td>
<td nowrap>解决四足机器人在开放世界中长程探索和操作任务。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38927">paper</a></td>
<td nowrap><a href="https://kaijwang.github.io/odyssey.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38949">Keep On Going: Learning Robust Humanoid Motion Skills via Selective Adversarial Training</a></td>
<td nowrap>Keep On Going 通过选择性对抗训练提升人形运动技能在扰动下的鲁棒性和持续执行能力。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>selective adversarial training</td>
<td nowrap>-</td>
<td nowrap>解决人形运动技能在扰动下的鲁棒性和持续执行问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38949">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38951">Towards Adaptive Humanoid Control via Multi-Behavior Distillation and Reinforced Fine-Tuning</a></td>
<td nowrap>该文将多种人形行为蒸馏到统一策略中，并通过强化微调用于真实硬件适应。</td>
<td nowrap>人形/足式机器人</td>
<td nowrap>触觉/接触</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>multi-behavior distillation + reinforced fine-tuning</td>
<td nowrap>Sim + Real / Unitree G1</td>
<td nowrap>解决多行为人形控制策略蒸馏后在真实机器人上的适应性微调问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38951">paper</a></td>
<td nowrap><a href="https://ahc-humanoid.github.io">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62003">Scalable and General Whole-Body Control for Cross-Humanoid Locomotion</a></td>
<td nowrap>该文利用跨人形形态变化训练可扩展全身行走控制器，使其能迁移到多种人形机器人。</td>
<td nowrap>人形机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>cross-embodiment morphological randomization</td>
<td nowrap>12 simulated humanoids + 7 real robots</td>
<td nowrap>解决跨多种人形形态的可扩展通用全身行走控制问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62003">paper</a></td>
<td nowrap><a href="https://xhugwbc.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65120">Learning Transferable Interaction Primitives from Game Videos for Humanoids</a></td>
<td nowrap>该文从游戏视频中学习可复用的人形交互基元，将类人接触和物体交互技能迁移到机器人。</td>
<td nowrap>人形机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>humanoid control</td>
<td nowrap>-</td>
<td nowrap>提升人形机器人控制</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65120">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2511.15200">VIRAL: Visual Sim-to-Real at Scale for Humanoid Loco-Manipulation</a></td>
<td nowrap>VIRAL 在仿真中训练视觉学生策略并零样本部署到真实人形机器人，实现规模化视觉 sim-to-real loco-manipulation。</td>
<td nowrap>人形机器人</td>
<td nowrap>视觉</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>privileged RL teacher + visual student distillation + DAgger/BC</td>
<td nowrap>Sim training + Real zero-shot</td>
<td nowrap>解决人形机器人视觉移动操作技能难以从仿真迁移到真实硬件的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2511.15200">paper</a></td>
<td nowrap><a href="https://viral-humanoid.github.io/">project</a></td>
<td nowrap><a href="https://github.com/NVlabs/GR00T-VisualSim2Real">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2504.14305">Adversarial Locomotion and Motion Imitation for Humanoid Policy Learning</a></td>
<td nowrap>ALMI 通过上下半身对抗式学习，让下肢保持稳定行走、上肢跟踪多样动作。</td>
<td nowrap>人形机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>adversarial locomotion + motion imitation</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决人形机器人同时保持稳定移动和表达性全身动作模仿的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2504.14305">paper</a></td>
<td nowrap><a href="https://almi-humanoid.github.io/">project</a></td>
<td nowrap><a href="https://github.com/TeleHuman/ALMI-Open">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/TeleEmbodied/ALMI-X">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.12779">From Experts to a Generalist: Toward General Whole-Body Control for Humanoid Robots</a></td>
<td nowrap>BumbleBee 先聚类训练多专家，再结合真实数据适配并蒸馏为统一人形全身控制器。</td>
<td nowrap>人形机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>expert-generalist distillation + sim-to-real adaptation</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决多样敏捷人形动作之间控制需求冲突导致通用策略难训练的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.12779">paper</a></td>
<td nowrap><a href="https://beingbeyond.github.io/BumbleBee/">project</a></td>
<td nowrap><a href="https://github.com/BeingBeyond/BumbleBee">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://kungfubot.github.io/">KungfuBot: Physics-Based Humanoid Whole-Body Control for Learning Highly-Dynamic Skills</a></td>
<td nowrap>KungfuBot 通过动作处理、重定向和自适应跟踪课程，让人形机器人学习功夫和舞蹈等高动态技能。</td>
<td nowrap>人形机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>physics-based imitation + adaptive curriculum</td>
<td nowrap>-</td>
<td nowrap>解决现有全身动作模仿难以跟踪高速高动态人体动作的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.12851">paper</a></td>
<td nowrap><a href="https://kungfubot.github.io/">project</a></td>
<td nowrap><a href="https://github.com/TeleHuman/PBHC">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/34565">Let Humanoids Hike! Integrative Skill Development on Complex Trails</a></td>
<td nowrap>Let Humanoids Hike 将感知、移动和平衡控制结合起来，使人形机器人能够穿越复杂小径环境。</td>
<td nowrap>人形机器人</td>
<td nowrap>-</td>
<td nowrap>humanoid control / 人形/全身控制</td>
<td nowrap>humanoid control</td>
<td nowrap>-</td>
<td nowrap>解决人形机器人在复杂山路/小径上整合感知、移动和平衡技能的问题。</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/34565">paper</a></td>
<td nowrap><a href="https://lego-h-humanoidrobothiking.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### bimanual

共 13 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>本体类型</th>
<th nowrap>传感/接触</th>
<th nowrap>控制接口</th>
<th nowrap>训练方式</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=yAzN4tz7oI">RDT-1B: a Diffusion Foundation Model for Bimanual Manipulation</a></td>
<td nowrap>RDT-1B scales diffusion policy learning for bimanual robotic manipulation.</td>
<td nowrap>Bimanual manipulation</td>
<td nowrap>vision + proprioception</td>
<td nowrap>bimanual diffusion action</td>
<td nowrap>diffusion foundation model</td>
<td nowrap>Sim + Real</td>
<td nowrap>Train a large diffusion foundation model for bimanual manipulation.</td>
<td nowrap><a href="https://arxiv.org/pdf/2410.07864">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://dexmimicgen.github.io/">DexMimicGen: Automated Data Generation for Bimanual Dexterous Manipulation via Imitation Learning</a></td>
<td nowrap>DexMimicGen 从少量人类示教自动生成大规模双臂灵巧操作 demonstrations，并覆盖 sim/real。</td>
<td nowrap>Bimanual dexterous manipulation</td>
<td nowrap>vision + proprioception</td>
<td nowrap>bimanual action</td>
<td nowrap>imitation data generation</td>
<td nowrap>Sim + Real</td>
<td nowrap>降低双臂灵巧操作示教数据采集成本。</td>
<td nowrap><a href="https://dexmimicgen.github.io/">paper</a></td>
<td nowrap><a href="https://dexmimicgen.github.io/">project</a></td>
<td nowrap><a href="https://github.com/NVlabs/dexmimicgen/">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=jG9W6nAwVz">TwinVLA: Data-Efficient Bimanual Manipulation with Twin Single-Arm Vision-Language-Action Models</a></td>
<td nowrap>TwinVLA 将两个预训练单臂 VLA 组合成双臂 VLA，以少量双臂数据完成协调操作。</td>
<td nowrap>双臂机器人</td>
<td nowrap>视觉</td>
<td nowrap>twin single-arm VLA coordination</td>
<td nowrap>compose pretrained single-arm VLAs + limited bimanual finetuning</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决双臂 VLA 训练缺少大规模双臂数据且微调成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=jG9W6nAwVz">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=he86smZzRk">VLBiMan: Vision-Language Anchored One-Shot Demonstration Enables Generalizable Bimanual Robotic Manipulation</a></td>
<td nowrap>VLBiMan 从单次人类示范中分解可复用双臂技能，并用视觉语言锚点适配场景变化。</td>
<td nowrap>双臂机器人</td>
<td nowrap>视觉</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>one-shot demonstration + VLM grounding + geometric constraints</td>
<td nowrap>Real</td>
<td nowrap>解决双臂操作如何从极少示范泛化到不同背景、物体位置和干扰场景。</td>
<td nowrap><a href="https://openreview.net/forum?id=he86smZzRk">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38926">LatentVLA: Taming Latent Space for Generalizable and Long-Horizon Bimanual Manipulation</a></td>
<td nowrap>LatentVLA 组织视觉-语言-动作策略的潜空间，以提升长程双臂操作的泛化能力。</td>
<td nowrap>双臂机器人</td>
<td nowrap>-</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>latent-space VLA for long-horizon bimanual manipulation</td>
<td nowrap>-</td>
<td nowrap>解决长程双臂操作中 VLA 潜空间组织和泛化控制问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38926">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63277">DexMachina: Functional Retargeting for Bimanual Dexterous Manipulation</a></td>
<td nowrap>DexMachina 通过保持任务相关效果，在不同手和工具之间重定向双臂灵巧操作技能。</td>
<td nowrap>双臂机器人</td>
<td nowrap>-</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>bimanual policy</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63277">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66358">DECO: Decoupled Multimodal Diffusion Transformer for Bimanual Dexterous Manipulation with a Plugin Tactile Adapter</a></td>
<td nowrap>DECO 使用带触觉适配器的解耦多模态扩散 Transformer，为双臂灵巧操作建模视觉、动作和触觉。</td>
<td nowrap>双臂机器人</td>
<td nowrap>触觉/接触</td>
<td nowrap>diffusion policy / tactile policy / diffusion transformer / 双臂操作</td>
<td nowrap>diffusion policy / tactile policy / diffusion transformer</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66358">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62192">RoboTwin 2.0: A Scalable Data Generator and Benchmark with Strong Domain Randomization for Robust Bimanual Robotic Manipulation</a></td>
<td nowrap>RoboTwin 2.0 提供强域随机化的双臂机器人数据生成器和基准。</td>
<td nowrap>双臂机器人</td>
<td nowrap>-</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>sim data generator / domain randomization / benchmark</td>
<td nowrap>Sim + Benchmark</td>
<td nowrap>解决双臂操作缺少可扩展仿真数据和鲁棒评测任务的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62192">paper</a> / <a href="https://arxiv.org/pdf/2506.18088">paper</a> / <a href="https://arxiv.org/abs/2506.18088">paper</a></td>
<td nowrap><a href="https://robotwin-platform.github.io/">project</a></td>
<td nowrap><a href="https://github.com/robotwin-Platform/RoboTwin">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/TianxingChen/RoboTwin2.0">hf</a></td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.09186">Rethinking Bimanual Robotic Manipulation: Learning with Decoupled Interaction Framework</a></td>
<td nowrap>该文把双臂任务区分为协调与非协调情形，用双臂独立模型加选择性交互模块提升学习。</td>
<td nowrap>双臂机器人</td>
<td nowrap>-</td>
<td nowrap>per-arm policies + selective interaction module</td>
<td nowrap>decoupled interaction framework</td>
<td nowrap>-</td>
<td nowrap>解决集成式双臂策略强制早期协作、忽略非协作子任务的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.09186">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.06779">AnyBimanual: Transferring Unimanual Policy for General Bimanual Manipulation</a></td>
<td nowrap>AnyBimanual 将预训练单臂策略通过技能管理和少量双臂示范迁移到语言条件双臂操作。</td>
<td nowrap>双臂机器人</td>
<td nowrap>-</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>unimanual-to-bimanual transfer + few bimanual demos</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决双臂操作数据昂贵而单臂策略知识难复用的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.06779">paper</a></td>
<td nowrap><a href="https://anybimanual.github.io/">project</a></td>
<td nowrap><a href="https://github.com/TengBoYu01/AnyBimanual">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.23152">DexH2R: A Benchmark for Dynamic Dexterous Grasping in Human-to-Robot Handover</a></td>
<td nowrap>DexH2R 构建真实人到灵巧手交接数据集和基准，覆盖动态物体、人手运动和视觉标注。</td>
<td nowrap>灵巧手</td>
<td nowrap>-</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>bimanual policy</td>
<td nowrap>Real + Benchmark</td>
<td nowrap>解决动态人机交接中灵巧抓取缺少真实高质量数据集的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.23152">paper</a></td>
<td nowrap><a href="https://dexh2r.github.io/">project</a></td>
<td nowrap><a href="https://github.com/4DVLab/DexH2R">code</a></td>
<td nowrap>DexH2R benchmark</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.10743">Spatial-Temporal Graph Diffusion Policy with Kinematic Modeling for Bimanual Robotic Manipulation</a></td>
<td nowrap>KStar Diffuser 用空间时间图扩散策略显式建模机器人结构和运动学约束。</td>
<td nowrap>双臂机器人</td>
<td nowrap>-</td>
<td nowrap>diffusion policy / 双臂操作</td>
<td nowrap>spatial-temporal graph diffusion policy + differentiable kinematics</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决双臂模仿学习中动作预测忽略机器人结构、易碰撞和不满足关节约束的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.10743">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2501.04595">MobileH2R: Learning Generalizable Human to Mobile Robot Handover Exclusively from Scalable and Diverse Synthetic Data</a></td>
<td nowrap>MobileH2R 用可扩展合成人体动作数据和 4D 模仿学习训练移动机器人接物技能。</td>
<td nowrap>移动机器人+机械臂</td>
<td nowrap>-</td>
<td nowrap>bimanual policy / 双臂操作</td>
<td nowrap>synthetic data + 4D imitation learning</td>
<td nowrap>Sim training + Real evaluation</td>
<td nowrap>解决移动机器人在人到机器人交接中大工作空间、真实示范难采集的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2501.04595">paper</a></td>
<td nowrap><a href="https://mobileh2r.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### dexterous hand

共 31 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>本体类型</th>
<th nowrap>传感/接触</th>
<th nowrap>控制接口</th>
<th nowrap>训练方式</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/html/Li_ManipTrans_Efficient_Dexterous_Bimanual_Manipulation_Transfer_via_Residual_Learning_CVPR_2025_paper.html">ManipTrans: Efficient Dexterous Bimanual Manipulation Transfer via Residual Learning</a></td>
<td nowrap>ManipTrans transfers dexterous bimanual manipulation skills efficiently with residual learning.</td>
<td nowrap>Dexterous bimanual manipulation</td>
<td nowrap>hand-object contact</td>
<td nowrap>dexterous bimanual control</td>
<td nowrap>residual transfer learning</td>
<td nowrap>Simulation / robot tasks</td>
<td nowrap>Transfer dexterous bimanual manipulation skills.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Li_ManipTrans_Efficient_Dexterous_Bimanual_Manipulation_Transfer_via_Residual_Learning_CVPR_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2024</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/he24o.html">DynSyn: Dynamical Synergistic Representation for Efficient Learning and Control in Overactuated Embodied Systems</a></td>
<td nowrap>DynSyn learns dynamical synergies for efficient control in overactuated embodied systems.</td>
<td nowrap>Dexterous / overactuated embodiment</td>
<td nowrap>joint coordination</td>
<td nowrap>synergy control</td>
<td nowrap>representation learning + control</td>
<td nowrap>Control benchmarks</td>
<td nowrap>Reduce control complexity in high-DoF embodied systems.</td>
<td nowrap><a href="https://proceedings.mlr.press/v235/he24o/he24o.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2025/html/He_DexVLG_Dexterous_Vision-Language-Grasp_Model_at_Scale_ICCV_2025_paper.html">DexVLG: Dexterous Vision-Language-Grasp Model at Scale</a></td>
<td nowrap>DexVLG scales a vision-language grasp model for dexterous manipulation.</td>
<td nowrap>Dexterous grasping</td>
<td nowrap>vision-language grasp cues</td>
<td nowrap>dexterous grasp action</td>
<td nowrap>large-scale grasp model</td>
<td nowrap>Dexterous grasp tasks</td>
<td nowrap>Scale vision-language grasping to dexterous hands.</td>
<td nowrap><a href="https://arxiv.org/pdf/2507.02747">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2606.24450">NoContactNoWorries: Estimating Contact through Vision and Proprioception for In-Hand Dexterous Manipulation</a></td>
<td nowrap>NoContactNoWorries 不依赖触觉硬件，用视觉和本体感知估计灵巧手接触状态。</td>
<td nowrap>Dexterous hand</td>
<td nowrap>vision + proprioception contact estimation</td>
<td nowrap>in-hand manipulation</td>
<td nowrap>contact representation learning</td>
<td nowrap>Real</td>
<td nowrap>用低成本感知补足灵巧手接触反馈。</td>
<td nowrap><a href="https://arxiv.org/abs/2606.24450">paper</a></td>
<td nowrap><a href="https://soham2560.github.io/no-contact-no-worries/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Bf4FeuW0Mr">DemoGrasp: Universal Dexterous Grasping from a Single Demonstration</a></td>
<td nowrap>DemoGrasp 从单条成功抓取轨迹出发，通过编辑腕部位姿和手指关节并用 RL 优化通用抓取。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>single demonstration + RL trajectory editing</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决灵巧手通用抓取中高维长程探索和奖励课程设计复杂的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=Bf4FeuW0Mr">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/BeingBeyond/DemoGrasp">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=80vjyj5o7l">DexNDM: Closing the Reality Gap for Dexterous In-Hand Rotation via Joint-Wise Neural Dynamics Model</a></td>
<td nowrap>DexNDM 用关节级神经动力学模型用少量真实数据校正仿真策略，实现泛化物体掌内旋转。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>sim policy + joint-wise neural dynamics model + real-data adaptation</td>
<td nowrap>Sim-to-Real</td>
<td nowrap>解决灵巧手掌内旋转从仿真到真实的接触动力学现实差距问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=80vjyj5o7l">paper</a></td>
<td nowrap><a href="https://meowuu7.github.io/DexNDM/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=FFxkFMU89E">EgoDex: Learning Dexterous Manipulation from Large-Scale Egocentric Video</a></td>
<td nowrap>EgoDex 用 Apple Vision Pro 采集 829 小时第一视角视频和 3D 手指跟踪，支撑灵巧操作学习。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>egocentric RGB/video + 3D hand tracking</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>large-scale egocentric video pretraining</td>
<td nowrap>-</td>
<td nowrap>解决灵巧操作缺少互联网规模、带手部姿态标注的数据问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=FFxkFMU89E">paper</a> / <a href="https://arxiv.org/pdf/2505.11709">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/apple/ml-egodex">code</a></td>
<td nowrap>EgoDex dataset/benchmark</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Kt9tJeOwjy">RFS: Reinforcement learning with Residual flow steering for dexterous manipulation</a></td>
<td nowrap>RFS 用残差动作和延迟流时间变量强化学习微调预训练 flow-matching 灵巧操作策略。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>触觉/接触</td>
<td nowrap>residual action + flow steering</td>
<td nowrap>RL with Residual Flow Steering over pretrained flow policy</td>
<td nowrap>-</td>
<td nowrap>解决生成式模仿策略部署泛化不足但微调需保留预训练探索能力的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=Kt9tJeOwjy">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=NZDaMcpXZm">Learning to Grasp Anything By Playing with Random Toys</a></td>
<td nowrap>该文表明机器人可通过由少量形状基元组成的随机玩具学习可零样本泛化的抓取策略。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>视觉+本体状态</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>random toy training + object-centric visual representation</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决机器人抓取策略对新物体泛化差的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=NZDaMcpXZm">paper</a></td>
<td nowrap><a href="https://lego-grasp.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=aemqAxScl9">SARM: Stage-Aware Reward Modeling for Long Horizon Robot Manipulation</a></td>
<td nowrap>SARM 用阶段感知视频奖励模型和语言子任务标注，为长程接触/可变形物体操作提供稳定监督。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>stage-aware video reward modeling + reward-aligned BC</td>
<td nowrap>-</td>
<td nowrap>解决长程接触丰富操作中示范质量不一致、奖励标签难对齐的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=aemqAxScl9">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=cVX3VqO8BO">UniHM: Unified Dexterous Hand Manipulation with Vision Language Model</a></td>
<td nowrap>UniHM 用统一手部 tokenizer 和 VLA 从开放语言指令生成跨灵巧手形态的操作序列。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>视觉+语言+手物交互</td>
<td nowrap>VLM/VLA + Unified Hand-Dexterous Tokenizer</td>
<td nowrap>human-object interaction data</td>
<td nowrap>-</td>
<td nowrap>解决自由语言指导下不同灵巧手形态的统一可行操作规划问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=cVX3VqO8BO">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=k8ovuXEQQu">House Of Dextra : Cross-Embodied Co-Design for Dexterous Hands</a></td>
<td nowrap>House of Dextra 联合搜索灵巧手形态和控制策略，并可快速制造部署新手型。</td>
<td nowrap>可设计灵巧手</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>morphology-conditioned cross-embodied control</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决灵巧操作中手部硬件形态和控制策略需要协同设计的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=k8ovuXEQQu">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=tv0Sz8A9Tc">Robotic Manipulation by Imitating Generated Videos Without Physical Demonstrations</a></td>
<td nowrap>RIGVid 让机器人通过生成视频、VLM 过滤和 6D 轨迹重定向执行操作，无需真实示范。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>视觉+语言</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>generated-video imitation + VLM filtering + pose tracking</td>
<td nowrap>Real evaluation</td>
<td nowrap>解决无物理示范时如何从生成视频获得可执行机器人操作轨迹的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=tv0Sz8A9Tc">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=wySMuWHmt4">Primary-Fine Decoupling for Action Generation in Robotic Imitation</a></td>
<td nowrap>PF-DAG 先选择离散粗动作模式，再用 MeanFlow 生成细粒度动作，降低模态跳变。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>primary-fine action generation</td>
<td nowrap>discrete action chunk modes + mode-conditioned MeanFlow</td>
<td nowrap>-</td>
<td nowrap>解决机器人模仿学习动作序列多模态分布下离散化损失细节、连续生成不稳定的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=wySMuWHmt4">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=13jshGCK9i">D-REX: Differentiable Real-to-Sim-to-Real Engine for Learning Dexterous Grasping</a></td>
<td nowrap>D-REX 用 Gaussian Splat 可微引擎从真实观测识别物体质量并同步学习力感知抓取策略。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>differentiable real-to-sim-to-real + force-aware grasping</td>
<td nowrap>Real-to-Sim-to-Real</td>
<td nowrap>解决灵巧抓取中物理参数识别和 sim-to-real 动力学差距问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=13jshGCK9i">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=RYwQ0xQcAh">Interaction-aware Representation Modeling With Co-Occurrence Consistency for Egocentric Hand-Object Parsing</a></td>
<td nowrap>该文用交互感知表示和共现一致性改善第一视角手-物体解析，减少物理不一致预测。</td>
<td nowrap>egocentric hand-object perception</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>interaction-aware representation modeling</td>
<td nowrap>-</td>
<td nowrap>解决第一视角具身感知中手和活动物体精细分割/解析问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=RYwQ0xQcAh">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38873">GRIM: Task-Oriented Grasping with Conditioning on Generative Examples</a></td>
<td nowrap>GRIM 以生成示例作为抓取选择条件，帮助机器人选择符合任务意图而不只匹配物体几何的抓取。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>conditioning on generative examples</td>
<td nowrap>-</td>
<td nowrap>解决任务导向抓取中如何利用生成示例作为条件来选择合适抓取的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38873">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38874">Dexterous Manipulation Transfer via Progressive Kinematic-Dynamic Alignment</a></td>
<td nowrap>该文通过逐步对齐运动学和动力学，将灵巧操作策略迁移到不同本体和环境。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>progressive kinematic-dynamic alignment</td>
<td nowrap>-</td>
<td nowrap>解决灵巧操作策略跨形态/环境迁移中的运动学和动力学逐步对齐问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38874">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38892">Learning Object-Centric Motion Priors from Human for Robotic Dexterous Manipulation</a></td>
<td nowrap>该文从人类示范中学习以物体为中心的运动先验，并用其引导机器人灵巧操作。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>human-derived object-centric motion priors</td>
<td nowrap>-</td>
<td nowrap>解决如何从人类动作中学习物体中心运动先验并迁移到机器人灵巧操作。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38892">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38894">Real Garment Benchmark (RGBench): A Comprehensive Benchmark for Robotic Garment Manipulation Featuring a High-Fidelity Scalable Simulator</a></td>
<td nowrap>RGBench 提供真实服装数据、高保真可扩展仿真器和服装操作基准。</td>
<td nowrap>服装操作机器人/双臂</td>
<td nowrap>视觉</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>dexterous manipulation</td>
<td nowrap>Real garment data + simulator benchmark</td>
<td nowrap>解决机器人服装操作缺少真实数据、高保真仿真和统一评测的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38894">paper</a></td>
<td nowrap><a href="https://rgbench.github.io/">project</a></td>
<td nowrap><a href="https://github.com/hwk0809/RGBench">code</a></td>
<td nowrap><a href="https://rgbench.github.io/">benchmarks</a></td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38940">GraphGrasp: Lightweight and Efficient Graph-Guided 6-DoF Robotic Grasp Pose Estimation Network</a></td>
<td nowrap>GraphGrasp 通过图引导建模实现轻量高效的 6-DoF 机器人抓取位姿估计。</td>
<td nowrap>机器人抓取/夹爪为主</td>
<td nowrap>-</td>
<td nowrap>6-DoF grasp pose estimation</td>
<td nowrap>graph-guided network</td>
<td nowrap>-</td>
<td nowrap>解决轻量高效的 6-DoF 机器人抓取位姿估计问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38940">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38953">DexGraspVLA: A Vision-Language-Action Framework Towards General Dexterous Grasping</a></td>
<td nowrap>DexGraspVLA 将视觉语言高层规划与动作生成结合起来，支持基于指令的通用灵巧抓取。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>视觉+语言</td>
<td nowrap>VLM high-level planner + diffusion low-level controller</td>
<td nowrap>dexterous manipulation</td>
<td nowrap>-</td>
<td nowrap>解决视觉语言指令下通用灵巧抓取的规划与低层控制问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38953">paper</a></td>
<td nowrap><a href="https://dexgraspvla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Psi-Robot/DexGraspVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38957">Effective Robotic Cloth Grasping Through Suppressing False Discoveries</a></td>
<td nowrap>该文抑制布料抓取检测中的错误发现，使机器人布料抓取更可靠。</td>
<td nowrap>布料抓取机器人</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>false-discovery suppression</td>
<td nowrap>-</td>
<td nowrap>解决布料抓取中误检/错误发现导致抓取点不可靠的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38957">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2603.22264">UniDex: A Robot Foundation Suite for Universal Dexterous Hand Control from Egocentric Human Videos</a></td>
<td nowrap>UniDex 将第一视角人类视频重定向为 50K 轨迹、8 种灵巧手数据，并训练统一 3D VLA 策略。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>egocentric video + 3D point cloud + language</td>
<td nowrap>VLA / 灵巧手/抓取</td>
<td nowrap>3D VLA pretraining on UniDex-Dataset + task finetuning</td>
<td nowrap>human video-derived robot trajectories + downstream real/sim tasks</td>
<td nowrap>解决灵巧手控制中真实遥操作数据昂贵、手型异构和高维控制难题。</td>
<td nowrap><a href="https://arxiv.org/abs/2603.22264">paper</a></td>
<td nowrap><a href="https://unidex-ai.github.io/">project</a></td>
<td nowrap><a href="https://github.com/unidex-ai/UniDex">code</a></td>
<td nowrap><a href="https://huggingface.co/UniDex-ai/UniDex">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/pdf/2511.01276">Generalizable Dexterous Grasp Generation via Contact Map Transfer</a></td>
<td nowrap>该文迁移接触图来条件化扩散式灵巧抓取生成，使抓取能泛化到不同物体。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>触觉/接触</td>
<td nowrap>conditional diffusion grasp generation</td>
<td nowrap>diffusion policy</td>
<td nowrap>-</td>
<td nowrap>解决通过接触图迁移生成可泛化灵巧抓取的问题。</td>
<td nowrap><a href="https://arxiv.org/pdf/2511.01276">paper</a></td>
<td nowrap><a href="https://cmtdiffusion.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Yiyao-Ma/cmtdiffusion">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.02489">Grasp2Grasp: Vision-Based Dexterous Grasp Translation via Schrödinger Bridges</a></td>
<td nowrap>Grasp2Grasp 用 Schrödinger Bridge 在不同机械手之间做视觉条件的功能等价抓取迁移。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>视觉</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>score/flow matching + physics-informed costs</td>
<td nowrap>-</td>
<td nowrap>解决不同灵巧手形态之间无需配对示范或手型仿真的抓取意图迁移问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.02489">paper</a></td>
<td nowrap><a href="https://grasp2grasp.github.io/">project</a></td>
<td nowrap><a href="https://github.com/n3il666/grasp2grasp">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.19212">Scaffolding Dexterous Manipulation with Vision-Language Models</a></td>
<td nowrap>该文用 VLM 生成足够粗的脚手架轨迹/物体位姿，引导 RL 学习灵巧操作。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>视觉</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>VLM scaffolding + RL refinement</td>
<td nowrap>Simulation</td>
<td nowrap>解决灵巧手 RL 缺少可扩展参考轨迹和任务奖励的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.19212">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/dexterous-vlm-scaffolding">project</a></td>
<td nowrap><a href="https://github.com/vdebakker/vlm-scaffolding">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.11032">DexGarmentLab: Dexterous Garment Manipulation Environment with Generalizable Policy</a></td>
<td nowrap>DexGarmentLab 构建面向双手灵巧服装操作的环境、3D 资产和可泛化策略。</td>
<td nowrap>双手/灵巧手服装操作</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>dexterous manipulation</td>
<td nowrap>Simulation benchmark</td>
<td nowrap>解决服装灵巧操作缺少真实仿真环境和高效数据生成策略的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.11032">paper</a></td>
<td nowrap><a href="https://wayrise.github.io/DexGarmentLab/">project</a></td>
<td nowrap><a href="https://github.com/wayrise/DexGarmentLab">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/wayrise/DexGarmentLab">hf</a></td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.02699">UniGraspTransformer: Simplified Policy Distillation for Scalable Dexterous Robotic Grasping</a></td>
<td nowrap>UniGraspTransformer 先用 RL 为单物体训练专家轨迹，再蒸馏到统一 Transformer 抓取网络。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>RL expert trajectories + policy distillation</td>
<td nowrap>state-based + vision-based eval</td>
<td nowrap>解决大规模灵巧抓取训练流程复杂、难扩展到大量物体的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.02699">paper</a></td>
<td nowrap><a href="https://dexhand.github.io/UniGraspTransformer/">project</a></td>
<td nowrap><a href="https://github.com/microsoft/UniGraspTransformer">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08257">DexGrasp Anything: Towards Universal Robotic Dexterous Grasping with Physics Awareness</a></td>
<td nowrap>DexGrasp Anything 将物理约束融入扩散抓取生成，并发布 3.4M 抓取位姿/15K 物体数据。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>physics-aware diffusion grasp generation</td>
<td nowrap>-</td>
<td nowrap>解决任意物体通用灵巧抓取位姿生成质量和物理可用性问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08257">paper</a></td>
<td nowrap><a href="https://dexgraspanything.github.io/">project</a></td>
<td nowrap><a href="https://github.com/4DVLab/DexGrasp-Anything">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/GaussionZhong/DexGrasp-Anything">hf</a></td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/32440">ZeroGrasp: Zero-Shot Shape Reconstruction Enabled Robotic Grasping</a></td>
<td nowrap>ZeroGrasp 在零样本场景中重建物体形状，使机器人无需特定物体训练数据即可抓取。</td>
<td nowrap>灵巧手/抓取</td>
<td nowrap>-</td>
<td nowrap>dexterous manipulation / 灵巧手/抓取</td>
<td nowrap>dexterous manipulation</td>
<td nowrap>-</td>
<td nowrap>解决零样本形状重建辅助机器人抓取的问题。</td>
<td nowrap><a href="https://cvpr.thecvf.com/virtual/2025/poster/32440">paper</a></td>
<td nowrap><a href="https://sh8.io/#/zerograsp">project</a></td>
<td nowrap><a href="https://github.com/sh8/ZeroGrasp">code</a></td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### tactile/contact-rich

共 13 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>本体类型</th>
<th nowrap>传感/接触</th>
<th nowrap>控制接口</th>
<th nowrap>训练方式</th>
<th nowrap>Sim/Real</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=dT3ZciXvNX">DexMove: Learning Tactile-Guided Non-Prehensile Manipulation with Dexterous Hands</a></td>
<td nowrap>DexMove 结合仿真轨迹和可穿戴视触觉人类接触数据，训练流策略实现灵巧手非抓取移动物体。</td>
<td nowrap>灵巧手非抓取操作</td>
<td nowrap>vision-based tactile + contact</td>
<td nowrap>tactile policy / 灵巧手/抓取</td>
<td nowrap>simulation trajectories + wearable visuotactile human contact data + flow policy</td>
<td nowrap>Sim + Real</td>
<td nowrap>解决灵巧手非抓取操作缺少接触感知数据和腕指协同策略的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=dT3ZciXvNX">paper</a></td>
<td nowrap><a href="https://peilin-666.github.io/projects/DexMove/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=ndilONnABZ">AnyTouch 2: General Optical Tactile Representation Learning For Dynamic Tactile Perception</a></td>
<td nowrap>AnyTouch 2 用 ToucHD 大规模动态触觉数据学习跨光学触觉传感器的通用力感知表示。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>ToucHD pretraining + dynamic tactile representation learning</td>
<td nowrap>-</td>
<td nowrap>解决触觉模型过度关注静态属性、缺少动态触觉和力信息的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=ndilONnABZ">paper</a></td>
<td nowrap><a href="https://gewu-lab.github.io/AnyTouch2/">project</a></td>
<td nowrap><a href="https://github.com/GeWu-Lab/AnyTouch2">code</a></td>
<td nowrap><a href="https://huggingface.co/collections/BAAI/touchd">hf</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=hU2gT2Ucua">APPLE: Toward General Active Perception via Reinforcement Learning</a></td>
<td nowrap>APPLE 联合训练 Transformer 感知模块和决策策略，用 RL 主动采集触觉等稀疏信息。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>RL joint perception-policy learning</td>
<td nowrap>Tactile MNIST / active perception benchmarks</td>
<td nowrap>解决主动感知方法任务绑定强、泛化不足的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=hU2gT2Ucua">paper</a></td>
<td nowrap><a href="https://timschneider42.github.io/apple">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38882">STOLA: Self-Adaptive Touch-Language Framework for Tactile Commonsense Reasoning in Open-Ended Scenarios</a></td>
<td nowrap>STOLA 将触觉-语言推理适配到开放触觉场景，把触觉信号与常识语言理解联系起来。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>touch-language reasoning framework</td>
<td nowrap>-</td>
<td nowrap>解决开放场景中触觉与语言结合的常识推理问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38882">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38915">TouchFormer: A Robust Transformer-based Framework for Multimodal Material Perception</a></td>
<td nowrap>TouchFormer 使用基于 Transformer 的多模态框架，使材料感知能稳健融合视觉和触觉线索。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉+视觉/多模态</td>
<td nowrap>perception model</td>
<td nowrap>Transformer-based material perception</td>
<td nowrap>-</td>
<td nowrap>解决视觉/触觉等多模态材料感知的鲁棒识别问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38915">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38956">Collaborative Representation Learning for Alignment of Tactile, Language, and Vision Modalities</a></td>
<td nowrap>该文学习协同表征，对齐触觉、语言和视觉模态以支持共享的多模态理解。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉+视觉+语言</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>collaborative multimodal representation learning</td>
<td nowrap>-</td>
<td nowrap>解决触觉、语言和视觉三模态表征对齐问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38956">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66793">Cross-Tactile Sensor Representation Learning</a></td>
<td nowrap>该文学习可跨不同传感器类型迁移的触觉表征，降低对单一触觉硬件的依赖。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>tactile policy</td>
<td nowrap>-</td>
<td nowrap>引入触觉提升接触操作</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66793">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65669">Tabero: Learning Gentle Manipulation with Closed-Loop Force Feedback from Vision, Touch, and Language</a></td>
<td nowrap>Tabero 结合视觉、触觉、语言和闭环力反馈，通过混合控制学习轻柔操作。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>vision + touch + language + force feedback</td>
<td nowrap>decoupled force-position commands + hybrid controller</td>
<td nowrap>tactile policy</td>
<td nowrap>-</td>
<td nowrap>解决用视觉、触觉和语言闭环力反馈学习轻柔操作的问题。</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65669">paper</a></td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/65669">project</a></td>
<td nowrap><a href="https://github.com/NathanWu7/Tabero">code</a></td>
<td nowrap>Tabero benchmark/model suite</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.22566">Universal Visuo-Tactile Video Understanding for Embodied Interaction</a></td>
<td nowrap>VTV-LLM 用 VTV150K 视频触觉数据训练通用视觉-触觉-语言理解模型。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>visuo-tactile-language understanding model</td>
<td nowrap>VTV150K multimodal pretraining</td>
<td nowrap>-</td>
<td nowrap>解决具身交互中触觉信息难与视觉语言统一理解的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.22566">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/IvanXie416/VTV-LLM">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/Ivan416/VBTS_video">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2510.21609">Enhancing Tactile-based Reinforcement Learning for Robotic Control</a></td>
<td nowrap>该文用自监督表示学习和稀疏二值触觉信号提升触觉 RL 在复杂接触任务中的灵巧度。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>proprioception + sparse binary contacts</td>
<td nowrap>tactile policy / RL / 触觉/接触</td>
<td nowrap>tactile RL + self-supervised representation learning</td>
<td nowrap>-</td>
<td nowrap>解决触觉 RL 效果不稳定、过度依赖理想状态信息的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.21609">paper</a></td>
<td nowrap><a href="https://elle-miller.github.io/tactile_rl/">project</a></td>
<td nowrap><a href="https://github.com/elle-miller/roto">code</a></td>
<td nowrap>RoTO benchmark</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://taccel-simulator.github.io/assets/taccel-paper.pdf">Taccel: Scaling Up Vision-based Tactile Robotics via High-performance GPU Simulation</a></td>
<td nowrap>Taccel 提供面向视觉触觉机器人的高性能 GPU 仿真，扩展带触觉感知的数据生成和策略训练。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>GPU tactile simulation</td>
<td nowrap>Simulation</td>
<td nowrap>解决基于视觉触觉传感的机器人训练难以高性能仿真扩展的问题。</td>
<td nowrap><a href="https://taccel-simulator.github.io/assets/taccel-paper.pdf">paper</a></td>
<td nowrap><a href="https://taccel-simulator.github.io/">project</a></td>
<td nowrap><a href="https://github.com/Taccel-Simulator/Taccel">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2511.16596">Toward Artificial Palpation: Representation Learning of Touch on Soft Bodies</a></td>
<td nowrap>该文用自监督编码器从软体触诊序列学习表征，并用于触觉成像和变化检测。</td>
<td nowrap>触觉/接触操作</td>
<td nowrap>触觉/接触</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>self-supervised tactile representation learning</td>
<td nowrap>Simulation + Real soft-body/MRI dataset</td>
<td nowrap>解决软体医学触诊中如何从触觉测量学习可用于下游任务的表示问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2511.16596">paper</a></td>
<td nowrap><a href="https://zoharri.github.io/artificial-palpation/">project</a></td>
<td nowrap><a href="https://github.com/zoharri/ArtificialPalpation">code</a></td>
<td nowrap><a href="https://zenodo.org/records/17608184">data</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.15062v1">Touch in the Wild: Learning Fine-Grained Manipulation with a Portable Visuo-Tactile Gripper</a></td>
<td nowrap>Touch in the Wild 用便携视触觉夹爪采集野外示范，并学习可解释跨模态表示提升精细操作策略。</td>
<td nowrap>便携视触觉夹爪+机器人操作</td>
<td nowrap>vision + tactile + proprioception</td>
<td nowrap>tactile policy / 触觉/接触</td>
<td nowrap>visuo-tactile pretraining + downstream imitation learning</td>
<td nowrap>Real / in-the-wild data + real robot tasks</td>
<td nowrap>解决人类示范采集缺少触觉、精细操作策略学习效率低的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.15062v1">paper</a></td>
<td nowrap><a href="https://binghao-huang.github.io/touch_in_the_wild/">project</a></td>
<td nowrap><a href="https://github.com/YolandaXinyueZhu/touch_in_the_wild">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/binghaohuang-robot/touch_in_the_wild-dataset">hf</a></td>
</tr>
</tbody>
</table>

### 轻量化 / 评测 / 数据

这一方向决定能不能真实部署：端侧推理、缓存/量化/action tokenization、实时执行、sim2real、benchmark 和 safety evaluation 都是必需条件。

子方向：quantization/cache/tokenization、real-time execution、benchmark/dataset、sim2real、safety evaluation。

共 95 篇。

<table>
<thead>
<tr>
<th nowrap>子方向</th>
<th nowrap>条目数</th>
<th nowrap>观察重点</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>quantization/cache/tokenization</td>
<td nowrap>21</td>
<td nowrap>看端侧部署、缓存复用和 action token 效率。</td>
</tr>
<tr>
<td nowrap>real-time execution</td>
<td nowrap>6</td>
<td nowrap>看低延迟执行和实时策略推理。</td>
</tr>
<tr>
<td nowrap>benchmark/dataset</td>
<td nowrap>39</td>
<td nowrap>看数据覆盖、任务设计和评测可信度。</td>
</tr>
<tr>
<td nowrap>sim2real</td>
<td nowrap>17</td>
<td nowrap>看仿真到真实迁移和真实部署差距。</td>
</tr>
<tr>
<td nowrap>safety evaluation</td>
<td nowrap>12</td>
<td nowrap>看鲁棒性、安全性和部署风险评估。</td>
</tr>
</tbody>
</table>

#### quantization/cache/tokenization

共 21 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>对象类型</th>
<th nowrap>效率指标</th>
<th nowrap>平台/硬件</th>
<th nowrap>覆盖任务</th>
<th nowrap>开放资源状态</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2509.05614">SpecPrune-VLA: Accelerating Vision-Language-Action Models via Action-Aware Self-Speculative Pruning</a></td>
<td nowrap>用动作感知 self-speculative pruning 加速 VLA 推理，同时尽量保持动作质量。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>self-speculative pruning</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>VLA manipulation</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 动作生成中的冗余计算。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.05614">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>EMNLP 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.22424">Spec-VLA: Speculative Decoding for Vision-Language-Action Models with Relaxed Acceptance</a></td>
<td nowrap>把 relaxed speculative decoding 用于加速 VLA 动作生成。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>speculative decoding</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>VLA manipulation</td>
<td nowrap>-</td>
<td nowrap>解决机器人执行中自回归 VLA 解码慢的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.22424">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2411.02359">DeeR-VLA: Dynamic Inference of Multimodal Large Language Models for Efficient Robot Execution</a></td>
<td nowrap>通过动态推理减少机器人执行时的多模态 VLA 计算量。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>dynamic inference</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>robot execution</td>
<td nowrap>Code</td>
<td nowrap>解决多模态 VLA 推理中的非必要计算。</td>
<td nowrap><a href="https://arxiv.org/abs/2411.02359">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/yueyang130/DeeR-VLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2024</td>
<td nowrap><a href="https://arxiv.org/abs/2406.04339">RoboMamba: Efficient Vision-Language-Action Model for Robotic Reasoning and Manipulation</a></td>
<td nowrap>用 Mamba/state-space 架构提升 VLA 机器人推理和操作效率。</td>
<td nowrap>efficient architecture</td>
<td nowrap>state-space model backbone</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>robot reasoning and manipulation</td>
<td nowrap>Project+Code</td>
<td nowrap>解决 VLA 策略中的 Transformer 效率瓶颈。</td>
<td nowrap><a href="https://arxiv.org/abs/2406.04339">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/robomamba-web">project</a></td>
<td nowrap><a href="https://github.com/lmzpai/roboMamba">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=E1K2Ph3LtS">MetaVLA: Unified Meta Co-Training for Efficient Embodied Adaptation</a></td>
<td nowrap>用元协同训练把多任务适配合并到低成本后训练，降低 VLA 微调算力并提升 LIBERO 泛化。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>meta co-training</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>LIBERO manipulation</td>
<td nowrap>Code planned</td>
<td nowrap>解决 VLA 任务适配成本高、泛化弱的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=E1K2Ph3LtS">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=RwdGIIjPlC">SP-VLA: A Joint Model Scheduling and Token Pruning Approach for VLA Model Acceleration</a></td>
<td nowrap>通过动作感知模型调度和时空语义 token pruning，让 VLA 在 LIBERO/SimplerEnv 中加速且不降性能。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>model scheduling + token pruning</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>LIBERO, SimplerEnv</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 顺序决策中的时间和视觉冗余。</td>
<td nowrap><a href="https://openreview.net/forum?id=RwdGIIjPlC">paper</a> / <a href="https://arxiv.org/abs/2506.12723">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=TpL2nXanru">QVLA: Not All Channels Are Equal in Vision-Language-Action Model&#x27;s Quantization</a></td>
<td nowrap>提出动作敏感的逐通道混合位宽量化，把 VLA 压到低显存同时保持成功率。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>channel-wise action-centric quantization/pruning</td>
<td nowrap>resource-constrained robot hardware</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决 LLM 式统一量化不适合机器人动作误差累积的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=TpL2nXanru">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=ea6j8k8Rnw">Action-aware Dynamic Pruning for Efficient Vision-Language-Action Manipulation</a></td>
<td nowrap>根据最近动作轨迹动态调整视觉 token 保留率，减少长时序 VLA 操作推理延迟。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>action-aware dynamic visual token pruning</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>LIBERO + real-world manipulation</td>
<td nowrap>-</td>
<td nowrap>解决操作不同阶段视觉冗余不同但固定 pruning 不适配的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=ea6j8k8Rnw">paper</a> / <a href="https://arxiv.org/abs/2509.22093">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=k6nTUFoqeT">FASTer: Toward Powerful and Efficient Autoregressive Vision–Language–Action Models with Learnable Action Tokenizer and Block-wise Decoding</a></td>
<td nowrap>用可学习动作 tokenizer 和 block-wise 解码提升自回归 VLA 的动作压缩、速度和任务表现。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>learnable action tokenizer + block-wise decoding</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>sim+real manipulation</td>
<td nowrap>-</td>
<td nowrap>解决动作 tokenization 在重建质量和推理效率之间的折中。</td>
<td nowrap><a href="https://openreview.net/forum?id=k6nTUFoqeT">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38880">FT-NCFM: An Influence-Aware Data Distillation Framework for Efficient VLA Models</a></td>
<td nowrap>用因果归因和对抗式 NCFM 蒸馏高价值 VLA 数据，少量 coreset 达到接近全量训练效果。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>data distillation</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Code+Data planned</td>
<td nowrap>解决 VLA 依赖大规模冗余数据导致训练成本高的问题。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38903">CronusVLA: Towards Efficient and Robust Manipulation via Multi-Frame Vision-Language-Action Modeling</a></td>
<td nowrap>CronusVLA 以多帧历史特征聚合提升 VLA 操作鲁棒性，同时控制多帧推理开销。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>tokenization</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决单帧 VLA 无法利用历史观测且多帧直接输入延迟高的问题。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38904">SemanticVLA: Semantic-Aligned Sparsification and Enhancement for Efficient Robotic Manipulation</a></td>
<td nowrap>通过语义对齐的视觉稀疏化、层级融合和动作耦合提升 VLA 操作效率与成功率。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>semantic-aligned sparsification</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决视觉冗余和浅层指令-视觉对齐影响机器人操作的问题。</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/JiuTian-VL/SemanticVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38931">VLA-Adapter: An Effective Paradigm for Tiny-Scale Vision-Language-Action Model</a></td>
<td nowrap>用小规模 VLA 适配范式在较低模型规模下保持机器人操作能力。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>tiny-scale VLA adapter</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project+Code</td>
<td nowrap>解决 tiny-scale VLA 如何有效适配操作任务的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38931">paper</a> / <a href="https://arxiv.org/abs/2509.09372">paper</a></td>
<td nowrap><a href="https://vla-adapter.github.io/">project</a></td>
<td nowrap><a href="https://github.com/OpenHelix-Team/VLA-Adapter">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38945">MoLe-VLA: Dynamic Layer-skipping Vision Language Action Model via Mixture-of-Layers for Efficient Robot Manipulation</a></td>
<td nowrap>用 mixture-of-layers 动态跳层减少 VLA 计算量并保持操作成功率。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>dynamic layer skipping / up to 5.6x compute reduction</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project+Code</td>
<td nowrap>解决 VLA 推理中不同样本/步骤不必经过全部层的问题。</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38945">paper</a> / <a href="https://arxiv.org/abs/2503.20384">paper</a></td>
<td nowrap><a href="https://sites.google.com/view/mole-vla">project</a></td>
<td nowrap><a href="https://github.com/RoyZry98/MoLe-VLA-Pytorch/">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2602.20309">QuantVLA: Scale-Calibrated Post-Training Quantization for Vision-Language-Action Models</a></td>
<td nowrap>提出免训练 PTQ 量化 VLA 语言骨干和 DiT 动作头，显著节省内存。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>PTQ</td>
<td nowrap>compute/memory/power constrained deployment</td>
<td nowrap>-</td>
<td nowrap>Project+Code</td>
<td nowrap>解决 VLA 大模型在低算力/低功耗部署中的量化问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.20309">paper</a></td>
<td nowrap><a href="https://quantvla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/AIoT-MLSys-Lab/QuantVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.06072">BEAST: Efficient Tokenization of B-Splines Encoded Action Sequences for Imitation Learning</a></td>
<td nowrap>用 B-spline 编码动作序列为定长 token，免单独 tokenizer 训练并生成平滑高频控制。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>B-spline action tokenizer</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>166 sim tasks + 8 real tasks</td>
<td nowrap>-</td>
<td nowrap>解决模仿学习动作序列 tokenization 成本和轨迹平滑性问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.06072">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.14259">Quantization-Free Autoregressive Action Transformer</a></td>
<td nowrap>用连续无限词表 Transformer 直接建模动作，避免离散量化破坏动作空间结构。</td>
<td nowrap>continuous autoregressive action modeling</td>
<td nowrap>quantization-free continuous autoregressive action modeling</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>降低模型部署成本</td>
<td nowrap>Code</td>
<td nowrap>解决自回归模仿学习中离散动作码限制连续控制的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.14259">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.10100">EfficientVLA: Training-Free Acceleration and Compression for Vision-Language-Action Models</a></td>
<td nowrap>通过语言层剪枝、视觉 token 选择和 diffusion 特征缓存实现免训练 VLA 加速压缩。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>layer pruning + visual token selection + diffusion cache</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>CogACT/SIMPLER</td>
<td nowrap>-</td>
<td nowrap>解决 VLA 管线中语言、视觉和动作头多处冗余。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.10100">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2502.02175">VLA-Cache: Efficient Vision-Language-Action Manipulation via Adaptive Token Caching</a></td>
<td nowrap>自适应复用相邻帧静态视觉 token 的 KV cache，提高 VLA 控制频率。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>adaptive visual token KV caching</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>LIBERO, SIMPLER, real robot</td>
<td nowrap>Project+Code</td>
<td nowrap>解决实时机器人控制中逐帧重复视觉计算的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2502.02175">paper</a></td>
<td nowrap><a href="https://vla-cache.github.io/">project</a></td>
<td nowrap><a href="https://github.com/siyuhsu/vla-cache">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.01016">VQ-VLA: Improving Vision-Language-Action Models via Scaling Vector-Quantized Action Tokenizers</a></td>
<td nowrap>用大规模合成/真实轨迹训练 VQ 动作 tokenizer，提升 VLA 推理速度和长时程动作质量。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>vector-quantized action tokenizer</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project+Code</td>
<td nowrap>解决动作 tokenizer 数据规模不足和泛化弱的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.01016">paper</a></td>
<td nowrap><a href="https://xiaoxiao0406.github.io/vqvla.github.io">project</a> / <a href="https://xiaoxiao0406.github.io/vqvla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/xiaoxiao0406/VQ-VLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.15304">Saliency-Aware Quantized Imitation Learning for Efficient Robotic Control</a></td>
<td nowrap>用显著性感知量化压缩模仿学习策略，在高效控制和任务性能之间折中。</td>
<td nowrap>压缩/缓存/tokenization</td>
<td nowrap>saliency-aware quantized imitation learning</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决机器人控制策略量化时关键感知/动作信息易损失的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.15304">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### real-time execution

共 6 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>对象类型</th>
<th nowrap>效率指标</th>
<th nowrap>平台/硬件</th>
<th nowrap>覆盖任务</th>
<th nowrap>开放资源状态</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=INsLvSCJ4z">Time Optimal Execution of Action Chunk Policies Beyond Demonstration Speed</a></td>
<td nowrap>将 action chunk policy 的执行时间优化到超过示教速度，同时保持动作可行性。</td>
<td nowrap>实时执行</td>
<td nowrap>time-optimal execution</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>action chunk policy execution</td>
<td nowrap>-</td>
<td nowrap>解决 action chunk 策略执行受示教速度限制的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=INsLvSCJ4z">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=mIeKe74W43">Mean Flow Policy with Instantaneous Velocity Constraint for One-step Action Generation</a></td>
<td nowrap>在 mean flow policy 中加入瞬时速度约束，实现一步动作生成与可执行控制。</td>
<td nowrap>实时执行</td>
<td nowrap>one-step action generation + velocity constraint</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决 flow policy 多步采样慢和速度约束缺失的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=mIeKe74W43">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=r0RGJ1j9on">Real-Time Robot Execution with Masked Action Chunking</a></td>
<td nowrap>用 masked action chunking 支持机器人实时执行，减少 chunk 推理和控制不匹配。</td>
<td nowrap>实时执行</td>
<td nowrap>masked action chunking</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>real-time robot execution</td>
<td nowrap>-</td>
<td nowrap>解决 action chunking 策略在实时闭环执行中的延迟问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=r0RGJ1j9on">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://www.physicalintelligence.company/download/real_time_chunking.pdf">Real-Time Execution of Action Chunking Flow Policies</a></td>
<td nowrap>Physical Intelligence 提出 action chunking flow policy 的实时执行机制。</td>
<td nowrap>实时执行</td>
<td nowrap>real-time</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决 flow policy 生成动作块后如何低延迟稳定执行的问题。</td>
<td nowrap><a href="https://www.physicalintelligence.company/download/real_time_chunking.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://www.arxiv.org/abs/2505.10646">Accelerating Visual-Policy Learning through Parallel Differentiable Simulation</a></td>
<td nowrap>用并行可微仿真加速视觉策略学习和训练反馈。</td>
<td nowrap>parallel differentiable simulation</td>
<td nowrap>real-time</td>
<td nowrap>simulation</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决视觉策略真实/串行仿真训练慢的问题。</td>
<td nowrap><a href="https://www.arxiv.org/abs/2505.10646">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2508.00697">On-Device Diffusion Transformer Policy for Efficient Robot Manipulation</a></td>
<td nowrap>通过剪枝/蒸馏把 diffusion transformer policy 部署到端侧实时机器人操作。</td>
<td nowrap>实时执行</td>
<td nowrap>latency + pruning/distillation</td>
<td nowrap>on-device/mobile robot hardware</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决 Diffusion Transformer Policy 在端侧设备延迟过高的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2508.00697">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### benchmark/dataset

共 39 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>对象类型</th>
<th nowrap>效率指标</th>
<th nowrap>平台/硬件</th>
<th nowrap>覆盖任务</th>
<th nowrap>开放资源状态</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2025/html/Zhong_UnrealZoo_Enriching_Photo-realistic_Virtual_Worlds_for_Embodied_AI_ICCV_2025_paper.html">UnrealZoo: Enriching Photo-realistic Virtual Worlds for Embodied AI</a></td>
<td nowrap>UnrealZoo expands photorealistic virtual worlds for embodied AI training and evaluation.</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>virtual-world coverage</td>
<td nowrap>simulation platform</td>
<td nowrap>embodied navigation and interaction</td>
<td nowrap>open virtual-world resource</td>
<td nowrap>Provide richer simulation environments for embodied AI.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/ICCV2025/papers/Zhong_UnrealZoo_Enriching_Photo-realistic_Virtual_Worlds_for_Embodied_AI_ICCV_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/html/Chen_ActiveGAMER_Active_GAussian_Mapping_through_Efficient_Rendering_CVPR_2025_paper.html">ActiveGAMER: Active GAussian Mapping through Efficient Rendering</a></td>
<td nowrap>ActiveGAMER performs active Gaussian mapping with efficient rendering for embodied scene understanding.</td>
<td nowrap>mapping/evaluation</td>
<td nowrap>mapping efficiency</td>
<td nowrap>Gaussian mapping pipeline</td>
<td nowrap>active mapping</td>
<td nowrap>mapping benchmark/resource</td>
<td nowrap>Improve active mapping efficiency for embodied agents.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2025/papers/Chen_ActiveGAMER_Active_Gaussian_Mapping_through_Efficient_Rendering_CVPR_2025_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Yang_Holodeck_Language_Guided_Generation_of_3D_Embodied_AI_Environments_CVPR_2024_paper.html">Holodeck: Language Guided Generation of 3D Embodied AI Environments</a></td>
<td nowrap>Holodeck generates 3D embodied AI environments from language guidance.</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>3D environment diversity</td>
<td nowrap>language-to-environment generator</td>
<td nowrap>environment generation</td>
<td nowrap>3D embodied environments</td>
<td nowrap>Generate diverse 3D scenes for embodied AI evaluation.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Yang_Holodeck_Language_Guided_Generation_of_3D_Embodied_AI_Environments_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2022</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2022/hash/27c546ab1e4f1d7d638e6a8dfbad9a07-Abstract-Conference.html">ProcTHOR: Large-Scale Embodied AI Using Procedural Generation</a></td>
<td nowrap>ProcTHOR uses procedural generation to create large-scale embodied AI environments.</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>procedural scene diversity</td>
<td nowrap>AI2-THOR environment generation</td>
<td nowrap>navigation and interaction tasks</td>
<td nowrap>ProcTHOR</td>
<td nowrap>Scale embodied-AI evaluation with generated houses.</td>
<td nowrap><a href="https://proceedings.neurips.cc/paper_files/paper/2022/file/27c546ab1e4f1d7d638e6a8dfbad9a07-Paper-Conference.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2024</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/html/Wang_EmbodiedScan_A_Holistic_Multi-Modal_3D_Perception_Suite_Towards_Embodied_AI_CVPR_2024_paper.html">EmbodiedScan: A Holistic Multi-Modal 3D Perception Suite Towards Embodied AI</a></td>
<td nowrap>EmbodiedScan provides a multimodal 3D perception suite for embodied AI.</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>multi-modal 3D perception coverage</td>
<td nowrap>dataset + benchmark</td>
<td nowrap>3D perception tasks</td>
<td nowrap>EmbodiedScan</td>
<td nowrap>Benchmark holistic 3D perception for embodied agents.</td>
<td nowrap><a href="https://openaccess.thecvf.com/content/CVPR2024/papers/Wang_EmbodiedScan_A_Holistic_Multi-Modal_3D_Perception_Suite_Towards_Embodied_AI_CVPR_2024_paper.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ECCV 2024</td>
<td nowrap><a href="https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/01610.pdf">ReALFRED: An Embodied Instruction Following Benchmark in Photo-Realistic Environments</a></td>
<td nowrap>ReALFRED benchmarks embodied instruction following in photorealistic environments.</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>photorealistic instruction-following coverage</td>
<td nowrap>benchmark</td>
<td nowrap>instruction following</td>
<td nowrap>ReALFRED</td>
<td nowrap>Evaluate embodied instruction following in realistic scenes.</td>
<td nowrap><a href="https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/01610.pdf">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICRA 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2509.14687">RealMirror: A Comprehensive, Open-Source Vision-Language-Action Platform for Embodied AI</a></td>
<td nowrap>RealMirror 提供 VLA 数据采集、仿真、训练、评测和 zero-shot sim2real 平台。</td>
<td nowrap>VLA platform / benchmark</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>simulation/evaluation environment</td>
<td nowrap>humanoid VLA research</td>
<td nowrap>project/code/models available</td>
<td nowrap>降低 VLA 数据、训练和评测门槛。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.14687">paper</a></td>
<td nowrap><a href="https://terminators2025.github.io/RealMirror.github.io/">project</a></td>
<td nowrap><a href="https://github.com/terminators2025/RealMirror">code</a></td>
<td nowrap><a href="https://huggingface.co/zte-terminators/realmirror-model-ckpt">hf</a></td>
</tr>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.05313">lambda: A Benchmark for Data-Efficiency in Long-Horizon Indoor Mobile Manipulation Robotics</a></td>
<td nowrap>lambda benchmark 评测长程室内移动操作在数据效率、语言任务和多房间场景下的表现。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>data efficiency</td>
<td nowrap>indoor mobile manipulation benchmark</td>
<td nowrap>long-horizon mobile manipulation</td>
<td nowrap>project/code/data available</td>
<td nowrap>补足长程移动操作数据效率评测。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.05313">paper</a></td>
<td nowrap><a href="https://lambdabenchmark.github.io/">project</a></td>
<td nowrap><a href="https://github.com/h2r/LAMBDA">code</a></td>
<td nowrap><a href="https://github.com/h2r/LAMBDA">data</a></td>
</tr>
<tr>
<td nowrap>ICRA 2025</td>
<td nowrap><a href="https://github.com/BAAI-DCAI/SpatialBot">SpatialBot: Precise Spatial Understanding with Vision Language Models</a></td>
<td nowrap>SpatialBot 面向 VLM 精确空间理解，提供 embodiment 数据、SpatialQA 和 SpatialBench。</td>
<td nowrap>spatial understanding benchmark</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>VLM spatial reasoning</td>
<td nowrap>embodied spatial QA</td>
<td nowrap>model/data/benchmark available</td>
<td nowrap>评测 VLM 是否具备可用于机器人操作的精确空间理解。</td>
<td nowrap><a href="https://github.com/BAAI-DCAI/SpatialBot">paper</a></td>
<td nowrap><a href="https://github.com/BAAI-DCAI/SpatialBot">project</a></td>
<td nowrap><a href="https://github.com/BAAI-DCAI/SpatialBot">code</a></td>
<td nowrap><a href="https://github.com/BAAI-DCAI/SpatialBot">data</a></td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=TRwQND3xpt">D2E: Scaling Vision-Action Pretraining on Desktop Data for Transfer to Embodied AI</a></td>
<td nowrap>用桌面交互数据扩展 vision-action 预训练并迁移到具身任务。</td>
<td nowrap>desktop-to-embodied dataset/pretraining</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>vision-action transfer</td>
<td nowrap>-</td>
<td nowrap>解决机器人数据稀缺下如何利用桌面数据预训练的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=TRwQND3xpt">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=PGUC3mmMoi">RoboInter: A Holistic Intermediate Representation Suite Towards Robotic Manipulation</a></td>
<td nowrap>构建面向机器人操作的中间表示套件，用于统一理解、规划和动作评测。</td>
<td nowrap>intermediate representation suite</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>robotic manipulation</td>
<td nowrap>-</td>
<td nowrap>解决操作学习缺少可复用中间表示基准的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=PGUC3mmMoi">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=UUE6HEtjhu">AutoBio: A Simulation and Benchmark for Robotic Automation in Digital Biology Laboratory</a></td>
<td nowrap>提供数字生物实验室机器人自动化仿真与基准。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>digital biology laboratory simulation</td>
<td nowrap>lab automation</td>
<td nowrap>-</td>
<td nowrap>解决生物实验室自动化缺少仿真和评测环境的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=UUE6HEtjhu">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=azj53PLJRL">Image Quality Assessment for Embodied AI</a></td>
<td nowrap>研究具身 AI 观测图像质量评估及其对任务表现的影响。</td>
<td nowrap>image quality benchmark</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>embodied perception/evaluation</td>
<td nowrap>-</td>
<td nowrap>解决具身感知输入质量缺少任务相关评估的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=azj53PLJRL">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=tQJYKwc3n4">RoboCasa365: A Large-Scale Simulation Framework for Training and Benchmarking Generalist Robots</a></td>
<td nowrap>提供大规模家庭场景仿真框架训练和评测通用机器人。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>RoboCasa simulation</td>
<td nowrap>generalist household robotics</td>
<td nowrap>-</td>
<td nowrap>解决通用机器人缺少多样、长期、可扩展仿真基准的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=tQJYKwc3n4">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38875">H-RDT: Human Manipulation Enhanced Bimanual Robotic Manipulation</a></td>
<td nowrap>利用第一视角人类操作数据预训练扩散 Transformer 策略，提升双臂机器人操作能力。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38875">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38883">PEOD: A Pixel-Aligned Event-RGB Benchmark for Object Detection Under Challenging Conditions</a></td>
<td nowrap>提供高分辨率像素对齐 Event-RGB 目标检测基准，覆盖弱光、过曝和高速场景。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38883">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38913">SIAM: Towards Generalizable Articulated Object Modeling via Single Robot-Object Interaction</a></td>
<td nowrap>从单次机器人-物体交互推断关节物体的部件分割、运动学和 URDF 式模型。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38913">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38923">VirtualEnv: A Platform for Embodied AI Research</a></td>
<td nowrap>提供 Unreal Engine 5 仿真平台，用于在交互式具身任务中评测 LLM/VLM 智能体。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38923">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>AAAI 2026</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38930">Lifelong Language-Conditioned Robotic Manipulation Learning</a></td>
<td nowrap>提出 SkillsCrafter，在持续学习语言条件操作技能时减少跨技能灾难性遗忘。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/article/view/38930">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64411">AIR-VLA: Vision-Language-Action Systems for Aerial Manipulation</a></td>
<td nowrap>构建空中操作系统的仿真、数据集和基准，用于评测 VLA/VLM 能力。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>无人机/空中机器人</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64411">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63391">DLO-Lab: Benchmarking Deformable Linear Object Manipulations with Differentiable Physics</a></td>
<td nowrap>提供可微物理仿真器和基准，用于柔性线状物体操作及 sim-to-real 研究。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63391">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63416">ManiSoft: Towards Vision-Language Manipulation for Soft Robotics</a></td>
<td nowrap>提供软体机械臂仿真基准，包含语言条件任务和专家轨迹，用于视觉语言操作研究。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/63416">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64619">OXE-AugE: A Large-Scale Robot Augmentation of OXE for Scaling Cross-Embodiment Policy Learning</a></td>
<td nowrap>用多样机器人本体扩展 Open X-Embodiment，以扩大跨本体策略学习规模。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64619">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.07961">BridgeVLA: Input-Output Alignment for Efficient 3D Manipulation Learning with Vision-Language Models</a></td>
<td nowrap>用输入输出对齐和 BridgeVLA 数据集提升 VLM 到 3D 操作策略学习效率。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>3D manipulation</td>
<td nowrap>Project+Code+Data/Bench</td>
<td nowrap>解决 VLM 学习 3D 操作时输入输出空间不匹配的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.07961">paper</a></td>
<td nowrap><a href="https://bridgevla.github.io/">project</a></td>
<td nowrap><a href="https://github.com/BridgeVLA/BridgeVLA">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.14763">RobotSmith: Generative Robotic Tool Design for Acquisition of Complex Manipulation Skills</a></td>
<td nowrap>用生成式工具设计让机器人获得刚体、柔性和流体对象的复杂操作技能。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>tool-design manipulation</td>
<td nowrap>Project+Code</td>
<td nowrap>解决机器人需要专用工具才能完成复杂操作的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.14763">paper</a></td>
<td nowrap><a href="https://umass-embodied-agi.github.io/RobotSmith/">project</a></td>
<td nowrap><a href="https://github.com/UMass-Embodied-AGI/RobotSmith">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2511.00940">URDF-Anything: Constructing Articulated Objects with 3D Multimodal Language Model</a></td>
<td nowrap>用 3D 多模态语言模型从多模态输入构建关节物体 URDF。</td>
<td nowrap>articulated object URDF construction</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>3D object modeling for simulation</td>
<td nowrap>-</td>
<td nowrap>解决仿真/机器人交互中 articulated object URDF 构建成本高的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2511.00940">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.08822">FreqPolicy: Efficient Flow-based Visuomotor Policy via Frequency Consistency</a></td>
<td nowrap>用频率一致性约束提升 flow-based 视觉运动策略效率和稳定性。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>frequency consistency</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决 flow policy 在视觉运动控制中高频/低频动作不一致问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.08822">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://www.arxiv.org/pdf/2506.06677">RoboCerebra: A Large-scale Benchmark for Long-horizon Robotic Manipulation Evaluation</a></td>
<td nowrap>提供长时程家庭机器人操作基准，评估规划、反思和记忆能力。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>100 task variants / 1,000 trajectories</td>
<td nowrap>Project+Code+Data/Bench</td>
<td nowrap>解决长时程机器人操作缺少系统评测的问题。</td>
<td nowrap><a href="https://www.arxiv.org/pdf/2506.06677">paper</a> / <a href="https://arxiv.org/pdf/2506.06677">paper</a></td>
<td nowrap><a href="https://robocerebra.github.io/">project</a></td>
<td nowrap><a href="https://github.com/qiuboxiang/RoboCerebra">code</a> / <a href="https://github.com/buaa-colalab/RoboCerebra">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/qiukingballball/RoboCerebra">hf</a> / <a href="https://huggingface.co/datasets/qiukingballball/RoboCerebraBench">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://suturebot.github.io/static/SutureBot_NeurIPS_2025.pdf">SutureBot: A Precision Framework &amp; Benchmark For Autonomous End-to-End Suturing</a></td>
<td nowrap>提供 dVRK 端到端自主缝合框架、数据集和精细评测基准。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>dVRK Si + wrist cameras/endoscope</td>
<td nowrap>-</td>
<td nowrap>Project+Code+Data/Bench</td>
<td nowrap>解决机器人自主缝合缺少端到端基准和数据的问题。</td>
<td nowrap><a href="https://suturebot.github.io/static/SutureBot_NeurIPS_2025.pdf">paper</a></td>
<td nowrap><a href="https://suturebot.github.io/">project</a></td>
<td nowrap><a href="https://github.com/SutureBot/SutureBot/tree/ACT">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/jchen396/SutureBot">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08367">Embodied Crowd Counting</a></td>
<td nowrap>定义具身人群计数任务，提供无人机仿真器、ECCD 数据集和零样本导航基线。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08367">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.06782">CARP: Visuomotor Policy Learning via Coarse-to-Fine Autoregressive Prediction</a></td>
<td nowrap>通过粗到细自回归预测提升视觉运动策略学习。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决连续机器人动作直接预测难、长时程误差累积的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.06782">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.16408">RoboFactory: Exploring Embodied Agent Collaboration with Compositional Constraints</a></td>
<td nowrap>构建带组合约束的多具身智能体协作仿真与数据集。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>simulation</td>
<td nowrap>-</td>
<td nowrap>Project+Code+Data/Bench</td>
<td nowrap>解决 embodied agent 协作任务中组合约束评测不足的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.16408">paper</a></td>
<td nowrap><a href="https://iranqin.github.io/robofactory/">project</a></td>
<td nowrap><a href="https://github.com/MARS-EAI/RoboFactory">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/FACEONG/RoboFactory_Dataset">hf</a></td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2504.10414">HUMOTO: A 4D Dataset of Mocap Human Object Interactions</a></td>
<td nowrap>提供人体-物体交互的 4D 动捕数据集。</td>
<td nowrap>4D mocap HOI dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决人体操作物体动态数据不足的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2504.10414">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2412.07215">RoboTron-Mani: All-in-One Multimodal Large Model for Robotic Manipulation</a></td>
<td nowrap>提出 RoboTron-Mani 模型及 RoboData，用多模态数据支持机器人操作。</td>
<td nowrap>RoboTron-Mani + RoboData</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Code+Data/Bench</td>
<td nowrap>解决机器人操作模型需要统一多模态训练和评测数据的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2412.07215">paper</a> / <a href="https://arxiv.org/pdf/2412.07215">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/RoboUniview/RoboMM">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/liufanfanlff/RoboData">hf</a></td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11117">Beyond the Destination: A Novel Benchmark for Exploration-Aware Embodied Question Answering</a></td>
<td nowrap>提出 EXPRESS-Bench，把探索轨迹和问答绑定评估 embodied QA。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>777 trajectories / 2,044 QA pairs</td>
<td nowrap>Code</td>
<td nowrap>解决 EQA 只看目的地、不评估探索过程的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2503.11117">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>EXPRESS-Bench</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1787">RobAVA: A Large-scale Dataset and Baseline Towards Video based Robotic Arm Action Understanding</a></td>
<td nowrap>提供大规模视频数据集和基线，用于机器人臂动作理解。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>提供训练/评测数据资源</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/1787">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/2215">RoboAnnotatorX: A Comprehensive and Universal Annotation Framework for Accurate Understanding of Long-horizon Robot Demonstration</a></td>
<td nowrap>提供多模态标注框架，为长时程机器人示教生成丰富标签。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://iccv.thecvf.com/virtual/2025/poster/2215">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2502.09560">EmbodiedBench: Comprehensive Benchmarking Multi-modal Large Language Models for Vision-Driven Embodied Agents</a></td>
<td nowrap>综合评测 MLLM 在视觉驱动具身智能体中的导航、交互和推理能力。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>1,128 tasks / 4 environments / 6 capability subsets</td>
<td nowrap>Project+Code</td>
<td nowrap>解决多模态大模型具身能力缺少统一基准的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2502.09560">paper</a></td>
<td nowrap><a href="https://embodiedbench.github.io/">project</a></td>
<td nowrap><a href="https://github.com/EmbodiedBench/EmbodiedBench">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18025">Pixel-aligned RGB-NIR Stereo Imaging and Dataset for Robot Vision</a></td>
<td nowrap>提供像素对齐 RGB-NIR 双目成像系统和机器人视觉数据集。</td>
<td nowrap>RGB-NIR stereo dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>robot vision</td>
<td nowrap>-</td>
<td nowrap>解决机器人视觉在可见光/NIR 融合下缺少对齐数据的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2411.18025">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
</tbody>
</table>

#### sim2real

共 17 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>对象类型</th>
<th nowrap>效率指标</th>
<th nowrap>平台/硬件</th>
<th nowrap>覆盖任务</th>
<th nowrap>开放资源状态</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=W3Q2xvrZtx">PD$^{2}$GS: Part-Level Decoupling and Continuous Deformation of Articulated Objects via Gaussian Splatting</a></td>
<td nowrap>用部件级解耦和连续形变高斯表示建模关节物体。</td>
<td nowrap>articulated object Gaussian Splatting</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决 articulated object 在真实/仿真中可变形建模的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=W3Q2xvrZtx">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=sWyX1BpeN4">Manipulation as in Simulation: Enabling Accurate Geometry Perception in Robots</a></td>
<td nowrap>让机器人获得接近仿真的准确几何感知以提升真实操作。</td>
<td nowrap>geometry perception for manipulation</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>real robot manipulation</td>
<td nowrap>-</td>
<td nowrap>解决真实机器人几何感知噪声导致 sim2real 操作差距的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=sWyX1BpeN4">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=nAO9LcV7nE">Emergent Dexterity Via Diverse Resets and Large-Scale Reinforcement Learning</a></td>
<td nowrap>通过多样化 reset 和大规模 RL 训练涌现灵巧操作能力。</td>
<td nowrap>dexterous RL</td>
<td nowrap>sim2real</td>
<td nowrap>sim + robot hand likely</td>
<td nowrap>dexterous manipulation</td>
<td nowrap>-</td>
<td nowrap>解决灵巧操作策略从仿真训练到复杂状态恢复的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=nAO9LcV7nE">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=H4SyKHjd4c">Sim2Real VLA: Zero-Shot Generalization of Synthesized Skills to Realistic Manipulation</a></td>
<td nowrap>将合成技能训练的 VLA 零样本迁移到真实感操作环境。</td>
<td nowrap>sim2real VLA</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>realistic manipulation</td>
<td nowrap>-</td>
<td nowrap>解决合成技能到真实机器人操作的泛化问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=H4SyKHjd4c">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=TmYcqOnxhN">Exo-Plore: Exploring Exoskeleton Control Space through Human-aligned Simulation</a></td>
<td nowrap>用人体对齐仿真探索外骨骼控制空间。</td>
<td nowrap>exoskeleton control</td>
<td nowrap>sim2real</td>
<td nowrap>human-aligned simulation/exoskeleton</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决外骨骼控制策略难以安全高效探索的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=TmYcqOnxhN">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=yn9dzttHvT">Latent Adaptation of Foundation Policies for Sim-to-Real Transfer</a></td>
<td nowrap>在潜变量空间适配 foundation policy 以完成 sim-to-real 迁移。</td>
<td nowrap>latent policy adaptation</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>sim-to-real policy transfer</td>
<td nowrap>-</td>
<td nowrap>解决基础机器人策略在真实域分布偏移下性能下降的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=yn9dzttHvT">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=OutljIofvS">RobotArena ∞: Scalable Robot Benchmarking via Real-to-Sim Translation</a></td>
<td nowrap>通过 real-to-sim 翻译扩展真实机器人场景的可评测基准。</td>
<td nowrap>real-to-sim benchmark</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决真实机器人 benchmark 扩展成本高的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=OutljIofvS">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=xlr3NqxUqY">Contact-guided Real2Sim from Monocular Video with Planar Scene Primitives</a></td>
<td nowrap>用接触线索和平面场景基元从单目视频重建 real2sim 场景。</td>
<td nowrap>contact-guided Real2Sim</td>
<td nowrap>sim2real</td>
<td nowrap>monocular video</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决单目视频转仿真缺少物理接触约束的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=xlr3NqxUqY">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66662">FlatLab: A Unified Methodology Framework and Simulation-Based Benchmark for Robotic Manipulation of Flat Objects</a></td>
<td nowrap>提供统一方法框架和仿真基准，用于操作不同几何和材质的扁平物体。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/66662">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2602.20871">GeCo-SRT: Geometry-aware Continual Adaptation for Robotic Cross-Task Sim-to-Real Transfer</a></td>
<td nowrap>用几何感知持续适配支持跨任务 sim-to-real 迁移。</td>
<td nowrap>continual sim-to-real adaptation</td>
<td nowrap>sim2real</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决机器人策略跨任务真实迁移中几何差异和连续适配问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2602.20871">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.19626">EgoBridge: Domain Adaptation for Generalizable Imitation from Egocentric Human Data</a></td>
<td nowrap>将第一视角人类数据做域适配，用于可泛化机器人模仿学习。</td>
<td nowrap>human-to-robot domain adaptation</td>
<td nowrap>sim2real</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决 egocentric human data 到机器人策略的域差距问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.19626">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://openreview.net/forum?id=284GWLFtjU">DEAL: Diffusion Evolution Adversarial Learning for Sim-to-Real Transfer</a></td>
<td nowrap>结合扩散进化和对抗学习调节仿真器，缩小 RL 控制器的 sim-to-real 差距。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>缩小仿真到真实差距</td>
<td nowrap><a href="https://openreview.net/forum?id=284GWLFtjU">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2509.18631">Generalizable Domain Adaptation for Sim-and-Real Policy Co-Training</a></td>
<td nowrap>用 sim-and-real policy co-training 提升跨域泛化。</td>
<td nowrap>domain adaptation / co-training</td>
<td nowrap>sim2real</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决仿真和真实数据联合训练时域偏移影响策略泛化的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2509.18631">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2505.22634">LabUtopia: High-Fidelity Simulation and Hierarchical Benchmark for Scientific Embodied Agents</a></td>
<td nowrap>提供科学实验室高保真仿真、场景生成和分层 benchmark。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>sim2real</td>
<td nowrap>LabSim</td>
<td nowrap>30 lab tasks / 200+ assets</td>
<td nowrap>Project</td>
<td nowrap>解决科学具身智能体缺少复杂实验流程仿真和评测的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2505.22634">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2507.01152">SonoGym: High Performance Simulation for Challenging Surgical Tasks with Robotic Ultrasound</a></td>
<td nowrap>提供可并行的机器人超声手术仿真环境和任务。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>sim2real</td>
<td nowrap>robotic ultrasound</td>
<td nowrap>-</td>
<td nowrap>Code</td>
<td nowrap>解决机器人超声导航/重建缺少真实高效仿真训练环境的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2507.01152">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/SonoGym/SonoGym">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICCV 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.22756">RoboPearls: Editable Video Simulation for Robot Manipulation</a></td>
<td nowrap>用 3DGS 从示教视频构建可编辑、照片级机器人操作仿真。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>editable video simulation</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>Project</td>
<td nowrap>解决真实示教采集贵和传统仿真 sim2real gap 大的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.22756">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2409.02920">RoboTwin: Dual-Arm Robot Benchmark with Generative Digital Twins (early version)</a></td>
<td nowrap>用生成式数字孪生创建双臂操作数据和真实对齐评测平台。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>dual-arm robot / COBOT Magic</td>
<td nowrap>-</td>
<td nowrap>Project+Code+Data/Bench</td>
<td nowrap>解决双臂操作数据稀缺和仿真评测不对齐真实的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2409.02920">paper</a></td>
<td nowrap><a href="https://robotwin-benchmark.github.io/early-version/">project</a></td>
<td nowrap><a href="https://github.com/RoboTwin-Platform/RoboTwin">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/TianxingChen/RoboTwin">hf</a></td>
</tr>
</tbody>
</table>

#### safety evaluation

共 12 篇。

<table>
<thead>
<tr>
<th nowrap>会议/年份</th>
<th nowrap>论文/方法</th>
<th nowrap>摘要</th>
<th nowrap>对象类型</th>
<th nowrap>效率指标</th>
<th nowrap>平台/硬件</th>
<th nowrap>覆盖任务</th>
<th nowrap>开放资源状态</th>
<th nowrap>论文任务/目标</th>
<th nowrap>Paper</th>
<th nowrap>Project</th>
<th nowrap>Code</th>
<th nowrap>Data/Bench</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>ICLR 2025</td>
<td nowrap><a href="https://proceedings.iclr.cc/paper_files/paper/2025/file/5ab848771ff8c9c47aac4128e2ef9f4e-Paper-Conference.pdf">HASARD: A Benchmark for Vision-Based Safe Reinforcement Learning in Embodied Agents</a></td>
<td nowrap>HASARD benchmarks vision-based safe reinforcement learning for embodied agents.</td>
<td nowrap>safety evaluation</td>
<td nowrap>safe-RL benchmark coverage</td>
<td nowrap>benchmark platform</td>
<td nowrap>vision-based safe RL</td>
<td nowrap>HASARD</td>
<td nowrap>Evaluate safe RL agents under embodied visual observations.</td>
<td nowrap><a href="https://arxiv.org/abs/2503.08241">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2022</td>
<td nowrap><a href="https://openreview.net/forum?id=dwi57JI_-K&noteId=pfmgIWaQAoN">SafeBench: A Benchmarking Platform for Safety Evaluation of Autonomous Vehicles</a></td>
<td nowrap>SafeBench provides a benchmark platform for autonomous-vehicle safety evaluation.</td>
<td nowrap>safety evaluation</td>
<td nowrap>autonomous driving safety scenarios</td>
<td nowrap>benchmark platform</td>
<td nowrap>driving safety evaluation</td>
<td nowrap>SafeBench</td>
<td nowrap>Evaluate safety risks in autonomous driving scenarios.</td>
<td nowrap><a href="https://arxiv.org/abs/2206.09682">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>IROS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2410.15185">Semantically Safe Robot Manipulation: From Semantic Scene Understanding to Motion Safeguards</a></td>
<td nowrap>该文用 LLM 推理 commonsense 语义风险，并把语义风险映射为机器人操作安全过滤。</td>
<td nowrap>semantic safety layer</td>
<td nowrap>safety evaluation</td>
<td nowrap>robot manipulation safety</td>
<td nowrap>semantic scene understanding + safeguards</td>
<td nowrap>project available</td>
<td nowrap>将语义风险纳入机器人操作安全闭环。</td>
<td nowrap><a href="https://arxiv.org/abs/2410.15185">paper</a></td>
<td nowrap><a href="https://utiasdsl.github.io/semantic-manipulation/">project</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=8s5jBVybhQ">Remotely Detectable Robot Policy Watermarking</a></td>
<td nowrap>提出 CoNoCo，在远程视频/动捕观测中检测机器人策略水印且不影响动作分布。</td>
<td nowrap>policy watermarking</td>
<td nowrap>safety</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>remote safety/provenance detection</td>
<td nowrap>-</td>
<td nowrap>解决机器人策略知识产权和未授权使用的远程验证问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=8s5jBVybhQ">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICLR 2026</td>
<td nowrap><a href="https://openreview.net/forum?id=Gsrw1vxq1G">RoboMD: Uncovering Robot Vulnerabilities through Semantic Potential Fields</a></td>
<td nowrap>RoboMD 在语义视觉嵌入势场中主动搜索脆弱区域，用于安全发现和再训练。</td>
<td nowrap>vulnerability discovery</td>
<td nowrap>safety</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>manipulation robustness</td>
<td nowrap>-</td>
<td nowrap>解决真实机器人漏洞测试昂贵且未知扰动难枚举的问题。</td>
<td nowrap><a href="https://openreview.net/forum?id=Gsrw1vxq1G">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60472">Any3D-VLA: Enhancing VLA Robustness via Diverse Point Clouds</a></td>
<td nowrap>融合多样点云输入和 2D 观测，提升 VLA 在仿真、传感器和真实域中的鲁棒性。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>评估鲁棒性和安全性</td>
<td nowrap>-</td>
<td nowrap>评估鲁棒性和安全性</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/60472">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62679">PACT: Self-Evolving Physical Safety Alignment for Diffusion Policies in Embodied Manipulation</a></td>
<td nowrap>用物理约束对齐后训练扩散策略，在无需示教或奖励的情况下减少安全违规。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>safety</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/62679">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61584">SafeLab: An Interactive High-Fidelity Benchmark for Embodied Safety in Scientific Robotics</a></td>
<td nowrap>提供高保真实验室仿真安全基准，包含安全任务、校准资产和专家轨迹。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>safety</td>
<td nowrap>仿真/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/61584">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>ICML 2026</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64080">Dismantling the Illusion of Vision-Language-Action Models Competence via Explicit Distributional Shifts</a></td>
<td nowrap>提出 LIBERO-Gen，通过显式语义和环境分布偏移揭示 VLA 的脆弱性。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap><a href="https://icml.cc/virtual/2026/poster/64080">paper</a></td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>CVPR 2026</td>
<td nowrap><a href="https://arxiv.org/abs/2510.13626">LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models</a></td>
<td nowrap>通过七类扰动和 10,030 个任务系统揭示 VLA 鲁棒性缺陷。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>7 perturbation dimensions / 10,030 tasks</td>
<td nowrap>Project+Code+Data/Bench</td>
<td nowrap>解决 VLA 在标准 benchmark 上高分但对真实扰动脆弱的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2510.13626">paper</a> / <a href="https://arxiv.org/pdf/2510.13626">paper</a></td>
<td nowrap><a href="https://sylvestf.github.io/LIBERO-plus/">project</a></td>
<td nowrap><a href="https://github.com/sylvestf/LIBERO-plus">code</a></td>
<td nowrap><a href="https://huggingface.co/datasets/Sylvest/LIBERO-plus">hf</a></td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.05294">A Smooth Sea Never Made a Skilled SAILOR: Robust Imitation via Learning to Search</a></td>
<td nowrap>SAILOR 从示教学习搜索、世界模型和奖励模型，使模仿策略能从错误状态恢复。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>safety</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>12 visual manipulation tasks</td>
<td nowrap>Project</td>
<td nowrap>解决行为克隆离开示教分布后不会恢复的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.05294">paper</a></td>
<td nowrap>-</td>
<td nowrap><a href="https://github.com/arnavkj1995/SAILOR">code</a></td>
<td nowrap>-</td>
</tr>
<tr>
<td nowrap>NeurIPS 2025</td>
<td nowrap><a href="https://arxiv.org/abs/2506.23725">PAC Bench: Do Foundation Models Understand Prerequisites for Executing Manipulation Policies?</a></td>
<td nowrap>PAC Bench 评估 VLM 是否理解物体属性、可供性和约束等操作前置条件。</td>
<td nowrap>benchmark/dataset</td>
<td nowrap>safety</td>
<td nowrap>机器人部署/评测环境</td>
<td nowrap>-</td>
<td nowrap>-</td>
<td nowrap>解决基础模型高层机器人能力依赖的低层物理前提未被验证的问题。</td>
<td nowrap><a href="https://arxiv.org/abs/2506.23725">paper</a></td>
<td nowrap><a href="https://pacbench.github.io/">project</a></td>
<td nowrap>-</td>
<td nowrap>30k annotations / 673 images / 100 scenarios / 120 sim constraints</td>
</tr>
</tbody>
</table>


## 重点阅读顺序

1. 先看 VLN 和 Agentic Planning：确认“大范围规划”和“细粒度规划”分别解决什么。
2. 再看 VLA 和 WAM：区分“直接动作生成”和“先想象/预测再执行”。
3. 最后看本体扩展、轻量化、评测：这些决定路线能不能真实部署。

## 源仓库补充条目

以下条目来自本次保存的 README 快照，不并入方向主表；它们用于跟踪 WAM 数据源和 RL-VLA 方法线索。

<table>
<thead>
<tr>
<th nowrap>条目</th>
<th nowrap>来源</th>
<th nowrap>方向</th>
<th nowrap>时间</th>
<th nowrap>资源</th>
<th nowrap>为什么跟踪</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap>UnifoLM-WBT Dataset</td>
<td nowrap>WAM</td>
<td nowrap>WAM training data / robot-centric</td>
<td nowrap>2026-03</td>
<td nowrap><a href="https://huggingface.co/collections/unitreerobotics/unifolm-wbt-dataset">dataset</a></td>
<td nowrap>机器人中心数据源，适合后续看 WAM 训练数据覆盖。</td>
</tr>
<tr>
<td nowrap>DexUMI</td>
<td nowrap>WAM</td>
<td nowrap>UMI / dexterous manipulation data</td>
<td nowrap>2025-05</td>
<td nowrap><a href="https://arxiv.org/pdf/2505.21864">paper</a> / <a href="https://dex-umi.github.io/">web</a> / <a href="https://umi-data.github.io/">dataset</a> / <a href="https://github.com/real-stanford/DexUMI">code</a></td>
<td nowrap>手部交互数据源，连接 WAM 与灵巧操作。</td>
</tr>
<tr>
<td nowrap>InternData-A1 / InternVLA-A1</td>
<td nowrap>WAM</td>
<td nowrap>simulation + VLA data</td>
<td nowrap>2026-01</td>
<td nowrap><a href="https://arxiv.org/pdf/2601.02456">paper</a> / <a href="https://internrobotics.github.io/interndata-a1.github.io/">web</a> / <a href="https://huggingface.co/datasets/InternRobotics/InternData-A1">dataset</a> / <a href="https://github.com/InternRobotics/InternVLA-A1">code</a></td>
<td nowrap>同时有数据、模型和代码，适合作为 VLA/WAM 联合入口。</td>
</tr>
<tr>
<td nowrap>EgoDex</td>
<td nowrap>WAM</td>
<td nowrap>egocentric dexterous data</td>
<td nowrap>2025-05</td>
<td nowrap><a href="https://arxiv.org/pdf/2505.11709">paper</a> / <a href="https://github.com/apple/ml-egodex">dataset+code</a></td>
<td nowrap>第一视角灵巧操作数据，适合补足人类视频到机器人策略的链路。</td>
</tr>
<tr>
<td nowrap>ARM</td>
<td nowrap>RL-VLA</td>
<td nowrap>Offline RL-VLA / real robot</td>
<td nowrap>2026.4</td>
<td nowrap><a href="https://arxiv.org/pdf/2604.03037">paper</a> / <a href="https://aiming1998.github.io/ARM/">project</a></td>
<td nowrap>基于 GR00T N1.5 的真实机器人 RL-VLA 方法。</td>
</tr>
<tr>
<td nowrap>LaST-R1</td>
<td nowrap>RL-VLA</td>
<td nowrap>Online RL-VLA / simulation</td>
<td nowrap>2026.04</td>
<td nowrap><a href="https://arxiv.org/abs/2604.28192">paper</a></td>
<td nowrap>RL-VLA 在线训练线索，适合后续补到 VLA 微调方向。</td>
</tr>
<tr>
<td nowrap>POCO</td>
<td nowrap>RL-VLA</td>
<td nowrap>Offline + Online RL-VLA</td>
<td nowrap>2026.04</td>
<td nowrap><a href="https://arxiv.org/abs/2604.01860">paper</a> / <a href="https://cccedric.github.io/poco/">project</a></td>
<td nowrap>覆盖 sim 和 real，且连接 π0/Octo 与 RL 优化。</td>
</tr>
<tr>
<td nowrap>FASTER</td>
<td nowrap>RL-VLA</td>
<td nowrap>Test-time RL-VLA</td>
<td nowrap>2026.04</td>
<td nowrap><a href="https://arxiv.org/abs/2604.19730">paper</a></td>
<td nowrap>测试时 action optimization 线索，适合跟踪 VLA 执行期优化。</td>
</tr>
</tbody>
</table>

## 数据来源说明

GitHub 源仓库的元数据和 README 快照见 [`sources/github/repos.json`](sources/github/repos.json)；历史来源 ID 保留在该文件中，便于追溯。

<table>
<thead>
<tr>
<th nowrap>来源</th>
<th nowrap>用途</th>
</tr>
</thead>
<tbody>
<tr>
<td nowrap><a href="https://ccf.atom.im/">CCF 2026 推荐目录</a></td>
<td nowrap>核对 2026 版 CCF-A 人工智能会议口径。</td>
</tr>
<tr>
<td nowrap><a href="https://github.com/Songwxuan/Embodied-AI-Paper-TopConf">Songwxuan/Embodied-AI-Paper-TopConf</a></td>
<td nowrap>CCF-A 论文主来源，按会议和方向分类；论文、代码和项目页链接优先采用该仓库中已给出的资源。</td>
</tr>
<tr>
<td nowrap><a href="https://openreview.net/group?id=ICLR.cc/2026/Conference">ICLR 2026 OpenReview</a></td>
<td nowrap>核对 ICLR 2026 公开论文页和 PDF 资源。</td>
</tr>
<tr>
<td nowrap><a href="https://ojs.aaai.org/index.php/AAAI/issue/view/703">AAAI-26 Intelligent Robotics proceedings</a></td>
<td nowrap>核对并补入 AAAI 2026 机器人方向论文。</td>
</tr>
<tr>
<td nowrap><a href="https://ras.papercept.net/conferences/scripts/start.pl">IEEE RAS PaperCept programs</a></td>
<td nowrap>核对 ICRA 2026 和 IROS 2025 官方程序页；本环境访问 ICRA 2025 PaperCept 返回拒绝。</td>
</tr>
<tr>
<td nowrap><a href="https://arxiv.org/">arXiv and author project pages for ICRA/IROS papers</a></td>
<td nowrap>在正式 proceedings 或完整论文列表尚不稳定时，交叉核对 ICRA 2025 与 IROS 2026 论文。</td>
</tr>
<tr>
<td nowrap><a href="https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln">jonyzhang2023/awesome-embodied-vla-va-vln</a></td>
<td nowrap>参考 VLA、WAM、VLN、VA 和 survey 的组织方式。</td>
</tr>
<tr>
<td nowrap><a href="https://github.com/OpenMOSS/Awesome-WAM">OpenMOSS/Awesome-WAM</a></td>
<td nowrap>参考 WAM 的 cascaded/joint、autoregressive/diffusion、evaluation/training data 分类。</td>
</tr>
<tr>
<td nowrap><a href="https://github.com/UCSB-AI/awesome-vision-language-navigation">UCSB-AI/awesome-vision-language-navigation</a></td>
<td nowrap>参考 VLN 的 dataset、evaluation、representation、action strategy、planning、asking for help 分类。</td>
</tr>
<tr>
<td nowrap><a href="https://github.com/DelinQu/awesome-vision-language-action-model">DelinQu/awesome-vision-language-action-model</a></td>
<td nowrap>参考 VLA 里程碑时间线。</td>
</tr>
<tr>
<td nowrap><a href="https://github.com/yueen-ma/Awesome-VLA">yueen-ma/Awesome-VLA</a></td>
<td nowrap>参考 VLA components、world models、reasoning、policy steering、low-level/high-level planners 分类。</td>
</tr>
</tbody>
</table>
