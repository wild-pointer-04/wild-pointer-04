<p align="center"><img src="assets/header.svg" alt="吕鹤冉 / Heran Lü · 中南大学硕士研究生 · 导师戴训华博士" width="100%"></p>

<p align="center"><a href="https://wild-pointer-04.github.io/">学术主页 / Academic Homepage</a> · <a href="https://faculty.csu.edu.cn/daixunhua/zh_CN/index.htm">导师 / Advisor</a> · <b>ENTP</b></p>

## 关于我 / About Me

我叫 **吕鹤冉（Heran Lü）**，目前是 **[中南大学](https://www.csu.edu.cn/)** 的硕士研究生，导师是 **[戴训华博士](https://faculty.csu.edu.cn/daixunhua/zh_CN/index.htm)**。

我的研究兴趣集中在 **多智能体强化学习、策略复用与具身智能**，关注智能体如何在团队规模、环境和任务变化时复用已有技能，并通过感知、学习与控制的协同完成决策和操作。研究与工程实践围绕以下方向展开：

- **多智能体学习与协同决策**：集合观测编码、共享策略、分层决策与课程训练。
- **灵巧操作与抓取表征**：真实物体点云、Robot–Object 几何表征与触觉稳定性评估。
- **机器人示教与系统实践**：臂手遥操、多模态示教采集和视觉闭环控制。

I am a master’s student at **Central South University**, advised by **Dr. Xunhua Dai**. My research focuses on multi-agent reinforcement learning, reusable policies, and embodied intelligence.

## 教育经历 / Education

- **中南大学（Central South University）** · 2026—2029（预计毕业）
  电子信息，硕士研究生，在读；导师：[戴训华博士](https://faculty.csu.edu.cn/daixunhua/zh_CN/index.htm)。
- **兰州理工大学（Lanzhou University of Technology）** · 2022—2026
  软件工程，本科；专业排名：**1/215**。

## 研究经历 / Research Experience

- **2026.06—2026.09**：臂手协同遥操作与多模态示教采集，负责系统方案、动作重定向、末端控制与数据管线。
- **2025.11—2026.06**：实物点云驱动的灵巧抓取，开展 WujiHand 适配、实物感知、抓取学习与触觉仿真评估。

## 研究项目 / Research Projects

### 1. RF｜面向可变团队规模的多无人机分层强化学习与策略复用

<p><img src="assets/rf.svg" alt="RF｜面向可变团队规模的多无人机分层强化学习与策略复用：方法与系统架构示意" width="520"></p>

**个人研究项目 · 策略架构与训练评估**

面向障碍环境中的多无人机导航与协同对抗，研究团队规模变化、成员失效和任务切换条件下的共享策略学习、基础技能复用与分阶段迁移。

- **分层策略：**高层任务指挥—中层策略融合—底层飞行控制；策略生成三轴速度，动力学模型与串级 PID 执行。
- **规模适配：**CNN 地形编码与 MaskedSetEncoder 融合实体状态，通过掩码、均值/最大池化与参数共享，在既定观测容量内适配团队人数变化。
- **技能复用：**Softmax 动作融合与 Residual Policy 联合适配；PPO 课程训练后冻结 7 个基础原语与地形编码，更新融合、残差及价值网络。

**结果与实现：**固定仿真回归集：240 个已知场景。初始策略 → V2：185/240（77.08%）→ 225/240（93.75%），提升 16.67 个百分点。

<details><summary>技术细节与版本说明</summary>

版本演进：初始策略 → V1（地形与避障课程、全网络适配）→ V2（基础模块冻结、多机共享策略训练）。V2 训练场景配比为 25% 基础导航、15% 多机相遇、60% 对抗；评估流程检查冻结参数、缓冲区与 checkpoint 来源。

</details>

[私有仓库 / Private repository](https://github.com/wild-pointer-04/RF-LSTM) · [学术主页中的项目详情](https://wild-pointer-04.github.io/#rf)

<sub>PyTorch · PPO · Masked Set Encoding · Policy Sharing · Skill Reuse</sub>

---

### 2. 臂手协同遥操作与多模态示教采集

<p><img src="assets/teleop.svg" alt="臂手协同遥操作与多模态示教采集：方法与系统架构示意" width="520"></p>

**2026.06—2026.09 · 系统方案与核心模块开发**

面向机器人遥操与示教，构建 AIRBOT 机械臂、Revo2 灵巧手与 MANUS 数据手套协同系统，贯通设备输入、动作重定向、末端控制与数据采集。

- **统一控制管线：**将 PICO 与 SteamVR/OpenVR 双 Tracker 输入转换为统一位姿协议，复用 TeleopPipeline；结合 Clutch、EMA、SLERP 与工作空间约束生成末端目标。
- **手部重定向：**人体关节语义映射生成 Revo2 六维动作；四指加权屈曲、拇指屈曲/外展分通道，并集成向量映射与 DLS 拇指 IK 可选后端。
- **多模态示教：**ROS 2/rosbridge + LeRobot 组织 RGB、臂关节/末端、手部状态与五指触觉；单调时钟和异步缓存支持帧校验、脚踏门控、Episode 切分与续采。

**结果与实现：**实现 PICO/VIVE 双输入适配、Revo2 六维动作重定向与多模态 Episode 采集，形成可复用的臂手协同工程原型。

<details><summary>技术细节与版本说明</summary>

从 PICO + MANUS 双链路原型迭代到 VIVE 输入适配、统一控制管线与 LeRobot 采集。完成坐标基变换、身体相对位姿映射、安装外参与真机跟随调试，并接入五指法向力到 MANUS 振动反馈的映射。

</details>

[代码 / Code](https://github.com/wild-pointer-04/airbot-revo-workspace) · [学术主页中的项目详情](https://wild-pointer-04.github.io/#teleop)

<sub>Python · ROS 2 · OpenVR · Hand Retargeting · DLS IK · LeRobot</sub>

---

### 3. 实物点云驱动的 WujiHand 跨本体抓取与触觉评估

<p><img src="assets/grasp.svg" alt="实物点云驱动的 WujiHand 跨本体抓取与触觉评估：方法与系统架构示意" width="520"></p>

**2025.11—2026.06 · 感知、抓取学习与仿真**

基于 D(R,O) Grasp 距离场表征框架，连接真实物体点云提取、Robot–Object 双边网络、WujiHand 姿态恢复与触觉稳定性评估。

- **抓取表征与求解：**DGCNN 提取手部/物体点云特征，Cross-attention 建立几何关联，CVAE 建模多模态抓取；经 Multilateration、SE(3) 恢复与可微 IK 求解 WujiHand 姿态。
- **实物点云管线：**RealSense + ROS 2 + SAM2 完成采集与目标分割，结合 Colored ICP/TSDF、RGB-D VO、DBSCAN 与 RANSAC 组织配准、重建及点云清理。
- **仿真与触觉评估：**在 Isaac Gym 中完成 URDF、IK 对齐与 PD 抓取控制；构建五指 Taxel 阵列、CAE 触觉编码和双特征表征，用于抓取稳定性判断。

**结果与实现：**形成“实物点云 → 跨本体抓取姿态 → 仿真执行 → 触觉稳定性评估”的研究链路。

<details><summary>技术细节与版本说明</summary>

WujiHand 抓取配置包含 6 维全局位姿与 20 个手指关节，共 26 个配置自由度。补充构型不变性预训练、合成抓取数据与配对点云数据集，连接模型训练、抓取执行和仿真验证。

基于 [D(R,O) Grasp（Wei et al.）](https://github.com/zhenyuwei2003/DRO-Grasp)；这里展示 WujiHand 适配与系统集成，原论文归属原作者。

</details>

[代码 / Code](https://github.com/wild-pointer-04/DRO_wujihand) · [学术主页中的项目详情](https://wild-pointer-04.github.io/#grasp)

<sub>PyTorch · DGCNN · Cross-attention · CVAE · Open3D · Isaac Gym</sub>

---

### 4. SEBOT T710｜自主导航与视觉闭环操作

<p><img src="assets/sebot.svg" alt="SEBOT T710｜自主导航与视觉闭环操作：方法与系统架构示意" width="520"></p>

**机器人竞赛项目 · 感知、规划与控制**

面向竞赛与餐饮服务场景，将端侧目标检测、激光建图、定位导航、视觉伺服抓取与任务状态机整合到 T710 机器人平台。

- **端侧视觉：**PaddleDetection/YOLO 与 PPNC/NPU 推理，结合 ONNX Runtime 后处理及 NMS，将检测结果输入导航与抓取任务。
- **导航与任务编排：**SLAM、AMCL/EKF、代价地图与全局/局部规划贯通移动导航；服务状态机衔接点餐、取放、送餐及结算。
- **视觉闭环操作：**通过视觉偏差与雷达距离反馈，协调底盘接近、目标对准、PID 调节和 Talon 机械臂动作；配套 Qt/RViz 与 STDR 联调。

**结果与实现：**贯通“目标检测 → 建图定位 → 导航到达 → 视觉抓取 → 服务执行”的系统链路。

<details><summary>技术细节与版本说明</summary>

公开基础版本为 ROS1/catkin，默认 Dijkstra + DWA，并包含 A*。项目扩展包括 YOLO 训练/剪枝、Docker 部署，以及 ROS2 下改进 A* + TEB 与强化学习抓取；扩展实现范围见仓库说明。

</details>

[代码 / Code](https://github.com/wild-pointer-04/sebot-t710-competition) · [学术主页中的项目详情](https://wild-pointer-04.github.io/#sebot) · [公开实现范围](https://github.com/wild-pointer-04/sebot-t710-competition/blob/main/docs/IMPLEMENTATION_STATUS.md)

<sub>C++ · ROS · YOLO · SLAM · Visual Servoing · OpenCV</sub>


---

<sub>Research in multi-agent learning, dexterous manipulation, and embodied intelligence.</sub>
