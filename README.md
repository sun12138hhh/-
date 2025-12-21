# Hi there, I'm 孙浩翔 👋

> **M.S. in Mechanical Engineering @ 浙江大学 | B.S. in Physics** > 🤖 **Focus:** Embodied AI, Sim-to-Real, Robot Learning & Motion Planning.

欢迎来到我的机器人项目集。这里汇集了我对 **具身智能（Embodied AI）** 和 **经典机器人控制** 的探索。我致力于结合**物理学的第一性原理**直觉与**深度强化学习**的范式，解决机器人从仿真到现实（Sim2Real）的落地难题。

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-EE4C2C?logo=pytorch)
![ROS2](https://img.shields.io/badge/ROS2-Humble-22314E?logo=ros)
![MuJoCo](https://img.shields.io/badge/Simulator-MuJoCo-orange)
![Isaac Gym](https://img.shields.io/badge/Simulator-Isaac%20Gym-green)

---

## 🚀 Featured Projects | 精选项目

### 1. XLerobot: MuJoCo 仿真与 Sim-to-Real 全栈强化学习框架
**关键词**: `Reinforcement Learning (PPO)` `Sim2Real` `MuJoCo` `Domain Randomization` `Engineering`

> **项目概述**:  
> 这是一个面向工程落地的具身智能项目。针对 **XLerobot** 双臂机器人，构建了从 MuJoCo 仿真训练到真机部署的完整闭环。重点解决了仿真与现实的动力学鸿沟（Dynamics Gap），并实现了训练流水线的标准化。



https://github.com/user-attachments/assets/04f9cae8-80fa-438e-a01e-f52a30c4c278



https://github.com/user-attachments/assets/beb5fbb2-7e38-44a0-831d-e9566df54222



**✨ 核心工作 (Key Contributions):**
* **工程化流水线**: 将环境封装为 Gym 接口，构建了可复现的 Training/Evaluation Pipeline。
* **策略训练**: 基于 `stable-baselines3` 和 `PyTorch` 实现 **PPO** 算法，完成复杂操作任务的策略学习。
* **Sim-to-Real**: 在仿真中引入 **Domain Randomization** (摩擦力、质量、延迟等) 以提高策略的鲁棒性，成功迁移至真机。
* **DevOps**: 提供 `Dockerfile` 和一键运行脚本 (`run.sh`)，确保开发环境的一致性。

🔗 **资源**: [代码仓库](#) | [技术报告 (PDF)](#) | [演示视频](#)

---

### 2. Autonomous Navigation: A* 路径规划与最小加加速度轨迹优化
**关键词**: `Motion Planning` `A* Algorithm` `Trajectory Smoothing` `Minimum Jerk` `ROS`

> **项目概述**:  
> 基于 ROS 的移动机器人导航系统。在经典 A* 搜索的基础上，结合物理约束（动力学）进行了后端轨迹优化，实现了在复杂障碍物环境下的平滑避障。



https://github.com/user-attachments/assets/9e20aeb9-ac9a-467e-a40d-be3237b12ef5



**✨ 核心功能 (Key Features):**
* **🎯 前端搜索**: 实现 **A*** 算法，并通过启发式函数优化（Heuristic Optimization）提升在随机障碍物环境下的搜索效率。
* **🌊 后端平滑**: 采用 **5次多项式 (Quintic Polynomial)** 进行轨迹插值，解析求解 **Minimum Jerk**（最小加加速度）轨迹，确保速度与加速度连续。
* **📊 可视化交互**: 集成 RViz 实时可视化，动态展示搜索过程（Open/Closed Set）与优化后的平滑轨迹。

🔗 **资源**: [代码仓库](#) | [演示视频](#)

---

## 📝 Other Explorations

* **Diffusion Policy 复现**: 基于 `Diffusers` 复现 Vision-Language-Action 控制策略。[链接](#)
* **LeetCode 算法笔记**: 记录数据结构与算法的刷题心得。[链接](#)

---

<div align="center">
  <p>Looking for <b>Embodied AI Algorithm Intern</b> opportunities.</p>
  <p>📫 Contact: <a href="mailto:your_email@example.com">your_email@example.com</a></p>
</div>





















## 🚀 Featured Projects | 精选项目

### 📚 Theoretical Algorithms | 理论与算法验证
> *关注经典算法的数学原理复现与特定场景下的优化。*

#### 1. Autonomous Navigation: A* 路径规划与最小加加速度轨迹优化
**关键词**: `Motion Planning` `A* Algorithm` `Trajectory Smoothing` `Minimum Jerk` `ROS`

> **项目概述**:  
> 基于 ROS 的移动机器人导航系统。在经典 A* 搜索的基础上，结合物理约束（动力学）进行了后端轨迹优化，实现了在复杂障碍物环境下的平滑避障。

[[这里放你的 A.mp4 或者转成的 GIF]](https://github.com/user-attachments/assets/9e20aeb9-ac9a-467e-a40d-be3237b12ef5)

**✨ 核心功能 (Key Features):**
* **🎯 前端搜索**: 实现 **A*** 算法，并通过启发式函数优化（Heuristic Optimization）提升在随机障碍物环境下的搜索效率。
* **🌊 后端平滑**: 采用 **5次多项式 (Quintic Polynomial)** 进行轨迹插值，解析求解 **Minimum Jerk**（最小加加速度）轨迹，确保速度与加速度连续。
* **📊 可视化交互**: 集成 RViz 实时可视化，动态展示搜索过程（Open/Closed Set）与优化后的平滑轨迹。

🔗 **资源**: [代码仓库](#) | [演示视频](#)

---

#### 2. PCB Defect Detection: 基于 Faster R-CNN 的缺陷检测系统
**关键词**: `Computer Vision` `Faster R-CNN` `ResNet-50 FPN` `WandB` `GUI Deployment`

> **项目概述**:  
> 针对工业场景下的 PCB 缺陷检测，对比实现了两套 **Faster R-CNN** 方案：基于 torchvision 的工程化实现与基于底层网络构建的完整复现。项目集成 MLOps 工具流与桌面端部署应用。



https://github.com/user-attachments/assets/42b8d4cf-3f77-40a1-8128-08f4421a53b0


**✨ 核心功能 (Key Features):**
* **🔍 双重架构对比**: 
    * **自研方案**: 基于 `torchvision` 预训练模型，集成 **WandB** 进行贝叶斯超参搜索（Bayesian Sweep），优化 ResNet-50 + FPN 的特征提取能力。
    * **底层复现**: 从零构建 RPN (Region Proposal Network) 与 RoI Heads，深入理解 Anchor 生成与 NMS 筛选机制。
* **⚙️ 完整工程流**: 实现 VOC 格式数据流水线，支持 Mosaic/Mixup 等数据增强策略。
* **🖥️ 部署与交互**: 开发 **Tkinter/PyQt5** 双版本 GUI，支持单图推理与视频流实时检测，实现工业级交互体验。

🔗 **资源**: [代码仓库](#) | [技术文档](#)

---

### 🤖 Embodied AI Practice | 具身智能工程实践
> *聚焦 SOTA 具身策略（ACT, Diffusion Policy）的复现与 Sim2Real 落地。*

#### 3. LeRobot Implementation: ACT 与 Diffusion Policy 的实机部署
**关键词**: `Imitation Learning` `ACT` `Diffusion Policy` `HuggingFace LeRobot` `Sim2Real`

> **项目概述**:  
> 基于 HuggingFace **LeRobot** 框架，在双臂机器人平台上复现并部署了 **ACT (Action Chunking Transformer)** 与 **Diffusion Policy** 算法。打通了从数据采集、策略训练到真机推理的全栈流程。

[这里放真机抓取的 GIF/视频]

**✨ 核心工作 (Key Contributions):**
* **策略复现**: 深入研究 Transformer 动作分块预测与去噪扩散过程，成功在低数据量下训练出高鲁棒性策略。
* **VLA 对齐**: 处理多模态数据输入（RGB 图像 + 关节状态），实现视觉特征与动作空间的对齐编码。
* **真机适配**: 解决推理延迟与控制频率同步问题，成功完成双臂协同物体操作任务。

🔗 **资源**: [代码仓库](#) | [演示视频](#)

---

#### 4. Isaac Sim Teleoperation: 高保真仿真与遥操作数据管线
**关键词**: `NVIDIA Isaac Sim` `Teleoperation` `Data Collection` `Digital Twin` `USD`

> **项目概述**:  
> 构建基于 **NVIDIA Isaac Sim** 的高保真仿真环境，用于具身智能策略的低成本训练与验证。搭建了基于 VR/手柄 的遥操作（Teleoperation）数据采集管线，为 LeRobot 提供高质量合成数据。

[这里放 Isaac Sim 里的仿真录屏 GIF]

**✨ 核心工作 (Key Contributions):**
* **数字孪生构建**: 导入机器人的 URDF/MJCF 模型，配置物理属性（碰撞体、关节阻尼）以对齐真实物理世界。
* **遥操作映射**: 实现 VR 手柄/SpaceMouse 到机械臂末端执行器（End-effector）的 IK 逆运动学映射，实现流畅的示教数据录制。
* **Sim-to-Sim 验证**: 在仿真环境中直接验证 LeRobot 训练出的策略模型，大幅降低真机试错成本。

🔗 **资源**: [代码仓库](#) | [演示视频](#)

---

## 📝 Other Explorations

* **LeetCode 算法笔记**: 记录数据结构与算法的刷题心得。[链接](#)
* **CS 基础**: 操作系统与计算机网络学习记录。[链接](#)

---

<div align="center">
  <p>Looking for <b>Embodied AI Algorithm Intern</b> opportunities.</p>
  <p>📫 Contact: <a href="mailto:your_email@example.com">your_email@example.com</a></p>
</div>
