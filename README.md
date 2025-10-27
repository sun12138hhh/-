# 机器人项目展示
本知识库旨在通过汇编我在该领域最杰出的一些项目，来凸显我在机器人技术领域的精湛技艺和专业技能。
以下项目代表了我的个人工作，其中一些项目也涉及合作。如需详细了解个人贡献，请参阅相应的知识库。
这些项目让我得以深入研究机器人技术的各个方面，涵盖纯控制理论和概率算法的应用。

---

# XLerobot — MuJoCo 上的 Sim-to-Real 强化学习（PPO）工程化仓库

**仓库**：`<GitHub 链接 替换这里>`
**年份**：2025
**编程语言**：Python (MuJoCo / ROS2 可选集成)
**其他资源**：报告（`report.pdf`）、幻灯片（`Slides`）、演示视频（`Video`）

---

## 项目概述（Description）

本项目将 **XLerobot** 的控制/任务在 **MuJoCo** 仿真环境中完整工程化：

* 把环境封装为可复现的训练/评估流水线；
* 使用 **PPO**（基于 `stable-baselines3` / `torch`）训练策略；
* 在仿真中使用 **domain / dynamics randomization** 提高鲁棒性；
* 提供一键运行脚本（`run.sh`）、`Dockerfile`、日志与 Demo 视频，便于面试/复现；
* 包含 **sim→real** 的微调/部署说明与实机对比结果。

**目标**：给出一个从训练到部署、可复现、面向工程化的 Sim-to-Real 流程示例，便于在求职面试中展示能力与工程素养。

---

## 主要结果（示例 — 请替换为你自己的量化数据）

| 指标                | 仿真（avg） | 实机（avg） |
| ----------------- | ------: | ------: |
| 成功率 (N=100)       |    0.94 |    0.78 |
| 平均跟踪误差 (m)        |   0.045 |    0.12 |
| 平均 episode 长度 (s) |    15.2 |    14.8 |

---

## 仓库结构

```
XLerobot_mujoco/
├── README.md
├── Dockerfile
├── run.sh
├── requirements.txt
├── configs/
│   └── ppo_xlerobot.yaml
├── envs/
│   └── xlerobot_env.py        # gym 接口封装
├── mujoco_models/
│   └── xlerobot.xml
├── agents/
│   └── ppo_train.py
├── scripts/
│   └── eval.py
│   └── render_rollout.py
├── logs/
├── tensorboard/
├── videos/
├── reports/
│   └── report.pdf
├── slides/
│   └── slides_link_or_file
└── README_assets/
```

---

## 快速开始（Quick Start）

### 1) 本地运行（最小示例）

```bash
# 克隆仓库
git clone <GitHub 链接>
cd XLerobot_mujoco

# 建议先创建虚拟环境
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 一键训练（示例）
bash run.sh train --config configs/ppo_xlerobot.yaml

# 评估 / 渲染 rollout
bash run.sh eval --checkpoint outputs/ppo/latest.pt --video_out videos/rollout.mp4
```

### 2) Docker（推荐，保证环境一致）

```bash
# 构建镜像
docker build -t xlerobot_mujoco:latest .

# 运行训练（挂载 volumes 保留 logs）
docker run --gpus all -v $(pwd)/logs:/workspace/logs -it xlerobot_mujoco:latest bash -c "bash run.sh train --config configs/ppo_xlerobot.yaml"
```

---
## 示例 `run.sh`（模板）

```bash
#!/bin/bash
set -e
MODE=$1
CONFIG=${2:-configs/ppo_xlerobot.yaml}
LOGDIR=logs/$(date +"%Y%m%d_%H%M%S")

mkdir -p $LOGDIR
echo "Log dir: $LOGDIR"

if [ "$MODE" == "train" ]; then
  python agents/ppo_train.py --config $CONFIG 2>&1 | tee $LOGDIR/train.log
elif [ "$MODE" == "eval" ]; then
  CHECKPOINT=${3:-outputs/ppo/latest.pt}
  python scripts/eval.py --checkpoint $CHECKPOINT 2>&1 | tee $LOGDIR/eval.log
else
  echo "Usage: bash run.sh [train|eval] [config]"
fi
```

---

## 示例 `Dockerfile`（简易）

```dockerfile
FROM nvidia/cuda:12.2.0-cudnn8-devel-ubuntu22.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y \
    python3 python3-pip git wget ffmpeg libgl1-mesa-glx && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /workspace
COPY . /workspace
RUN pip3 install -r requirements.txt

CMD ["bash", "run.sh", "train"]
```

---
