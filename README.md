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
