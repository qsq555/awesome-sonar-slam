# Awesome Sonar SLAM（声呐SLAM精选资源）

**语言：简体中文 | [English](README.md)**

这是一个基于精选水下声呐研究文献整理的论文、数据集与可复用方法索引。重点覆盖**前视成像声呐/多波束前视成像声呐（FLS/MFLS）与IMU、深度信息的水下SLAM**，并纳入机械扫描声呐、多波束测深声呐、侧扫声呐、测深建图和多传感器融合等相关工作。

> **版本：** v0.1 · 2026-09-28  
> **说明：** 本列表依据当前整理的205篇文献形成，属于持续完善的精选目录，并不代表穷尽所有相关研究。总表中的论文名称保留原文，以便检索；传感器信息和方法说明尽量以中文呈现。论文链接使用来源资料中记录的DOI或arXiv地址；没有稳定链接的条目留空。代码和数据链接仅在文献资料明确报告时列出。

## 目录

- [研究范围与分类](#研究范围与分类)
- [论文总表](#论文总表)
- [代码与数据资源](#代码与数据资源)
- [参与维护](#参与维护)

## 研究范围与分类

分类按方法用途划分，同一篇论文可能涉及多个模块。总表将每篇论文列出一次，便于快速筛选。

- **核心FLS/MFLS SLAM系统：** 直接利用前视或多波束前视成像声呐完成定位与建图。
- **声呐-惯性里程计与SLAM前端：** 估计相邻声呐帧间运动，为全局SLAM提供前端约束。
- **三维成像声呐与声学建图：** 重建高程、三维结构、体素地图或神经场景表示。
- **闭环检测与场所识别：** 识别重访区域并改善长程轨迹和地图一致性。
- **机械扫描、多波束、侧扫与测深SLAM：** 收录与FLS任务不同、但可迁移其建图和估计方法的声呐类型。
- **多传感器、协同与主动SLAM：** 涵盖相机、惯性、DVL、深度、多机器人通信和主动探索。
- **学习型声呐前端：** 包括特征对应、高程估计、配准、去噪和神经重建。
- **数据集、仿真器与综述：** 支持方法复现、基准评测和领域入门。

总表中的“传感器”优先列出论文实际使用的传感器类型或型号；“方法 / 作用”概括论文的主要技术路线。传感器型号未报告时保留传感器类别或不填写。

## 论文总表

| 传感器 | 方法 / 作用 | 年份 | 论文 | DOI / 链接 |
|---|---|---:|---|---|
| 前视成像声呐（FLS）； IMU； 深度/DVL | FLS 导航； 成像声呐辅助定位 | 2010 | Imaging Sonar-Aided Navigation for Autonomous Underwater Harbor Surveillance |  |
| 前视成像声呐（FLS）； IMU； 深度/DVL | 声呐 SLAM； 神经进化优化 | 2010 | [Sonar-Based Simultaneous Localization and Mapping Using a Neuro-Evolutionary Optimization](https://doi.org/10.1163/016918610X501435) | 10.1163/016918610X501435 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | FLS位姿图 SLAM | 2018 | Pose-Graph SLAM Using Forward-Looking Sonar |  |
| 前视成像声呐（FLS）； IMU； 深度/DVL | Imaging 声呐； 欠约束路标 | 2018 | Feature-Based SLAM for Imaging Sonar with Under-Constrained Landmarks |  |
| 前视成像声呐（FLS）； IMU； 深度/DVL | FLS； 自适应滤波 / 导航 | 2020 | [2D forward looking SONAR in underwater navigation aiding: An AUKF-based strategy for AUVs](https://doi.org/10.1016/j.ifacol.2020.12.1463) | 10.1016/j.ifacol.2020.12.1463 |
| 前视成像声呐（FLS）； IMU； DVL (RexROV2/UUV-Simulator) | FLS + IMU + DVL； RBPF占据栅格建图 | 2021 | [Underwater SLAM Based on Forward-Looking Sonar](https://doi.org/10.1007/978-981-16-2336-3_55) | 10.1007/978-981-16-2336-3_55 |
| 多波束前视成像声呐（MFLS）； DVL； IMU (RexROV2/BlueROV2) | MFLS 定位与建图 | 2022 | [Underwater Localization and Mapping Based on Multi-Beam Forward Looking Sonar](https://doi.org/10.3389/fnbot.2021.801956) | 10.3389/fnbot.2021.801956 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | Imaging 声呐 keyframes + inertial aiding | 2022 | [Robust inertial-aided underwater localization based on imaging sonar keyframes](https://arxiv.org/abs/2106.16032) | arXiv:2106.16032 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | 占据栅格 FLS SLAM | 2022 | [Occupancy Grid-Based AUV SLAM Method with Forward-Looking Sonar](https://doi.org/10.3390/jmse10081056) | 10.3390/jmse10081056 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | FLS位姿图 用于 深海采矿 | 2023 | [A localization algorithm based on pose graph using Forward-looking sonar for deep-sea mining vehicle](https://doi.org/10.1016/j.oceaneng.2023.114968) | 10.1016/j.oceaneng.2023.114968 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | 结构化水下环境 | 2024 | [Sonar SLAM in structured underwater environments](https://doi.org/10.1109/OCEANS51537.2024.10682261) | 10.1109/OCEANS51537.2024.10682261 |
| Oculus M750d； DVL； IMU； 压力 sensor | 半直接法 声呐-image SLAM | 2024 | [Sonar-Based Simultaneous Localization and Mapping Using the Semi-Direct Method](https://doi.org/10.3390/jmse12122234) | 10.3390/jmse12122234 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | SO-CFAR + ADT特征提取 | 2024 | [AUV SLAM method based on SO-CFAR and ADT feature extraction](https://doi.org/10.1177/00368504241286969) | 10.1177/00368504241286969 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | Multibeam 声呐 graph matching | 2024 | [Graph Matching for Underwater Simultaneous Localization and Mapping Using Multibeam Sonar Imaging](https://doi.org/10.3390/jmse12101859) | 10.3390/jmse12101859 |
| 前视成像声呐（FLS）； IMU； 深度/DVL | 声呐预处理 用于 AUV positioning / SLAM | 2025 | [A Novel Sonar Image Preprocessing Method for AUV Positioning Based on Underwater SLAM](https://doi.org/10.1109/TIM.2025.3595226) | 10.1109/TIM.2025.3595226 |
| 声呐； IMU | 慢采样声呐 + 图优化 | 2015 | [Improving Localization Accuracy for an Underwater Robot With a Slow-Sampling Sonar Through Graph Optimization](https://doi.org/10.1109/JSEN.2015.2432082) | 10.1109/JSEN.2015.2432082 |
| 声呐； IMU | 光束法平差； 声呐-惯性里程计 | 2022 | [Bundle Adjustment-Based Sonar-Inertial Odometry for Underwater Navigation](https://doi.org/10.1109/ROBIO55434.2022.10011721) | 10.1109/ROBIO55434.2022.10011721 |
| 声呐； IMU | 声学-惯性 特征 + 图优化 | 2022 | An Acoustic-Inertial Pose Estimation Method with Robust Feature Match and Graph Optimization |  |
| BlueROV2/M750D 前视成像声呐（FLS）； IMU | 自适应分组 声呐-惯性里程计 | 2024 | [An adaptive grouping sonar-inertial odometry for underwater navigation](https://doi.org/10.1016/j.oceaneng.2024.116688) | 10.1016/j.oceaneng.2024.116688 |
| BlueView P900-130； IMU/DVL (when available) | 直接法成像声呐里程计 | 2024 | [DISO: Direct Imaging Sonar Odometry](https://doi.org/10.1109/ICRA57147.2024.10611064) | 10.1109/ICRA57147.2024.10611064 |
| Water Linked 声呐 3D-15； IMU； 深度传感器 | 鲁棒声呐-惯性-深度里程计 | 2026 | [RA-SIDO: Robust and Adaptive Sonar–Inertial–Depth Odometry for Consistent Underwater Acoustic 3D Mapping](https://doi.org/10.3390/jmse14161520) | 10.3390/jmse14161520 |
| 前视成像声呐（FLS）； IMU (model not reported) | 紧耦合惯性-声呐融合 | 2025 | A Tightly Coupled Inertial-Sonar Fusion for Localization of Underwater Robots |  |
| BlueView M900 前视成像声呐（FLS）； IMU/relative-pose prior | 两阶段直接法FLS里程计 | 2025 | [Direct Forward-Looking Sonar Odometry: A Two-Stage Odometry for Underwater Robot Localization](https://doi.org/10.3390/rs17132166) | 10.3390/rs17132166 |
| 前视成像声呐（FLS） (model not reported) | 点跟踪 imaging-声呐 odometry | 2026 | [ISOPoT: Imaging Sonar Odometry by Point Tracking](https://arxiv.org/abs/2606.23006) | arXiv:2606.23006 |
| 前视成像声呐（FLS）； IMU pose-graph factors | 傅里叶配准 用于 FLS odometry | 2026 | [Deep Learning-Based Fourier Registration for Forward-Looking Sonar Odometry in Texture-Sparse Underwater Environments](https://doi.org/10.1109/LRA.2026.3668623) | 10.1109/LRA.2026.3668623 |
| 声呐； IMU | 图像相似度 acoustic odometry | 2023 | [A Study on Acoustic Odometry Estimation based on the Image Similarity using Forward-looking Sonar](https://doi.org/10.46670/JSST.2023.32.5.313) | 10.46670/JSST.2023.32.5.313 |
| 三维成像声呐； INS/DVL | 声学运动恢复结构 | 2015 | Towards Acoustic Structure from Motion for Imaging Sonar |  |
| 三维成像声呐； INS/DVL | 声学透镜 multibeam 点云 | 2018 | [AUV-Based Underwater 3-D Point Cloud Generation Using Acoustic Lens-Based Multibeam Sonar](https://doi.org/10.1109/JOE.2017.2751139) | 10.1109/JOE.2017.2751139 |
| 三维成像声呐； INS/DVL | 3-D 扫描匹配 | 2022 | [3DupIC: An Underwater Scan Matching Method for Three-Dimensional Sonar Registration](https://doi.org/10.3390/s22103631) | 10.3390/s22103631 |
| 三维成像声呐； INS/DVL | 费马路径 重建 | 2020 | [A Theory of Fermat Paths for 3D Imaging Sonar Reconstruction](https://doi.org/10.1109/IROS45743.2020.9341613) | 10.1109/IROS45743.2020.9341613 |
| 三维成像声呐； INS/DVL | 体积反照率 | 2020 | A Volumetric Albedo Framework for 3D Imaging Sonar Reconstruction |  |
| 三维成像声呐； INS/DVL | 可微 / volumetric 重建 | 2020 | [Fusing concurrent orthogonal wide-aperture sonar images for dense underwater 3D reconstruction](https://arxiv.org/abs/2007.10407) | arXiv:2007.10407 |
| Tritech Gemini 720i； DVL； INS | 空间声学投影 + 神经 TSDF | 2022 | [Spatial Acoustic Projection for 3D Imaging Sonar Reconstruction](https://doi.org/10.1109/ICRA46639.2022.9812277) | 10.1109/ICRA46639.2022.9812277 |
| Two imaging sonars | 双声呐 概率 重建 | 2022 | [Probabilistic 3D Reconstruction Using Two Sonar Devices](https://doi.org/10.3390/s22062094) | 10.3390/s22062094 |
| 三维成像声呐； INS/DVL | 可微 空间雕刻 | 2024 | [Differentiable Space Carving for 3D Reconstruction Using Imaging Sonar](https://doi.org/10.1109/LRA.2024.3469778) | 10.1109/LRA.2024.3469778 |
| 三维成像声呐； INS/DVL | Volumetric 自由空间建图 | 2024 | [Underwater Volumetric Mapping using Imaging Sonar and Free-Space Modeling Approach](https://doi.org/10.1109/ICRA57147.2024.10611082) | 10.1109/ICRA57147.2024.10611082 |
| 前视成像声呐（FLS）； INS/DVL | 神经场 用于 FLS 重建 | 2025 | [NFFLS: Rapid and Accurate Underwater 3-D Reconstruction With Neural Fields for Forward-Looking Sonar](https://doi.org/10.1109/JOE.2025.3590076) | 10.1109/JOE.2025.3590076 |
| 三维成像声呐； INS/DVL | 神经 acoustic 重建 under 位姿漂移 | 2025 | [Acoustic Neural 3D Reconstruction Under Pose Drift](https://doi.org/10.1109/IROS60139.2025.11247485) | 10.1109/IROS60139.2025.11247485 |
| WaterLinked Sonar3D-15； Nortek Nucleus 1000 DVL/AHRS/压力； stereo 相机 for reference | 3-D 声呐 + INS submaps, GICP, TSDF | 2026 | [InsSo3D: Inertial Navigation System and 3D Sonar SLAM for Turbid Environment Inspection](https://arxiv.org/abs/2601.05805) | arXiv:2601.05805 |
| 三维成像声呐； INS/DVL | 神经 隐式表面重建 | 2026 | [Sonar-neus: voxel-based efficient neural implicit surface reconstruction for forward-looking sonar](https://doi.org/10.1016/j.neunet.2026.108664) | 10.1016/j.neunet.2026.108664 |
| 三维成像声呐； INS/DVL | Noise-aware 声呐 高斯泼溅 | 2026 | [NAS-GS: Noise-Aware Sonar Gaussian Splatting](https://doi.org/10.1109/LRA.2026.3706932) | 10.1109/LRA.2026.3706932 |
| 三维成像声呐； INS/DVL | 声呐-guided Gaussian-splatting SLAM | 2026 | [SonarReg-GS SLAM: Sparse Sonar-Guided Depth Regularization for Underwater Gaussian Splatting SLAM](https://doi.org/10.3390/s26154713) | 10.3390/s26154713 |
| 成像声呐/前视成像声呐（FLS） | 声呐-based 特征重定位 | 2013 | [Relocating Underwater Features Autonomously Using Sonar-Based SLAM](https://doi.org/10.1109/JOE.2012.2235664) | 10.1109/JOE.2012.2235664 |
| 成像声呐/前视成像声呐（FLS） | 拓扑式 FLS 场所识别 | 2018 | [Underwater place recognition using forward-looking sonar images: A topological approach](https://doi.org/10.1002/rob.21822) | 10.1002/rob.21822 |
| MSIS | MSIS 闭环 与 PHD 滤波 | 2019 | [Underwater Loop-Closure Detection for Mechanical Scanning Imaging Sonar by Filtering the Similarity Matrix With Probability Hypothesis Density Filter](https://doi.org/10.1109/ACCESS.2019.2952445) | 10.1109/ACCESS.2019.2952445 |
| 测深声呐/MBES | Bathymetric 闭环 invalidation | 2021 | [Efficient Bathymetric SLAM with Invalid Loop Closure Identification](https://doi.org/10.1109/TMECH.2020.3043136) | 10.1109/TMECH.2020.3043136 |
| 测深声呐/MBES | 学习型 bathymetric 闭环 | 2022 | [Data-driven Loop Closure Detection in Bathymetric Point Clouds for Underwater SLAM](https://arxiv.org/abs/2209.08578) | arXiv:2209.08578 |
| 成像声呐/前视成像声呐（FLS） | 俯视图像因子 | 2022 | [Overhead Image Factors for Underwater Sonar-Based SLAM](https://doi.org/10.1109/LRA.2022.3154048) | 10.1109/LRA.2022.3154048 |
| 成像声呐/前视成像声呐（FLS） | 鲁棒 imaging-声呐 场所识别 | 2023 | [Robust Imaging Sonar-based Place Recognition and Localization in Underwater Environments](https://doi.org/10.1109/ICRA48891.2023.10161518) | 10.1109/ICRA48891.2023.10161518 |
| 成像声呐/前视成像声呐（FLS） | 学习型FLS描述子 | 2023 | [Improving Generalization of Synthetically Trained Sonar Image Descriptors for Underwater Place Recognition](https://doi.org/10.1007/978-3-031-44137-0_28) | 10.1007/978-3-031-44137-0_28 |
| 成像声呐/前视成像声呐（FLS） | FLS 基于特征 场所识别 | 2023 | [Feature-Based Place Recognition Using Forward-Looking Sonar](https://doi.org/10.3390/jmse11112198) | 10.3390/jmse11112198 |
| 成像声呐/前视成像声呐（FLS） | 通信受限 协同 闭环 | 2024 | [An efficient loop closure detection method for communication-constrained bathymetric cooperative SLAM](https://doi.org/10.1016/j.oceaneng.2024.117720) | 10.1016/j.oceaneng.2024.117720 |
| 侧扫声呐 | 侧扫 topology matching | 2024 | [Side-Scan Sonar Image Matching Method Based on Topology Representation](https://doi.org/10.3390/jmse12050782) | 10.3390/jmse12050782 |
| 成像声呐/前视成像声呐（FLS） | 多会话 语义场景图 | 2026 | [Multi-Session SLAM for Imaging Sonar Equipped Underwater Vehicles Using Semantic Scene Graphs](https://doi.org/10.1109/LRA.2026.3693583) | 10.1109/LRA.2026.3693583 |
| MSIS/成像声呐 | 机械扫描 imaging 声呐； 概率 扫描匹配 | 2009 | Pose-based SLAM with probabilistic scan matching algorithm using a mechanical scanned imaging sonar |  |
| MSIS/成像声呐 | Ship-hull inspection； 稀疏扩展信息滤波器 | 2008 | SLAM for Ship Hull Inspection using Exactly Sparse Extended Information Filters |  |
| MSIS/成像声呐 | MSIS； Rao–Blackwell化粒子滤波 | 2020 | [RBPF-MSIS: Toward Rao-Blackwellized Particle Filter SLAM for Autonomous Underwater Vehicle With Slow Mechanical Scanning Imaging Sonar](https://doi.org/10.1109/JSYST.2019.2938599) | 10.1109/JSYST.2019.2938599 |
| WASSP 120 kHz MBES； Norbit WBMS 400 kHz； RTK-GPS； AHRS/IMU； DVL； CTD | Bathymetric SLAM dataset与真实值 | 2022 | [A bathymetric mapping and SLAM dataset with high-precision ground truth for marine robotics](https://doi.org/10.1177/02783649211044749) | 10.1177/02783649211044749 |
| 测深声呐/MBES | Active bathymetric exploration | 2023 | [Active Bathymetric SLAM for autonomous underwater exploration](https://doi.org/10.1016/j.apor.2022.103439) | 10.1016/j.apor.2022.103439 |
| 测深声呐/MBES | 协同 bathymetric SLAM | 2022 | [Communication-constrained cooperative bathymetric simultaneous localisation and mapping with efficient loop closures](https://doi.org/10.1017/S0373463321000904) | 10.1017/S0373463321000904 |
| 测深声呐/MBES | 基于特征 bathymetric SLAM | 2024 | [TTT SLAM: A feature-based bathymetric SLAM framework](https://doi.org/10.1016/j.oceaneng.2024.116777) | 10.1016/j.oceaneng.2024.116777 |
| MSIS/成像声呐 | GMM 扫描匹配 用于 profiling 声呐 | 2023 | [Underwater Pose SLAM using GMM scan matching for a mechanical profiling sonar](https://doi.org/10.1002/rob.22272) | 10.1002/rob.22272 |
| Forward-looking acoustic 相机； 2-DoF roll/pitch rotator (no IMU/DVL required) | 声学相机 位姿图与稠密三维建图 | 2021 | [Acoustic Camera-Based Pose Graph SLAM for Dense 3-D Mapping in Underwater Environments](https://doi.org/10.1109/JOE.2020.3033036) | 10.1109/JOE.2020.3033036 |
| 侧扫声呐 | 全自动 侧扫 SLAM | 2024 | [A Fully-automatic Side-scan Sonar SLAM Framework](https://arxiv.org/abs/2304.01854) | arXiv:2304.01854 |
| 测深声呐/MBES | Bathymetric + 距离信息融合 | 2025 | [Robust underwater SLAM fusing bathymetric and range information](https://doi.org/10.1016/j.measurement.2024.116223) | 10.1016/j.measurement.2024.116223 |
| 侧扫声呐 | 侧扫 SLAM in algae-farm monitoring | 2025 | [Side Scan Sonar-based SLAM for Autonomous Algae Farm Monitoring](https://doi.org/10.1109/IROS60139.2025.11246888) | 10.1109/IROS60139.2025.11246888 |
| 侧扫声呐 | Dense subframe 侧扫 SLAM | 2025 | [A Dense Subframe-Based SLAM Framework With Side-Scan Sonar](https://doi.org/10.1109/JOE.2024.3503663) | 10.1109/JOE.2024.3503663 |
| MBES； IMU； DVL； 深度/压力 | 多波束测深声呐 + INS | 2025 | [MINS: Tightly coupled MultiBeam EchoSounder Inertial Navigation System for 3D bathymetric underwater inspection](https://doi.org/10.1016/j.joes.2025.08.010) | 10.1016/j.joes.2025.08.010 |
| 侧扫声呐 | 神经渲染 用于 侧扫 SLAM | 2025 | [NeuRSS: Enhancing AUV Localization and Bathymetric Mapping With Neural Rendering for Sidescan SLAM](https://doi.org/10.1109/JOE.2024.3501317) | 10.1109/JOE.2024.3501317 |
| MSIS/成像声呐 | 高分辨率 imaging-声呐 建图 | 2026 | [High-resolution underwater mapping in low-visibility and confined environments using imaging sonar](https://doi.org/10.1016/j.apor.2026.104959) | 10.1016/j.apor.2026.104959 |
| 声呐； 相机/光学 | Optical + acoustic 位姿图 SLAM | 2024 | [Pose-graph underwater simultaneous localization and mapping for autonomous monitoring and 3D reconstruction by means of optical and acoustic sensors](https://doi.org/10.1002/rob.22375) | 10.1002/rob.22375 |
| 声呐； 相机/光学 | 多会话 光声 factor graph | 2021 | [Multi-session Underwater Pose-graph SLAM using Inter-session Opti-acoustic Two-view Factor](https://doi.org/10.1109/ICRA48506.2021.9561161) | 10.1109/ICRA48506.2021.9561161 |
| 声呐； 相机/光学 | 视觉SLAM 与 acoustic sensing | 2021 | [Robust Underwater Visual SLAM Fusing Acoustic Sensing](https://doi.org/10.1109/ICRA48506.2021.9561537) | 10.1109/ICRA48506.2021.9561537 |
| 声呐； 相机； IMU； 深度/DVL | 声呐, visual, inertial,与depth | 2019 | SVIn2: An Underwater SLAM System Using Sonar, Visual, Inertial, and Depth Sensor |  |
| 声呐； 相机/IMU | Open multi-sensor SVIn2 system | 2022 | [SVIn2: A multi-sensor fusion-based underwater SLAM system](https://doi.org/10.1177/02783649221110259) | 10.1177/02783649221110259 |
| 成像声呐； inter-robot communication | 分布式声学 multi-robot SLAM | 2022 | [DRACo-SLAM: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams](https://doi.org/10.1109/IROS47612.2022.9981822) | 10.1109/IROS47612.2022.9981822 |
| 成像声呐； navigation sensors | 虚拟地图 用于 主动探索 | 2022 | [Virtual Maps for Autonomous Exploration of Cluttered Underwater Environments](https://doi.org/10.1109/JOE.2022.3153897) | 10.1109/JOE.2022.3153897 |
| 声呐； 相机/光学 | 光声 semantic SLAM | 2024 | [Opti-Acoustic Semantic SLAM with Unknown Objects in Underwater Environments](https://doi.org/10.1109/IROS58592.2024.10802819) | 10.1109/IROS58592.2024.10802819 |
| 声呐； 相机； IMU； 深度/DVL | 视觉-惯性-声学 SLAM 与 DVL | 2025 | [VIA-SLAM: An Underwater Visual–Inertial–Acoustic SLAM With Integrated DVL](https://doi.org/10.1109/TIM.2025.3571157) | 10.1109/TIM.2025.3571157 |
| 声呐； 相机/光学 | 声呐 优化 under visual degradation | 2025 | [RUSSO: Robust Underwater SLAM With Sonar Optimization Against Visual Degradation](https://doi.org/10.1109/TMECH.2025.3550730) | 10.1109/TMECH.2025.3550730 |
| 成像声呐； inter-robot communication | 分布式声学 SLAM sequel | 2025 | DRACo-SLAM2: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams with Object Graph Matching |  |
| 声呐； 相机/光学 | Tightly coupled acoustic–visual–inertial calibration | 2025 | [AQUA-SLAM Tightly coupled underwater acoustic-visual-inertial SLAM with sensor calibration](https://doi.org/10.1109/TRO.2025.3554396) | 10.1109/TRO.2025.3554396 |
| Surface/underwater 声呐； multi-robot sensors | 水面-水下异构 multi-robot SLAM | 2026 | [Above and Below: Heterogeneous Multi-Robot SLAM Across Surface and Underwater Domains](https://doi.org/10.1109/LRA.2025.3632613) | 10.1109/LRA.2025.3632613 |
| 前视成像声呐（FLS）/成像声呐 | 伪正视图 高程 estimation | 2021 | [Elevation Angle Estimation in 2D Acoustic Images Using Pseudo Front View](https://doi.org/10.1109/LRA.2021.3058911) | 10.1109/LRA.2021.3058911 |
| 前视成像声呐（FLS）/成像声呐 | 学习型 pseudo-front depth / 多视图立体匹配 | 2022 | [Learning Pseudo Front Depth for 2D Forward-Looking Sonar-based Multi-view Stereo](https://doi.org/10.1109/IROS47612.2022.9982049) | 10.1109/IROS47612.2022.9982049 |
| 成像声呐 | cGAN声呐滤波 用于 占据栅格建图 | 2023 | [Conditional GANs for Sonar Image Filtering with Applications to Underwater Occupancy Mapping](https://doi.org/10.1109/ICRA48891.2023.10160646) | 10.1109/ICRA48891.2023.10160646 |
| 成像声呐 | 自监督 高程与运动退化 | 2023 | [Motion Degeneracy in Self-supervised Learning of Elevation Angle Estimation for 2D Forward-Looking Sonar](https://doi.org/10.1109/IROS55552.2023.10341601) | 10.1109/IROS55552.2023.10341601 |
| 成像声呐 | 位姿监督的声呐特征对应 | 2024 | [SONIC: Sonar Image Correspondence using Pose Supervised Learning for Imaging Sonars](https://doi.org/10.1109/ICRA57147.2024.10611678) | 10.1109/ICRA57147.2024.10611678 |
| 成像声呐 | 全局/局部光流配准 | 2022 | [GPLFR—Global perspective and local flow registration for forward-looking sonar images](https://doi.org/10.1007/s00521-022-07113-8) | 10.1007/s00521-022-07113-8 |
| Acoustic 相机 | 可微 声学相机 pose refinement | 2023 | [Acoustic Camera Pose Refinement Using Differentiable Rendering](https://doi.org/10.1109/SII55687.2023.10039267) | 10.1109/SII55687.2023.10039267 |
| 前视成像声呐（FLS）/成像声呐 | 滚动快门补偿 用于 acoustic lens FLS | 2024 | [Analysis and Compensation of Acoustic Rolling Shutter Effect of Acoustic-Lens-Based Forward-Looking Sonar](https://doi.org/10.1109/JOE.2023.3341466) | 10.1109/JOE.2023.3341466 |
| 前视成像声呐（FLS）/成像声呐 | 声学n点估计 | 2025 | [BESTAnP: Bi-Step Efficient and Statistically Optimal Estimator for Acoustic-n-Point Problem](https://doi.org/10.1109/LRA.2025.3558451) | 10.1109/LRA.2025.3558451 |
| 前视成像声呐（FLS）/成像声呐 | 凸优化全局PnP 用于 2-D FLS | 2025 | [A Convex and Global Solution for the PnP Problem in 2D Forward-Looking Sonar](https://doi.org/10.1109/OCEANS58557.2025.11104528) | 10.1109/OCEANS58557.2025.11104528 |
| 前视成像声呐（FLS）/成像声呐 | 外点剔除 用于 FLS correspondences | 2025 | [Rejecting Outliers in 2D-3D Point Correspondences from 2D Forward-Looking Sonar Observations](https://doi.org/10.1109/IROS60139.2025.11246791) | 10.1109/IROS60139.2025.11246791 |
| 声呐； IMU | 声呐-惯性里程计 与 小波 | 2026 | [DeepWavelet: A Multimodal Wavelet-Based Network for Sonar-Inertial Odometry in Underwater Robots](https://doi.org/10.1109/JOE.2025.3630404) | 10.1109/JOE.2025.3630404 |
| 多波束前视成像声呐（MFLS） | MFLS SLAM | 2020 | [基于多波束声呐的同时定位与地图构建](https://doi.org/10.19838/j.issn.2096-5753.2020.03.013) | 10.19838/j.issn.2096-5753.2020.03.013 |
| 前视成像声呐（FLS）； 相机/IMU | FLS–visual–inertial SLAM thesis | 2023 | 基于前视声呐-视觉-惯性的水下SLAM算法研究 |  |
| 前视成像声呐（FLS）； 相机/IMU | FLS SLAM thesis | 2024 | 基于前视声呐的水下机器人SLAM技术研究 |  |
| 多波束前视成像声呐（MFLS） | MFLS SLAM thesis | 2024 | 基于多波束声呐的水下同步定位与地图构建 |  |
| 声呐； 相机/IMU/深度 | Multi-sensor 水下 SLAM thesis | 2024 | Research on Multi-Sensor Simultaneous Localization and Mapping Method for Underwater Robots |  |
| 声呐 | 水下 SLAM review | 2025 | [水下机器人同步定位与建图关键技术进展与展望](https://doi.org/10.3969/j.issn.1003-2029.2025.03.011) | 10.3969/j.issn.1003-2029.2025.03.011 |
| 前视成像声呐（FLS）； 相机/IMU | FLS 3-D odometry review / method | 2026 | [前视声呐三维视觉里程计技术](https://doi.org/10.12395/0371-0025.2025015) | 10.12395/0371-0025.2025015 |

## 代码与数据资源

以下资源链接由对应论文或数据资料报告。使用前建议查看仓库当前版本、许可协议和数据下载说明。

| 资源 | 链接 |
|---|---|
| OpenSonarDatasets | [github.com/remaro-network/OpenSonarDatasets](https://github.com/remaro-network/OpenSonarDatasets) |
| SONIC对应关系代码与数据 | [github.com/rpl-cmu/sonic](https://github.com/rpl-cmu/sonic) |
| 声呐场所识别 | [github.com/sparolab/sonar_context](https://github.com/sparolab/sonar_context) |
| Bathymetric数据集与解析资源 | [seaward.science/data/pos](https://www.seaward.science/data/pos) |
| DRACo-SLAM | [github.com/jake3991/DRACo-SLAM](https://github.com/jake3991/DRACo-SLAM) |
| Above-and-Below异构SLAM | [github.com/Jake-maritime-lab/Above-and-Below-SLAM](https://github.com/Jake-maritime-lab/Above-and-Below-SLAM/) |
| 多会话成像声呐SLAM | [github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar](https://github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar) |
| RUSSO | [github.com/CLASS-Lab/RUSSO](https://github.com/CLASS-Lab/RUSSO) |
| SVIn2 | [github.com/sharminrahman/SVIn2](https://github.com/sharminrahman/SVIn2) |
| SonarGraph | [github.com/matheusbg8/SonarGraph](https://github.com/matheusbg8/SonarGraph) |
| BESTAnP | [github.com/LIAS-CUHKSZ/BESTAnP](https://github.com/LIAS-CUHKSZ/BESTAnP) |
| Bathymetric闭环学习 | [github.com/tjr16/bathy_nn_learning](https://github.com/tjr16/bathy_nn_learning) |
| 侧扫声呐SLAM | [github.com/julRusVal/sss_farm_slam](https://github.com/julRusVal/sss_farm_slam) |
| 声学相机仿真器 | [github.com/sollynoay](https://github.com/sollynoay) |
| A2FNet | [github.com/sollynoay/A2FNet](https://github.com/sollynoay/A2FNet) |
| EPSSN | [github.com/sollynoay/EPSSN](https://github.com/sollynoay/EPSSN) |
| Blender声呐仿真器 | [github.com/sollynoay/Sonar-simulator-blender](https://github.com/sollynoay/Sonar-simulator-blender) |
| DISO | [github.com/SenseRoboticsLab/DISO](https://github.com/SenseRoboticsLab/DISO) |
| AQUA-SLAM | [github.com/SenseRoboticsLab/AQUA-SLAM](https://github.com/SenseRoboticsLab/AQUA-SLAM) |
| 侧扫声呐SLAM框架 | [github.com/halajun/diasss](https://github.com/halajun/diasss) |
| 稠密子帧侧扫SLAM | [github.com/halajun/acoustic_slam](https://github.com/halajun/acoustic_slam) |
| 侧扫声呐数据集 | [github.com/YDY-andy/Sonar-dataset](https://github.com/YDY-andy/Sonar-dataset) |
| AUV导航数据集 | [github.com/nature1949/AUV_navigation_dataset](https://github.com/nature1949/AUV_navigation_dataset) |

## 参与维护

- 新增论文前请核实论文名称、年份、传感器配置和DOI/持久链接。
- 代码与数据链接应与论文引用分开记录；论文提到“未来开放”不等于仓库已经公开。
- 优先将论文放入最具体的功能分类；只有在其提供了不同的可复用模块时，才在多个分类中重复列出。
- 欢迎提交遗漏论文、分类修订和失效链接的更正。


