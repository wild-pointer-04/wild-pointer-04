<p align="center">
  <img src="assets/header.svg" alt="Heran Lü · 吕鹤冉 — Robotics, Vision and Embodied AI" width="100%">
</p>

<p align="center">
  <b>Robot perception & calibration · Dexterous manipulation · Vision-language planning</b>
</p>

<p align="center">
  <a href="https://wild-pointer-04.github.io/">Academic website / 学术主页 ↗</a>
</p>

Hi, I'm **Heran Lü (吕鹤冉)**. I explore how robots perceive their surroundings, learn from human demonstrations, and turn language into action. My projects connect visual geometry, dexterous manipulation, and robot data collection.

My undergraduate project at **Lanzhou University of Technology** focused on vision-language UAV instruction generation. This profile brings together my project implementations and engineering notes.

我关注机器人感知与标定、灵巧操作和视觉语言任务规划，尝试将学习方法连接到实际的机器人系统。

### Selected work

| Project | What it explores | Tools |
| :--- | :--- | :--- |
| **[AIRBOT × Revo2](https://github.com/wild-pointer-04/airbot-revo-workspace)** | VIVE/PICO arm teleoperation, MANUS hand retargeting, and synchronized image/arm/hand recording in LeRobot episodes. | ROS 2 · gRPC · CAN · LeRobot |
| **[DRO-Grasp → WujiHand](https://github.com/wild-pointer-04/DRO_wujihand)** | WujiHand adaptation, synthetic grasp data, paired point clouds, and configuration-invariant pretraining, built on [D(R,O) Grasp](https://github.com/zhenyuwei2003/DRO-Grasp) by Wei et al. | PyTorch · Point clouds · URDF |
| **[UAV-VLA](https://github.com/wild-pointer-04/UAV-VLA)** | An undergraduate project connecting natural-language instructions and satellite imagery to a UAV mission-planning workflow, with a web interface and mission export. | VLM / LLM · Flask · ArduPilot |
| **[Fisheye & ChArUco](https://github.com/wild-pointer-04/fisheye-camera-calibration-c-improved)** | Corner-point undistortion, standard PnP pose estimation, and reprojection-error analysis. | OpenCV · NumPy · PnP |

Related tools: [Stereo calibration](https://github.com/wild-pointer-04/wanbu_calibration) · [AprilTag camera pose checks](https://github.com/wild-pointer-04/-AprilTag-)

### Engineering notes

- [Configuration-invariant pretraining for WujiHand](https://github.com/wild-pointer-04/DRO_wujihand/blob/main/WujiHand_Stage1_Pretrain_Summary.md) — synthetic data, paired point clouds, and the training pipeline.
- [From teleoperation to a LeRobot episode](https://github.com/wild-pointer-04/airbot-revo-workspace#readme) — the path from arm/hand control to synchronized robot data.
- [Fisheye geometry: undistort points, then solve PnP](https://github.com/wild-pointer-04/fisheye-camera-calibration-c-improved#readme) — pose estimation and reprojection-error analysis.

### In my projects

`Python` · `PyTorch` · `OpenCV` · `ROS 2` · `LeRobot` · `Flask`

<sub>From visual perception to robotic action. / 从视觉感知，走向机器人行动。</sub>
