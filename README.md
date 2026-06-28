# 具身智能前沿方向调研结果

更新日期：2026-06-28

本 README 是调研结果本身：按方向总结具身智能前沿，并把已读 GitHub 仓库中明确归属 CCF-A 会议的论文整理成表。

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

## 参考仓库

| 仓库 | 用途 |
| --- | --- |
| [Songwxuan/Embodied-AI-Paper-TopConf](https://github.com/Songwxuan/Embodied-AI-Paper-TopConf) | CCF-A/顶会论文主来源，按会议和方向分类。 |
| [jonyzhang2023/awesome-embodied-vla-va-vln](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln) | 综合参考 VLA、WAM、VLN、VA 和 survey 的组织方式。 |
| [OpenMOSS/Awesome-WAM](https://github.com/OpenMOSS/Awesome-WAM) | WAM 分类参考：cascaded/joint、autoregressive/diffusion、evaluation/training data。 |
| [UCSB-AI/awesome-vision-language-navigation](https://github.com/UCSB-AI/awesome-vision-language-navigation) | VLN 分类参考：dataset、evaluation、representation、action strategy、planning、asking for help。 |
| [DelinQu/awesome-vision-language-action-model](https://github.com/DelinQu/awesome-vision-language-action-model) | VLA 里程碑时间线参考。 |
| [yueen-ma/Awesome-VLA](https://github.com/yueen-ma/Awesome-VLA) | VLA taxonomy 参考：components、world models、reasoning、policy steering、low-level/high-level planners。 |

下方 CCF-A 表基于这些仓库在 2026-06-28 可读到的内容整理；会议名按论文来源中的标注保留。

## 方向概览

| 方向 | 总结 | CCF-A 条目数 |
| --- | --- | --- |
| VLN / 大范围导航 | VLN 侧重大范围任务规划、语言 grounding、地图/记忆、连续环境导航和失败恢复；本体可先抽象成移动点，但表中开始出现无人机、城市导航、多场景 lifelong navigation 等更物理化的问题。 | 34 |
| VLA / 操作策略 | VLA 是机械臂和移动操作的主战场，核心不只是“大模型接动作头”，还包括 action representation、diffusion/flow policy、3D grounding、online/RL fine-tuning 和安全鲁棒性。 | 110 |
| WAM / 世界模型 | WAM 把未来世界状态预测和动作生成合在一起，更适合作为 agent 与低层控制之间的想象、验证和失败恢复层。 | 22 |
| Agentic Planning / 推理规划 | 这一方向关注任务分解、推理、记忆、监控、自改进和规划可执行性，是“agent 规划 + 小模型/传统控制执行”路线的核心。 | 48 |
| 本体扩展 / 灵巧操作 | 具身智能正在从单机械臂扩展到 humanoid、bimanual、dexterous hand、tactile/contact-rich manipulation，本体差异会直接影响动作空间和控制策略。 | 28 |
| 轻量化 / 评测 / 数据 | 部署侧重点包括高效 action tokenization、quantization、cache、real-time execution，以及更真实的 benchmark、dataset 和安全评测。 | 45 |

## 各方向 CCF-A 论文

### VLN / 大范围导航

VLN 侧重大范围任务规划、语言 grounding、地图/记忆、连续环境导航和失败恢复；本体可先抽象成移动点，但表中开始出现无人机、城市导航、多场景 lifelong navigation 等更物理化的问题。

导航类论文主要来自 VLN、Navigation、Embodied Navigation/Simulation 等分类。

共 34 篇。

| 会议 | 原分类 | 论文 |
| --- | --- | --- |
| ICML2026 | Vision-Language-Navigation Models | [AdaNav: Adaptive Reasoning with Uncertainty for Vision-Language Navigation](https://icml.cc/virtual/2026/poster/61535) |
| ICML2026 | Vision-Language-Navigation Models | [Instruction Decomposition and Action Alignment for Vision-Language Navigation](https://icml.cc/virtual/2026/poster/64780) |
| ICML2026 | Vision-Language-Navigation Models | [MapDream: Task-Driven Map Learning for Vision-Language Navigation](https://icml.cc/virtual/2026/poster/64902) |
| ICML2026 | Vision-Language-Navigation Models | [SC$^{2}$-WM: A Self-Correcting World Model with Closed-Loop Feedback for Vision-and-Language Navigation in Continuous Environments](https://icml.cc/virtual/2026/poster/64257) |
| ICML2026 | Navigation | [TIC-VLA: A Think-in-Control Vision-Language-Action Model for Robot Navigation in Dynamic Environments](https://icml.cc/virtual/2026/poster/65809) |
| ICML2026 | Navigation | [Hydra-Nav: Object Navigation via Adaptive Dual-Process Reasoning](https://icml.cc/virtual/2026/poster/61357) |
| ICML2026 | Navigation | [Plan in Sandbox, Navigate in Open Worlds: Learning Physics-Grounded Abstracted Experience for Embodied Navigation](https://icml.cc/virtual/2026/poster/63554) |
| ICML2026 | Navigation | [SafeDec: Constrained Decoding for Safe Autoregressive Generalist Robot Navigation Policies](https://icml.cc/virtual/2026/poster/60775) |
| CVPR2026 | Embodied Navigation, Planning and Simulation | [GLMap: Multi-Scale Gaussian-Language Map for Zero-shot Embodied Navigation and Reasoning](https://arxiv.org/abs/2605.01736) |
| CVPR2026 | Embodied Navigation, Planning and Simulation | [Wanderland: Geometrically Grounded Simulation for Open-World Embodied AI](https://arxiv.org/abs/2511.20620) |
| CVPR2026 | Embodied Navigation, Planning and Simulation | [SpaceTools: Tool-Augmented Spatial Reasoning via Double Interactive RL](https://arxiv.org/abs/2512.04069) |
| CVPR2026 | Embodied Navigation, Planning and Simulation | [Dexterous World Models](https://arxiv.org/abs/2512.17907) |
| NeurIPS2025 | Navigation | [C-NAV: Towards Self-Evolving Continual Object Navigation in Open World](https://arxiv.org/abs/2510.20685) |
| NeurIPS2025 | Navigation | [Distilling LLM Prior to Flow Model for Generalizable Agent’s Imagination in Object Goal Navigation](https://arxiv.org/abs/2508.09423) |
| NeurIPS2025 | Navigation | TP-MDDN: Task-Preferenced Multi-Demand-Driven Navigation with Autonomous Decision-Making |
| NeurIPS2025 | Navigation | [Active Test-time Vision-Language Navigation](https://arxiv.org/abs/2506.06630) |
| NeurIPS2025 | Navigation | Aux-Think: Exploring Reasoning Strategies for Data-Efficient Vision-Language Navigation |
| NeurIPS2025 | Navigation | [EfficientNav: Towards On-Device Object-Goal Navigation with Navigation Map Caching and Retrieval](https://arxiv.org/abs/2510.18546) |
| NeurIPS2025 | Navigation | [Seeing through Uncertainty: Robust Task-Oriented Optimization in Visual Navigation](https://arxiv.org/abs/2510.00441) |
| NeurIPS2025 | Benchmark and Dataset | Synthesizing Photorealistic and Dynamic Urban Environments for Multimodal Robot Navigation and Collaboration |
| ICCV2025 | Vision-Language-Navigation Model | [Move to Understand a 3D Scene: Bridging Visual Grounding and Exploration for Efficient and Versatile Embodied Navigation](https://arxiv.org/abs/2507.04047) |
| ICCV2025 | Vision-Language-Navigation Model | [Rethinking the Embodied Gap in Vision-and-Language Navigation: A Holistic Study of Physical and Visual Disparities](https://arxiv.org/abs/2507.13019) |
| ICCV2025 | Vision-Language-Navigation Model | [P3Nav: A Unified Framework for Embodied Navigation Integrating Perception, Planning, and Prediction](https://arxiv.org/abs/2503.18525) |
| ICCV2025 | Vision-Language-Navigation Model | [SAME: Learning Generic Language-Guided Visual Navigation with State-Adaptive Mixture of Experts](https://arxiv.org/abs/2412.05552) |
| ICCV2025 | Vision-Language-Navigation Model | [NavMorph: A Self-Evolving World Model for Vision-and-Language Navigation in Continuous Environments](https://arxiv.org/abs/2506.23468) |
| ICCV2025 | Vision-Language-Navigation Model | [Harnessing Input-adaptive Inference for Efficient VLN](https://openreview.net/pdf?id=5gptKWnVPF) |
| ICCV2025 | Vision-Language-Navigation Model | [Embodied Navigation with Auxiliary Task of Action Description Prediction](https://iccv.thecvf.com/virtual/2025/poster/1984) |
| ICCV2025 | Vision-Language-Navigation Model | [3D Gaussian Map with Open-Set Semantic Grouping for Vision-Language Navigation](https://iccv.thecvf.com/virtual/2025/poster/299) |
| ICCV2025 | Vision-Language-Navigation Model | [NavQ: Learning a Q-Model for Foresighted Vision-and-Language Navigation](https://iccv.thecvf.com/virtual/2025/poster/944) |
| ICCV2025 | Vision-Language-Navigation Model | [monoVLN: Bridging the Observation Gap between Monocular and Panoramic Vision and Language Navigation](https://iccv.thecvf.com/virtual/2025/poster/1792) |
| ICCV2025 | Hierarchical Planning | [CogNav: Cognitive Process Modeling for Object Goal Navigation with LLMs](https://arxiv.org/abs/2412.10439) |
| ICCV2025 | Accelerating and Deploying | [COSMO: Combination of Selective Memorization for Low-cost Vision-and-Language Navigation](https://arxiv.org/abs/2503.24065) |
| ICCV2025 | Benchmark and Dataset | [MoMa-Kitchen: A 100K+ Benchmark for Affordance-Grounded Last-Mile Navigation in Mobile Manipulation](https://arxiv.org/abs/2503.11081) |
| CVPR2025 | Benchmark and Dataset | [RoboSense: Large-scale Dataset and Benchmark for Egocentric Robot Perception and Navigation in Crowded and Unstructured Environments](https://arxiv.org/abs/2408.15503) |

### VLA / 操作策略

VLA 是机械臂和移动操作的主战场，核心不只是“大模型接动作头”，还包括 action representation、diffusion/flow policy、3D grounding、online/RL fine-tuning 和安全鲁棒性。

操作策略类论文主要来自 VLA、Policy/Policies、Robot Learning and Policy、Grasp 等分类。

共 110 篇。

| 会议 | 原分类 | 论文 |
| --- | --- | --- |
| ICML2026 | Vision-Language-Action Models | [Vision-Language-Action Pretraining from Large-Scale Human Videos](https://icml.cc/virtual/2026/poster/62813) |
| ICML2026 | Vision-Language-Action Models | [RA-VLA: Retrieval-Augmented VLA for Test-Time Adaptation](https://icml.cc/virtual/2026/poster/60980) |
| ICML2026 | Vision-Language-Action Models | [A Generalist Pair-wise Progress Critic Model for Vision-Language-Action Robots](https://icml.cc/virtual/2026/poster/62270) |
| ICML2026 | Vision-Language-Action Models | [Bring My Cup! Personalizing Vision-Language-Action Models with Visual Attentive Prompting](https://icml.cc/virtual/2026/poster/62528) |
| ICML2026 | Vision-Language-Action Models | [Discrete Diffusion VLA: Bringing Discrete Diffusion to Action Decoding in Vision-Language-Action Policies](https://icml.cc/virtual/2026/poster/62902) |
| ICML2026 | Vision-Language-Action Models | [DyGRO-VLA: Cross-Task Scaling of Vision-Language-Action Models via Dynamic Grouped Residual Optimization](https://icml.cc/virtual/2026/poster/60681) |
| ICML2026 | Vision-Language-Action Models | HIER: Human-in-the-Loop Imagination-Execution Refinement for General Real-World Vision-Language-Action Models |
| ICML2026 | Vision-Language-Action Models | [LARA: Latent Action Representation Alignment for Vision-Language-Action Models](https://icml.cc/virtual/2026/poster/61232) |
| ICML2026 | Vision-Language-Action Models | [From Abstraction to Instantiation: Learning Behavioral Representation for Vision-Language-Action Model](https://icml.cc/virtual/2026/poster/66596) |
| ICML2026 | Vision-Language-Action Models | [From Noise to Intent: Anchoring Generative VLA Policies with Residual Bridges](https://icml.cc/virtual/2026/poster/62908) |
| ICML2026 | Vision-Language-Action Models | [VLA-ATTC: Adaptive Test-Time Compute for VLA Models with Relative Action Critic Model](https://icml.cc/virtual/2026/poster/61157) |
| ICML2026 | Vision-Language-Action Models | [SCALE: Self-uncertainty Conditioned Adaptive Looking and Execution for Vision-Language-Action Models](https://icml.cc/virtual/2026/poster/66066) |
| ICML2026 | Vision-Language-Action Models | [XR-1: Towards Versatile Vision-Language-Action Models via Learning Unified Vision-Motion Representations](https://icml.cc/virtual/2026/poster/64826) |
| ICML2026 | 3D Vision | [Any3D-VLA: Enhancing VLA Robustness via Diverse Point Clouds](https://icml.cc/virtual/2026/poster/60472) |
| ICML2026 | Policy | [STEP: Warm-Started Visuomotor Policies with Spatiotemporal Consistency Prediction](https://icml.cc/virtual/2026/poster/61717) |
| ICML2026 | Policy | [Demystifying Action Space Design for Robotic Manipulation Policies](https://icml.cc/virtual/2026/poster/65967) |
| ICML2026 | Policy | [Escaping the Diversity Trap in Robotic Manipulation via Anchor-Centric Adaptation](https://icml.cc/virtual/2026/poster/66510) |
| ICML2026 | Policy | [FocalPolicy: Frequency-Optimized Chunking and Locally Anchored Flow Matching for Coherent Visuomotor Policy](https://icml.cc/virtual/2026/poster/66520) |
| ICML2026 | Policy | [GeoMoLa: Geometry-Aware Motion Latents for Learning Robust Manipulation Policies](https://icml.cc/virtual/2026/poster/62176) |
| ICML2026 | Policy | [Learning Human-Robot Collaboration via Heterogeneous-Agent Lyapunov Policy Optimization](https://icml.cc/virtual/2026/poster/61049) |
| ICML2026 | Policy | [PACT: Self-Evolving Physical Safety Alignment for Diffusion Policies in Embodied Manipulation](https://icml.cc/virtual/2026/poster/62679) |
| ICML2026 | Policy | [Embodied Interpretability: Linking Causal Understanding to Generalization in Vision-Language-Action Models](https://icml.cc/virtual/2026/poster/63997) |
| CVPR2026 | Vision-Language-Action Models | [Evo-1: Lightweight Vision-Language-Action Model with Preserved Semantic Alignment](https://arxiv.org/abs/2511.04555) |
| CVPR2026 | Vision-Language-Action Models | [HiF-VLA: Hindsight, Insight and Foresight through Motion Representation for Vision-Language-Action Models](https://arxiv.org/abs/2512.09928) |
| CVPR2026 | Vision-Language-Action Models | [SaPaVe: Towards Active Perception and Manipulation in Vision-Language-Action Models for Robotics](https://arxiv.org/abs/2603.12193) |
| CVPR2026 | Vision-Language-Action Models | [SRPO: Self-Referential Policy Optimization for Vision-Language-Action Models](https://arxiv.org/abs/2511.15605) |
| CVPR2026 | Vision-Language-Action Models | [Adaptive Action Chunking at Inference-time for Vision-Language-Action Models](https://arxiv.org/abs/2604.04161) |
| CVPR2026 | Vision-Language-Action Models | [XL-VLA: Cross-Hand Latent Representation for Vision-Language-Action Models](https://arxiv.org/abs/2603.10158) |
| CVPR2026 | Robot Learning and Policy | [GeCo-SRT: Geometry-aware Continual Adaptation for Robotic Cross-Task Sim-to-Real Transfer](https://arxiv.org/abs/2602.20871) |
| CVPR2026 | Robot Learning and Policy | [Contact-Aware Neural Dynamics](https://arxiv.org/abs/2601.12796) |
| NeurIPS2025 | Vision-Language-Action Model | [AC-DiT: Adaptive Coordination Diffusion Transformer for Mobile Manipulation](https://arxiv.org/abs/2507.01961) |
| NeurIPS2025 | Vision-Language-Action Model | [CogVLA: Cognition-Aligned Vision-Language-Action Models via Instruction-Driven Routing & Sparsification](https://arxiv.org/abs/2508.21046) |
| NeurIPS2025 | Vision-Language-Action Model | [Exploring the Limits of Vision-Language-Action Manipulation in Cross-task Generalization](https://arxiv.org/abs/2505.15660) |
| NeurIPS2025 | Vision-Language-Action Model | [BadVLA: Towards Backdoor Attacks on Vision-Language-Action Models via Objective-Decoupled Optimization](https://arxiv.org/abs/2505.16640) |
| NeurIPS2025 | Vision-Language-Action Model | [Compliant Residual DAgger: Improving Real-World Contact-Rich Manipulation with Human Corrections](https://arxiv.org/abs/2506.16685) |
| NeurIPS2025 | Vision-Language-Action Model | [Robo2VLM: Improving Visual Question Answering using Large-Scale Robot Manipulation Data](https://arxiv.org/abs/2505.15517) |
| NeurIPS2025 | Vision-Language-Action Model | [Learning Spatial-Aware Manipulation Ordering](https://arxiv.org/abs/2510.25138) |
| NeurIPS2025 | Vision-Language-Action Model | [PRIMT: Preference-based Reinforcement Learning with Multimodal Feedback and Trajectory Synthesis from Foundation Models](https://arxiv.org/abs/2509.15607) |
| NeurIPS2025 | Vision-Language-Action Model | [PointMapPolicy: Structured Point Cloud Processing for Multi-Modal Imitation Learning](https://arxiv.org/abs/2510.20406) |
| NeurIPS2025 | Vision-Language-Action Model | 4D-VLA: Spatiotemporal Vision-Language-Action Pretraining with Cross-Scene Calibration |
| NeurIPS2025 | Vision-Language-Action Model | [Blindfolded Experts Generalize Better: Insights from Robotic Manipulation and Videogames](https://arxiv.org/abs/2510.24194) |
| NeurIPS2025 | Vision-Language-Action Model | [HiMaCon: Discovering Hierarchical Manipulation Concepts from Unlabeled Multi-Modal Data](https://arxiv.org/abs/2510.11321) |
| NeurIPS2025 | Vision-Language-Action Model | [Knowledge Insulating Vision-Language-Action Models: Train Fast, Run Fast, Generalize Better](https://arxiv.org/abs/2505.23705) |
| NeurIPS2025 | Vision-Language-Action Model | [Provable Ordering and Continuity in Vision-Language Pretraining for Generalizable Embodied Agents](https://arxiv.org/abs/2502.01218) |
| NeurIPS2025 | 3D Vision | [DynaRend: Learning 3D Dynamics via Masked Future Rendering for Robotic Manipulation](https://arxiv.org/abs/2510.24261) |
| NeurIPS2025 | 3D Vision | [Building 3D Representations and Generating Motions From a Single Image via Video-Generation](https://neurips.cc/virtual/2025/loc/san-diego/poster/118141) |
| NeurIPS2025 | Policy | Emerging Risks from Embodied AI Require Urgent Policy Action |
| NeurIPS2025 | Policy | [Human-assisted Robotic Policy Refinement via Action Preference Optimization](https://arxiv.org/abs/2506.07127) |
| NeurIPS2025 | Policy | *Hyper-GoalNet*: Goal-Conditioned Manipulation Policy Learning with HyperNetworks |
| NeurIPS2025 | Policy | [ReinFlow: Fine-tuning Flow Matching Policy with Online Reinforcement Learning](https://arxiv.org/abs/2505.22094) |
| NeurIPS2025 | Policy | Diversifying Parallel Ergodic Search: A Signature Kernel Evolution Strategy |
| NeurIPS2025 | Policy | [A Practical Guide for Incorporating Symmetry in Diffusion Policy](https://arxiv.org/abs/2505.13431) |
| NeurIPS2025 | Policy | [Latent Policy Barrier: Learning Robust Visuomotor Policies by Staying In-Distribution](https://arxiv.org/abs/2508.05941) |
| NeurIPS2025 | Policy | Real-World Reinforcement Learning of Active Perception Behaviors |
| NeurIPS2025 | Policy | [Act to See, See to Act: Diffusion-Driven Perception-Action Interplay for Adaptive Policies](https://arxiv.org/abs/2509.25822) |
| NeurIPS2025 | Policy | [Dynamic Test-Time Compute Scaling in Control Policy: Difficulty-Aware Stochastic Interpolant Policy](https://arxiv.org/abs/2511.20906) |
| NeurIPS2025 | Policy | [DynaGuide: Steering Diffusion Polices with Active Dynamic Guidance](https://arxiv.org/abs/2506.13922) |
| ICCV2025 | Vision-Language-Action Model | [Exploring the Adversarial Vulnerabilities of Vision-Language-Action Models in Robotics](https://arxiv.org/abs/2411.13587) |
| ICCV2025 | Vision-Language-Action Model | [Dita: Scaling Diffusion Transformer for Generalist Vision-Language-Action Policy](https://arxiv.org/abs/2503.19757) |
| ICCV2025 | Vision-Language-Action Model | [Moto: Latent Motion Token as the Bridging Language for Learning Robot Manipulation from Videos](https://arxiv.org/abs/2412.04445) |
| ICCV2025 | Vision-Language-Action Model | [A0: An Affordance-Aware Hierarchical Model for General Robotic Manipulation](https://arxiv.org/abs/2504.12636) |
| ICCV2025 | Vision-Language-Action Model | [FedVLA: Federated Vision-Language-Action Learning with Dual Gating Mixture-of-Experts for Robotic Manipulation](https://iccv.thecvf.com/virtual/2025/poster/1325) |
| ICCV2025 | Vision-Language-Action Model | [PASG: A Closed-Loop Framework for Automated Geometric Primitive Extraction and Semantic Anchoring in Robotic Manipulation](https://iccv.thecvf.com/virtual/2025/poster/225) |
| ICCV2025 | Vision-Language-Action Model | [SD2Actor: Continuous State Decomposition via Diffusion Embeddings for Robotic Manipulation](https://iccv.thecvf.com/virtual/2025/poster/1571) |
| ICCV2025 | Policy | [EC-Flow: Enabling Versatile Robotic Manipulation from Action-Unlabeled Videos via Embodiment-Centric Flow](https://arxiv.org/abs/2507.06224) |
| ICCV2025 | Policy | [Dense Policy: Bidirectional Autoregressive Learning of Actions](https://arxiv.org/abs/2503.13217) |
| ICCV2025 | Policy | [Learning Precise Affordances from Egocentric Videos for Robotic Manipulation](https://arxiv.org/abs/2408.10123v1) |
| ICCV2025 | Policy | [iManip: Skill-Incremental Learning for Robotic Manipulation](https://arxiv.org/abs/2503.07087) |
| ICCV2025 | Policy | [Spatial-Temporal Aware Visuomotor Diffusion Policy Learning](https://arxiv.org/abs/2507.06710) |
| ICCV2025 | Policy | [Wavelet Policy: Lifting Scheme for Policy Learning in Long-Horizon Tasks](https://arxiv.org/abs/2507.04331) |
| ICCV2025 | Policy | [4D Visual Pre-training for Robot Learning](https://iccv.thecvf.com/virtual/2025/poster/972) |
| ICCV2025 | Perception | [EmbodiedOcc: Embodied 3D Occupancy Prediction for Vision-based Online Scene Understanding](https://arxiv.org/abs/2412.04380) |
| ICCV2025 | Perception | [Embodied Image Captioning: Self-supervised Learning Agents for Spatially Coherent Image Descriptions](https://arxiv.org/abs/2504.08531) |
| ICML2025 | Vision-Language-Action Models | [Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models](https://arxiv.org/abs/2502.19417) |
| ICML2025 | Vision-Language-Action Models | OTTER: A Vision-Language-Action Model with Text-Aware Visual Feature Extraction |
| ICML2025 | Vision-Language-Action Models | UP-VLA: A Unified Understanding and Prediction Model for Embodied Agent |
| ICML2025 | Vision-Language-Action Models | ELEMENTAL: Interactive Learning from Demonstrations and Vision-Language Models for Reward Design in Robotics |
| ICML2025 | Vision-Language-Action Models | ReinboT: Amplifying Robot Visual-Language Manipulation with Reinforcement Learning |
| ICML2025 | Vision-Language-Action Models | A Large Recurrent Action Model: xLSTM enables Fast Inference for Robotics Tasks |
| ICML2025 | Policies | Pre-training Auto-regressive Robotic Models with 4D Representations |
| ICML2025 | Policies | Flow-based Domain Randomization for Learning and Sequencing Robotic Skills |
| ICML2025 | Policies | Learning Policy Committees for Effective Personalization in MDPs with Diverse Tasks |
| ICML2025 | Policies | Video Prediction Policy: A Generalist Robot Policy with Predictive Visual Representations |
| ICML2025 | Policies | STAR: Learning Diverse Robot Skill Abstractions through Rotation-Augmented |
| ICML2025 | 3D Vision | Unifying 2D and 3D Vision-Language Understanding |
| ICML2025 | 3D Vision | GAPrompt: Geometry-Aware Point Cloud Prompt for 3D Vision Model |
| CVPR2025 | Vision-Language-Action Models | [UniAct: Universal Actions For Enhanced Embodied Foundation Models](https://arxiv.org/abs/2501.10105) |
| CVPR2025 | Vision-Language-Action Models | [MoManipVLA: Transferring Vision-language-action Models for General Mobile Manipulation](https://arxiv.org/abs/2503.13446) |
| CVPR2025 | Vision-Language-Action Models | [SOLAMI: Social Vision-Language-Action Modeling for Immersive Interaction with 3D Autonomous Characters](https://arxiv.org/abs/2412.00174) |
| CVPR2025 | Vision-Language-Action Models | [A Data-Centric Revisit of Pre-Trained Vision Models for Robot Learning](https://arxiv.org/abs/2503.06960) |
| CVPR2025 | Vision-Language-Action Models | Think Small, Act Big: Primitive Prompt Learning for Lifelong Robot Manipulation |
| CVPR2025 | Vision-Language-Action Models | [Phoenix: A Motion-based Self-Reflection Framework for Fine-grained Robotic Action Correction](https://cvpr.thecvf.com/virtual/2025/poster/32789) |
| CVPR2025 | Vision-Language-Action Models | [OmniManip: Towards General Robotic Manipulation via Object-Centric Interaction Primitives as Spatial Constraints](https://arxiv.org/abs/2501.03841) |
| CVPR2025 | Vision-Language-Action Models | [Mitigating the Human-Robot Domain Discrepancy in Visual Pre-training for Robotic Manipulation](https://arxiv.org/abs/2406.14235) |
| CVPR2025 | Vision-Language-Action Models | Object-Centric Prompt-Driven Vision-Language-Action Model for Robotic Manipulation |
| CVPR2025 | Vision-Language-Action Models | Robotic Visual Instruction |
| CVPR2025 | Vision-Language-Action Models | RoboGround: Robot Manipulation with Grounded Vision-Language Priors |
| CVPR2025 | Policies | [RoboPEPP: Vision-Based Robot Pose and Joint Angle Estimation through Embedding Predictive Pre-Training](https://arxiv.org/abs/2411.17662) |
| CVPR2025 | Policies | [Lift3D Policy: Lifting 2D Foundation Models for Robust 3D Robotic Manipulation](https://arxiv.org/abs/2411.18623) |
| CVPR2025 | Policies | PDFactor: Learning Tri-Perspective View Policy Diffusion Field for Multi-Task Robotic Manipulation |
| CVPR2025 | Policies | Two by Two: Learning Cross-Task Pairwise Objects Assembly for Generalizable Robot Manipulation |
| CVPR2025 | Policies | FlowRAM: Grounding Flow Matching Policy with Region-Aware Mamba Framework for Robotic Manipulation |
| CVPR2025 | Policies | [G3Flow: Generative 3D Semantic Flow for Pose-aware and Generalizable Object Manipulation](https://arxiv.org/abs/2411.18369) |
| CVPR2025 | Policies | [Tra-MoE: Learning Trajectory Prediction Model from Multiple Domains for Adaptive Policy Conditioning](https://arxiv.org/abs/2411.14519) |
| CVPR2025 | Policies | [AffordDP: Generalizable Diffusion Policy with Transferable Affordance](https://arxiv.org/abs/2412.03142) |
| CVPR2025 | 3D Vision | [3D-MVP: 3D Multiview Pretraining for Robotic Manipulation](https://arxiv.org/abs/2406.18158) |
| CVPR2025 | 3D Vision | [VidBot: Learning Generalizable 3D Actions from In-the-Wild 2D Human Videos for Zero-Shot Robotic Manipulation](https://arxiv.org/abs/2503.07135) |
| CVPR2025 | 3D Vision | Touch2Shape: Touch-Conditioned 3D Diffusion for Shape Exploration and Reconstruction |
| CVPR2025 | Sim2real and Real2sim | [Prof. Robot: Differentiable Robot Rendering Without Static and Self-Collisions](https://arxiv.org/abs/2503.11269) |
| CVPR2025 | Sim2real and Real2sim | [AutoURDF: Unsupervised Robot Modeling from Point Cloud Frames Using Cluster Registration](https://arxiv.org/abs/2412.05507) |

### WAM / 世界模型

WAM 把未来世界状态预测和动作生成合在一起，更适合作为 agent 与低层控制之间的想象、验证和失败恢复层。

世界模型类论文主要来自 World Model(s)、Video/WAM 相关标题。

共 22 篇。

| 会议 | 原分类 | 论文 |
| --- | --- | --- |
| ICML2026 | World Models | [Cross-Embodiment Robot Foundation World Models with Latent Actions](https://icml.cc/virtual/2026/poster/63978) |
| ICML2026 | World Models | [DDP-WM: Disentangled Dynamics Prediction for Efficient World Models](https://icml.cc/virtual/2026/poster/62480) |
| ICML2026 | World Models | [DreamDojo: A Real-Time Robot World Model from Large-Scale Human Videos](https://icml.cc/virtual/2026/poster/65193) |
| ICML2026 | World Models | [RoboFlow4D: A Lightweight Flow World Model Toward Real-Time Flow-Guided Robotic Manipulation](https://icml.cc/virtual/2026/poster/62543) |
| ICML2026 | World Models | [Dual-Stream Diffusion for World-Model Augmented Vision-Language-Action Model](https://icml.cc/virtual/2026/poster/64447) |
| ICML2026 | World Models | [From Imagined Futures to Executable Actions: Mixture of Latent Actions for Robot Manipulation](https://icml.cc/virtual/2026/poster/66091) |
| ICML2026 | World Models | [Learning Task-Sufficient World Models by Synergizing Agentic Exploration and Structured Modeling](https://icml.cc/virtual/2026/poster/64209) |
| ICML2026 | World Models | [VLAW: Iterative Co-Improvement of Vision-Language-Action Policy and World Model](https://icml.cc/virtual/2026/poster/66169) |
| CVPR2026 | Vision-Language-Action Models | [CoWVLA: Chain of World: World Model Thinking in Latent Motion](https://arxiv.org/abs/2603.03195) |
| NeurIPS2025 | Vision-Language-Action Model | VideoVLA: Video Generators Can Be Generalizable Robot Manipulators |
| NeurIPS2025 | Vision-Language-Action Model | [EnerVerse: Envisioning Embodied Future Space for Robotics Manipulation](https://arxiv.org/abs/2501.01895) |
| NeurIPS2025 | Vision-Language-Action Model | [DreamVLA: A Vision-Language-Action Model Dreamed with Comprehensive World Knowledge](https://arxiv.org/abs/2507.04447) |
| NeurIPS2025 | World Model | [SAMPO: Scale-wise Autoregression with Motion Prompt for Generative World Models](https://arxiv.org/abs/2509.15536) |
| NeurIPS2025 | World Model | [Learning 3D Persistent Embodied World Models](https://arxiv.org/abs/2505.05495) |
| NeurIPS2025 | World Model | [OSVI-WM: One-Shot Visual Imitation for Unseen Tasks using World-Model-Guided Trajectory Generation](https://arxiv.org/abs/2505.20425) |
| ICCV2025 | World Model | [IRASim: A Fine-Grained World Model for Robot Manipulation](https://arxiv.org/abs/2406.14540) |
| ICCV2025 | World Model | [GWM: Towards Scalable Gaussian World Models for Robotic Manipulation](https://ziweiwangthu.github.io/data/GWM.pdf) |
| ICCV2025 | World Model | [DyWA: Dynamics-adaptive World Action Model for Generalizable Non-prehensile Manipulation](https://arxiv.org/abs/2503.16806) |
| ICCV2025 | World Model | [Diffusion-Based Imaginative Coordination for Bimanual Manipulation](https://arxiv.org/abs/2507.11296) |
| ICCV2025 | World Model | [Learning 4D Embodied World Models](https://openreview.net/pdf?id=mnwlhvmKMN) |
| CVPR2025 | Video | [TASTE-Rob: Advancing Video Generation of Task-Oriented Hand-Object Interaction for Generalizable Robotic Manipulation](https://arxiv.org/abs/2503.11423) |
| CVPR2025 | Video | [GraphMimic: Graph-to-Graphs Generative Modeling from Videos for Policy Learning](https://cvpr.thecvf.com/virtual/2025/poster/34942) |

### Agentic Planning / 推理规划

这一方向关注任务分解、推理、记忆、监控、自改进和规划可执行性，是“agent 规划 + 小模型/传统控制执行”路线的核心。

推理规划类论文主要来自 Planning and Reasoning、Hierarchical Planning，以及标题中带 planning、reasoning、memory、monitor、failure 等信号的条目。

共 48 篇。

| 会议 | 原分类 | 论文 |
| --- | --- | --- |
| ICML2026 | Vision-Language-Action Models | [HALO: A Unified Vision-Language-Action Model for Embodied Multimodal Chain-of-Thought Reasoning](https://icml.cc/virtual/2026/poster/61922) |
| ICML2026 | Vision-Language-Action Models | [HiMe: Hierarchical Embodied Memory for Long-Horizon Vision-Language-Action Control](https://icml.cc/virtual/2026/poster/60897) |
| ICML2026 | Vision-Language-Action Models | [Latent Reasoning VLA: Latent Thinking and Prediction for Vision-Language-Action Models](https://icml.cc/virtual/2026/poster/64290) |
| ICML2026 | Vision-Language-Action Models | [Sentinel-VLA: A Metacognitive VLA Model with Active Status Monitoring for Dynamic Reasoning and Error Recovery](https://icml.cc/virtual/2026/poster/61750) |
| ICML2026 | Vision-Language-Action Models | [Spatial Memory for Out-of-Vision Manipulation in Vision-Language-Action](https://icml.cc/virtual/2026/poster/66214) |
| ICML2026 | Vision-Language-Action Models | [NeurVLA: Unleashing Failure-Handling Capability of Vision-Language-Action Models via Neural-Symbolic Reasoning](https://icml.cc/virtual/2026/poster/63650) |
| ICML2026 | Vision-Language-Action Models | [LaST0: Latent Spatio-Temporal Chain-of-Thought for Robotic Vision-Language-Action Model](https://icml.cc/virtual/2026/poster/61887) |
| ICML2026 | Planning and Reasoning | [LAGEA: Language Guided Embodied Agents for Robotic Manipulation](https://icml.cc/virtual/2026/poster/60801) |
| ICML2026 | Planning and Reasoning | [TapSampling: Inference-Time Sampling with a Task-Progress-Understanding Verifier for Robotic Manipulation](https://icml.cc/virtual/2026/poster/60500) |
| ICML2026 | Planning and Reasoning | [Decompose and Recompose: Reasoning New Skills from Existing Abilities for Cross-Task Robotic Manipulation](https://icml.cc/virtual/2026/poster/63250) |
| ICML2026 | Planning and Reasoning | [Drift is a Sampling Error: SNR-Aware Power Distributions for Long-Horizon Robotic Planning](https://icml.cc/virtual/2026/poster/64055) |
| ICML2026 | Planning and Reasoning | [Can VLMs Diagnose and Recover from VLA Manipulation Faults?](https://icml.cc/virtual/2026/poster/64203) |
| CVPR2026 | Vision-Language-Action Models | [ACoT-VLA: Action Chain-of-Thought for Vision-Language-Action Models](https://arxiv.org/abs/2601.11404) |
| CVPR2026 | Vision-Language-Action Models | [OptimusVLA: Global Prior Meets Local Consistency: Dual-Memory Augmented Vision-Language-Action Model for Efficient Robotic Manipulation](https://arxiv.org/abs/2602.20200) |
| CVPR2026 | Vision-Language-Action Models | [Fast-ThinkAct: Efficient Vision-Language-Action Reasoning via Verbalizable Latent Planning](https://arxiv.org/abs/2601.09708) |
| NeurIPS2025 | Vision-Language-Action Model | [Fast-in-Slow: A Dual-System VLA Model Unifying Fast Manipulation within Slow Reasoning](https://arxiv.org/abs/2506.01953) |
| NeurIPS2025 | Vision-Language-Action Model | [ChatVLA-2: Vision-Language-Action Model with Open-World Reasoning](https://arxiv.org/abs/2505.21906) |
| NeurIPS2025 | Vision-Language-Action Model | [VLA-OS: Structuring and Dissecting Planning Representations and Paradigms in Vision-Language-Action Models](https://arxiv.org/abs/2506.17561) |
| NeurIPS2025 | Vision-Language-Action Model | [ThinkAct: Vision-Language-Action Reasoning via Reinforced Visual Latent Planning](https://arxiv.org/abs/2507.16815) |
| NeurIPS2025 | Vision-Language-Action Model | [Self-Improving Embodied Foundation Models](https://arxiv.org/abs/2509.15155) |
| NeurIPS2025 | Vision-Language-Action Model | [Chain-of-Action: Trajectory Autoregressive Modeling for Robotic Manipulation](https://arxiv.org/abs/2506.09990) |
| NeurIPS2025 | Vision-Language-Action Model | [SAFE: Multitask Failure Detection for Vision-Language-Action Models](https://arxiv.org/abs/2506.09937) |
| NeurIPS2025 | Planning and Reasoning | [Towards Reliable LLM-based Robots Planning via Combined Uncertainty Estimation](https://arxiv.org/abs/2510.08044) |
| NeurIPS2025 | Planning and Reasoning | [Towards Reliable Code-as-Policies: A Neuro-Symbolic Framework for Embodied Task Planning](https://arxiv.org/abs/2510.21302) |
| NeurIPS2025 | Planning and Reasoning | [RDD: Retrieval-Based Demonstration Decomposer for Planner Alignment in Long-Horizon Tasks](https://arxiv.org/abs/2510.14968) |
| NeurIPS2025 | Planning and Reasoning | [UniDomain: Pretraining a Unified PDDL Domain from Real-World Demonstrations for Generalizable Robot Task Planning](https://arxiv.org/abs/2507.21545) |
| NeurIPS2025 | Planning and Reasoning | InstructFlow: Adaptive Symbolic Constraint-Guided Code Generation for Long-Horizon Planning |
| NeurIPS2025 | Policy | [Failure Prediction at Runtime for Generative Robot Policies](https://arxiv.org/abs/2510.09459) |
| NeurIPS2025 | Policy | [World-aware Planning Narratives Enhance Large Vision-Language Model Planner](https://arxiv.org/abs/2506.21230) |
| NeurIPS2025 | Dexterous | [HumanoidGen: Data Generation for Bimanual Dexterous Manipulation via LLM Reasoning](https://arxiv.org/abs/2507.00833) |
| NeurIPS2025 | Dexterous | [DexFlyWheel: A Scalable and Self-improving Data Generation Framework for Dexterous Manipulation](https://arxiv.org/abs/2509.23829) |
| ICCV2025 | Vision-Language-Action Model | [Embodied VideoAgent: Persistent Memory from Egocentric Videos and Embodied Sensors Enables Dynamic Scene Understanding](https://arxiv.org/abs/2501.00358) |
| ICCV2025 | Vision-Language-Action Model | [CoA-VLA: Improving Vision-Language-Action Models via Visual-Text Chain-of-Affordance](https://iccv.thecvf.com/virtual/2025/poster/542) |
| ICCV2025 | Vision-Language-Action Model | [Towards Long-Horizon Vision-Language-Action System: Reasoning, Acting and Memory](https://iccv.thecvf.com/virtual/2025/poster/1915) |
| ICCV2025 | Hierarchical Planning | [Adaptive Articulated Object Manipulation On The Fly with Foundation Model Reasoning and Part Grounding](https://arxiv.org/abs/2507.18276) |
| ICCV2025 | Hierarchical Planning | [RoBridge: A Hierarchical Architecture Bridging Cognition and Execution for General Robotic Manipulation](https://arxiv.org/abs/2505.01709) |
| ICCV2025 | Benchmark and Dataset | [VLABench: A Large-Scale Benchmark for Language-Conditioned Robotics Manipulation with Long-Horizon Reasoning Tasks](https://arxiv.org/abs/2412.18194) |
| ICML2025 | Planning and Reasoning | Efficient Robotic Policy Learning via Latent Space Backward Planning |
| ICML2025 | Planning and Reasoning | Closed-Loop Long-Horizon Robotic Planning via Equilibrium Sequence Modeling |
| ICML2025 | Policies | SAM2Act:Integrating Visual Foundation Model with A Memory Architecture for Robotic Manipulation |
| ICML2025 | Dataset | WOMD-Reasoning: A Large-Scale Dataset for Interaction Reasoning in Driving |
| CVPR2025 | Vision-Language-Action Models | [CoT-VLA: Visual Chain-of-Thought Reasoning for Vision-Language-Action Models](https://cvpr.thecvf.com/virtual/2025/poster/33233) |
| CVPR2025 | Policies | [DexHandDiff: Interaction-aware Diffusion Planning for Adaptive Dexterous Manipulation](https://arxiv.org/abs/2411.18562) |
| CVPR2025 | Planning and Reasoning | [RoboBrain: A Unified Brain Model for Robotic Manipulation from Abstract to Concrete](https://arxiv.org/abs/2502.21257) |
| CVPR2025 | Planning and Reasoning | [PhysVLM: Enabling Visual Language Models to Understand Robotic Physical Reachability](https://arxiv.org/abs/2503.08481) |
| CVPR2025 | Planning and Reasoning | [RoboSpatial: Teaching Spatial Understanding to 2D and 3D Vision-Language Models for Robotics](https://arxiv.org/abs/2411.16537) |
| CVPR2025 | Planning and Reasoning | Tartan IMU: A Light Foundation Model for Inertial Positioning in Robotics |
| CVPR2025 | Planning and Reasoning | [Code-as-Monitor: Constraint-aware Visual Programming for Reactive and Proactive Robotic Failure Detection](https://arxiv.org/abs/2412.04455) |

### 本体扩展 / 灵巧操作

具身智能正在从单机械臂扩展到 humanoid、bimanual、dexterous hand、tactile/contact-rich manipulation，本体差异会直接影响动作空间和控制策略。

本体扩展类论文主要来自 Humanoid、Dexterous、Tactile，以及标题中明确出现 bimanual、dexterous、grasp、humanoid 等信号的条目。

共 28 篇。

| 会议 | 原分类 | 论文 |
| --- | --- | --- |
| ICML2026 | Humanoid | [Scalable and General Whole-Body Control for Cross-Humanoid Locomotion](https://icml.cc/virtual/2026/poster/62003) |
| ICML2026 | Humanoid | [Learning Transferable Interaction Primitives from Game Videos for Humanoids](https://icml.cc/virtual/2026/poster/65120) |
| ICML2026 | Dexterous Manipulation | [DexMachina: Functional Retargeting for Bimanual Dexterous Manipulation](https://icml.cc/virtual/2026/poster/63277) |
| ICML2026 | Dexterous Manipulation | [DECO: Decoupled Multimodal Diffusion Transformer for Bimanual Dexterous Manipulation with a Plugin Tactile Adapter](https://icml.cc/virtual/2026/poster/66358) |
| ICML2026 | Tactile | [Cross-Tactile Sensor Representation Learning](https://icml.cc/virtual/2026/poster/66793) |
| ICML2026 | Tactile | [Tabero: Learning Gentle Manipulation with Closed-Loop Force Feedback from Vision, Touch, and Language](https://icml.cc/virtual/2026/poster/65669) |
| CVPR2026 | Vision-Language-Action Models | [UniDex: A Robot Foundation Suite for Universal Dexterous Hand Control from Egocentric Human Videos](https://arxiv.org/abs/2603.22264) |
| CVPR2026 | Robot Learning and Policy | [VIRAL: Visual Sim-to-Real at Scale for Humanoid Loco-Manipulation](https://arxiv.org/abs/2511.15200) |
| NeurIPS2025 | Humanoid | [Adversarial Locomotion and Motion Imitation for Humanoid Policy Learning](https://arxiv.org/abs/2504.14305) |
| NeurIPS2025 | Humanoid | [From Experts to a Generalist: Toward General Whole-Body Control for Humanoid Robots](https://arxiv.org/abs/2506.12779) |
| NeurIPS2025 | Humanoid | [KungfuBot: Physics-Based Humanoid Whole-Body Control for Learning Highly-Dynamic Skills](https://kungfubot.github.io/) |
| NeurIPS2025 | Tactile | [Universal Visuo-Tactile Video Understanding for Embodied Interaction](https://arxiv.org/abs/2505.22566) |
| NeurIPS2025 | Tactile | [Enhancing Tactile-based Reinforcement Learning for Robotic Control](https://arxiv.org/abs/2510.21609) |
| NeurIPS2025 | Tactile | [Taccel: Scaling Up Vision-based Tactile Robotics via High-performance GPU Simulation](https://taccel-simulator.github.io/assets/taccel-paper.pdf) |
| NeurIPS2025 | Tactile | [Toward Artificial Palpation: Representation Learning of Touch on Soft Bodies](https://arxiv.org/abs/2511.16596) |
| NeurIPS2025 | Tactile | [Touch in the Wild: Learning Fine-Grained Manipulation with a Portable Visuo-Tactile Gripper](https://arxiv.org/abs/2507.15062v1) |
| NeurIPS2025 | Dexterous | [Contact Map Transfer with Conditional Diffusion Model for Generalizable Dexterous Grasp Generation](https://arxiv.org/pdf/2511.01276) |
| NeurIPS2025 | Dexterous | [Grasp2Grasp: Vision-Based Dexterous Grasp Translation via Schrödinger Bridges](https://arxiv.org/abs/2506.02489) |
| NeurIPS2025 | Dexterous | [Scaffolding Dexterous Manipulation with Vision-Language Models](https://arxiv.org/abs/2506.19212) |
| NeurIPS2025 | Dexterous | [DexGarmentLab: Dexterous Garment Manipulation Environment with Generalizable Policy](https://arxiv.org/abs/2505.11032) |
| ICCV2025 | Policy | [Rethinking Bimanual Robotic Manipulation: Learning with Decoupled Interaction Framework](https://arxiv.org/abs/2503.09186) |
| ICCV2025 | Policy | [AnyBimanual: Transferring Unimanual Policy for General Bimanual Manipulation](https://arxiv.org/abs/2412.06779) |
| CVPR2025 | Policies | [KStar Diffuser: Spatial-Temporal Graph Diffusion Policy with Kinematics Modeling for Bimanual Robotic Manipulation](https://arxiv.org/abs/2503.10743) |
| CVPR2025 | Grasp | [UniGraspTransformer: Simplified Policy Distillation for Scalable Dexterous Robotic Grasping](https://arxiv.org/abs/2412.02699) |
| CVPR2025 | Grasp | [DexGrasp Anything: Towards Universal Robotic Dexterous Grasping with Physics Awareness](https://arxiv.org/abs/2503.08257) |
| CVPR2025 | Grasp | [ZeroGrasp: Zero-Shot Shape Reconstruction Enabled Robotic Grasping](https://cvpr.thecvf.com/virtual/2025/poster/32440) |
| CVPR2025 | Humanoid | [Let Humanoid Robots Go Hiking! Integrative Skill Development over Complex Trails](https://cvpr.thecvf.com/virtual/2025/poster/34565) |
| CVPR2025 | Humanoid | [MobileH2R: Learning Generalizable Human to Mobile Robot Handover Exclusively from Scalable and Diverse Synthetic Data](https://arxiv.org/abs/2501.04595) |

### 轻量化 / 评测 / 数据

部署侧重点包括高效 action tokenization、quantization、cache、real-time execution，以及更真实的 benchmark、dataset 和安全评测。

轻量化/评测类论文主要来自 Accelerating and Deploying、Benchmark and Dataset、Data/Dataset，以及标题中明确出现 efficient、quant、cache、real-time 等信号的条目。

共 45 篇。

| 会议 | 原分类 | 论文 |
| --- | --- | --- |
| ICML2026 | Benchmark and Dataset | [AIR-VLA: Vision-Language-Action Systems for Aerial Manipulation](https://icml.cc/virtual/2026/poster/64411) |
| ICML2026 | Benchmark and Dataset | [DLO-Lab: Benchmarking Deformable Linear Object Manipulations with Differentiable Physics](https://icml.cc/virtual/2026/poster/63391) |
| ICML2026 | Benchmark and Dataset | [FlatLab: A Unified Methodology Framework and Simulation-Based Benchmark for Robotic Manipulation of Flat Objects](https://icml.cc/virtual/2026/poster/66662) |
| ICML2026 | Benchmark and Dataset | [ManiSoft: Towards Vision-Language Manipulation for Soft Robotics](https://icml.cc/virtual/2026/poster/63416) |
| ICML2026 | Benchmark and Dataset | [SafeLab: An Interactive High-Fidelity Benchmark for Embodied Safety in Scientific Robotics](https://icml.cc/virtual/2026/poster/61584) |
| ICML2026 | Benchmark and Dataset | [Dismantling the Illusion of Vision-Language-Action Models Competence via Explicit Distributional Shifts](https://icml.cc/virtual/2026/poster/64080) |
| ICML2026 | Benchmark and Dataset | [OXE-AugE: A Large-Scale Robot Augmentation of OXE for Scaling Cross-Embodiment Policy Learning](https://icml.cc/virtual/2026/poster/64619) |
| ICML2026 | Benchmark and Dataset | [RoboTwin 2.0: A Scalable Data Generator and Benchmark with Strong Domain Randomization for Robust Bimanual Robotic Manipulation](https://icml.cc/virtual/2026/poster/62192) |
| CVPR2026 | Vision-Language-Action Models | [QuantVLA: Scale-Calibrated Post-Training Quantization for Vision-Language-Action Models](https://arxiv.org/abs/2602.20309) |
| CVPR2026 | Benchmark and Dataset | [LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models](https://arxiv.org/abs/2510.13626) |
| NeurIPS2025 | Vision-Language-Action Model | [BridgeVLA: Input-Output Alignment for Efficient 3D Manipulation Learning with Vision-Language Models](https://arxiv.org/abs/2506.07961) |
| NeurIPS2025 | Vision-Language-Action Model | [BEAST: Efficient Tokenization of B-Splines Encoded Action Sequences for Imitation Learning](https://arxiv.org/abs/2506.06072) |
| NeurIPS2025 | Vision-Language-Action Model | [Real-Time Execution of Action Chunking Flow Policies](https://www.physicalintelligence.company/download/real_time_chunking.pdf) |
| NeurIPS2025 | Data | [EgoBridge: Domain Adaptation for Generalizable Imitation from Egocentric Human Data](https://arxiv.org/abs/2509.19626) |
| NeurIPS2025 | Data | [RobotSmith: Generative Robotic Tool Design for Acquisition of Complex Manipulation Skill](https://arxiv.org/abs/2506.14763) |
| NeurIPS2025 | Data | [URDF-Anything: Constructing Articulated Objects with 3D Multimodal Language Model](https://arxiv.org/abs/2511.00940) |
| NeurIPS2025 | Data | DEAL: Diffusion Evolution Adversarial Learning for Sim-to-Real Transfer |
| NeurIPS2025 | Data | [Generalizable Domain Adaptation for Sim-and-Real Policy Co-Training](https://arxiv.org/abs/2509.18631) |
| NeurIPS2025 | Policy | [FreqPolicy: Efficient Flow-based Visuomotor Policy via Frequency Consistency](https://arxiv.org/abs/2506.08822) |
| NeurIPS2025 | Policy | [Quantization-Free Autoregressive Action Transformer](https://arxiv.org/abs/2503.14259) |
| NeurIPS2025 | Accelerating and Deploying | [Accelerating Visual-Policy Learning through Parallel Differentiable Simulation](https://www.arxiv.org/abs/2505.10646) |
| NeurIPS2025 | Accelerating and Deploying | [EfficientVLA: Training-Free Acceleration and Compression for Vision-Language-Action Models](https://arxiv.org/abs/2506.10100) |
| NeurIPS2025 | Accelerating and Deploying | [A Smooth Sea Never Made a Skilled SAILOR: Robust Imitation via Learning to Search](https://arxiv.org/abs/2506.05294) |
| NeurIPS2025 | Accelerating and Deploying | [VLA-Cache: Efficient Vision-Language-Action Manipulation via Adaptive Token Caching](https://arxiv.org/abs/2502.02175) |
| NeurIPS2025 | Benchmark and Dataset | [RoboCerebra: A Large-scale Benchmark for Long-horizon Robotic Manipulation Evaluation](https://www.arxiv.org/pdf/2506.06677) |
| NeurIPS2025 | Benchmark and Dataset | [SutureBot: A Precision Framework & Benchmark For Autonomous End-to-End Suturing](https://suturebot.github.io/static/SutureBot_NeurIPS_2025.pdf) |
| NeurIPS2025 | Benchmark and Dataset | [LabUtopia: High-Fidelity Simulation and Hierarchical Benchmark for Scientific Embodied Agents](https://arxiv.org/abs/2505.22634) |
| NeurIPS2025 | Benchmark and Dataset | [SonoGym: High Performance Simulation for Challenging Surgical Tasks with Robotic Ultrasound](https://arxiv.org/abs/2507.01152) |
| NeurIPS2025 | Benchmark and Dataset | Embodied Crowd Counting |
| NeurIPS2025 | Benchmark and Dataset | [PAC Bench: Do Foundation Models Understand Prerequisites for Executing Manipulation Policies?](https://arxiv.org/abs/2506.23725) |
| ICCV2025 | Vision-Language-Action Model | [VQ-VLA: Improving Vision-Language-Action Models via Scaling Vector-Quantized Action Tokenizers](https://arxiv.org/abs/2507.01016) |
| ICCV2025 | Accelerating and Deploying | [Saliency-Aware Quantized Imitation Learning for Efficient Robotic Control](https://arxiv.org/abs/2505.15304) |
| ICCV2025 | Accelerating and Deploying | [On-Device Diffusion Transformer Policy for Efficient Robot Manipulation](https://arxiv.org/abs/2508.00697) |
| ICCV2025 | Accelerating and Deploying | [CARP: Coarse-to-Fine Autoregressive Prediction for Visuomotor Policy Learning](https://arxiv.org/abs/2412.06782) |
| ICCV2025 | Benchmark and Dataset | [RoboFactory: Exploring Embodied Agent Collaboration with Compositional Constraints](https://arxiv.org/abs/2503.16408) |
| ICCV2025 | Benchmark and Dataset | [HUMOTO: A 4D Dataset of Mocap Human Object Interactions](https://arxiv.org/abs/2504.10414) |
| ICCV2025 | Benchmark and Dataset | [RoboMM: All-in-One Multimodal Large Model for Robotic Manipulation](https://arxiv.org/abs/2412.07215) |
| ICCV2025 | Benchmark and Dataset | [RoboPearls: Editable Video Simulation for Robot Manipulation](https://arxiv.org/abs/2506.22756) |
| ICCV2025 | Benchmark and Dataset | [DexH2R: A Benchmark for Dynamic Dexterous Grasping in Human-to-Robot Handover](https://arxiv.org/abs/2506.23152) |
| ICCV2025 | Benchmark and Dataset | [Beyond the Destination: A Novel Benchmark for Exploration-Aware Embodied Question Answering](https://arxiv.org/abs/2503.11117) |
| ICCV2025 | Benchmark and Dataset | [RobAVA: A Large-scale Dataset and Baseline Towards Video based Robotic Arm Action Understanding](https://iccv.thecvf.com/virtual/2025/poster/1787) |
| ICCV2025 | Benchmark and Dataset | [RoboAnnotatorX: A Comprehensive and Universal Annotation Framework for Accurate Understanding of Long-horizon Robot Demonstration](https://iccv.thecvf.com/virtual/2025/poster/2215) |
| ICML2025 | Policies | EmbodiedBench: Comprehensive Benchmarking Multi-modal Large Language Models for Vision-Driven Embodied Agents |
| CVPR2025 | Benchmark and Dataset | [RoboTwin: Dual-Arm Robot Benchmark with Generative Digital Twins (early version)](https://arxiv.org/abs/2409.02920) |
| CVPR2025 | Benchmark and Dataset | [Pixel-aligned RGB-NIR Stereo Imaging and Dataset for Robot Vision](https://arxiv.org/abs/2411.18025) |

## 阅读顺序建议

1. 先看 VLN 和 Agentic Planning：确认“大范围规划”和“细粒度规划”分别解决什么。
2. 再看 VLA 和 WAM：区分“直接动作生成”和“先想象/预测再执行”。
3. 最后看本体扩展、轻量化、评测：这些决定路线能不能真实部署。

后续新增论文时，直接放到对应方向表中；如果一篇论文跨多个方向，优先放到它主要解决的问题下面。
