# Awesome Sonar SLAM（声呐SLAM精选资源）

**基于声呐的水下SLAM系统及可直接复用SLAM组件的精选列表。**

**语言：简体中文 | [English](README.md)**

本公开索引专注于SLAM方法，而不是复现完整调研语料库。收录内容包括完整SLAM系统，以及明确标注、能够直接服务于声呐SLAM流程的里程计、配准、闭环或SLAM因子方法。单纯的图像增强、目标检测、三维重建、数据集和综述论文暂不属于当前范围。

条目依据方法使用的声呐测量几何进行分类，并按年份从早到晚排列。论文题名和期刊/会议名称保留来源语言。没有正式方法名称时使用“—”，论文未报告具体硬件时标记为“未报告”。GitHub链接只在作者或项目仓库得到核实时列出；Star徽章动态更新，可能存在短暂缓存。

## 目录

- [声呐分类](#声呐分类)
- [前视成像声呐（FLS）](#前视成像声呐fls)
- [机械扫描成像声呐（MSIS）](#机械扫描成像声呐msis)
- [3D声呐](#3d声呐)
- [侧扫声呐（SSS）](#侧扫声呐sss)
- [多波束测深声呐（MBES）](#多波束测深声呐mbes)
- [缩写](#缩写)
- [参与维护](#参与维护)

## 声呐分类

本索引依据主要测量几何和SLAM用途采用五类工程分类：

- **FLS：** 前视二维距离—方位成像声呐，通常采用电子多波束成像。“MFLS”不作为独立类别。
- **MSIS：** 通过机械扫描随时间形成完整扫描图的成像或剖面声呐。
- **3D声呐：** 能直接分辨高程并输出三维点或距离—方位—高程测量的声呐。
- **SSS：** 随载体运动形成侧向条带图像的侧扫声呐。
- **MBES：** 主要朝下方或斜下方探测，用于生成测深条带和海底地形图的多波束测深声呐。

“多波束”在本索引中属于波束形成属性，不单独构成声呐类别。论文原题不会被改写，因此题名中仍可能出现“multi-beam forward-looking sonar”。

## 前视成像声呐（FLS）

| 年份 | 方法 / 系统 | 声呐类别 | 声呐型号 | 其他传感器 | 论文 | 期刊 / 会议 | 论文链接 / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|---|
| 2008 | ESEIF SLAM | FLS | Sound Metrics DIDSON | IMU, DVL, 深度计 | SLAM for Ship Hull Inspection using Exactly Sparse Extended Information Filters | IEEE International Conference on Robotics and Automation (ICRA) | — | — | — |
| 2015 | — | FLS | Sound Metrics DIDSON | DVL, IMU | Bundle Adjustment from Sonar Images and SLAM Application for Seafloor Mapping | MTS/IEEE OCEANS | — | — | — |
| 2015 | ASFM | FLS | Sound Metrics DIDSON | DVL, IMU | Towards Acoustic Structure from Motion for Imaging Sonar | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | — | — | — |
| 2018 | Pose-Graph SLAM | FLS | Sound Metrics DIDSON | DVL, IMU | Pose-Graph SLAM Using Forward-Looking Sonar | IEEE Robotics and Automation Letters | — | — | — |
| 2018 | — | FLS | Sound Metrics DIDSON | DVL, IMU | Feature-Based SLAM for Imaging Sonar with Under-Constrained Landmarks | IEEE International Conference on Robotics and Automation (ICRA) | — | — | — |
| 2020 | — | FLS | Sound Metrics DIDSON | DVL, IMU, 深度计 | Degeneracy-Aware Imaging Sonar Simultaneous Localization and Mapping | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2019.2937946](https://doi.org/10.1109/JOE.2019.2937946) | — | — |
| 2020 | — （定位） | FLS | 未报告 | IMU, 深度计 | Keyframe-Based Imaging Sonar Localization and Navigation using Elastic Windowed Optimization | Global OCEANS 2020 | [10.1109/IEEECONF38699.2020.9389045](https://doi.org/10.1109/IEEECONF38699.2020.9389045) | — | — |
| 2020 | — | FLS | 未报告 | 未报告 | 基于多波束声呐的同时定位与地图构建 | Digital Ocean & Underwater Warfare | [10.19838/j.issn.2096-5753.2020.03.013](https://doi.org/10.19838/j.issn.2096-5753.2020.03.013) | — | — |
| 2021 | — | FLS / 声学相机 | 未报告 | 2-DoF 旋转机构 | Acoustic Camera-Based Pose Graph SLAM for Dense 3-D Mapping in Underwater Environments | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2020.3033036](https://doi.org/10.1109/JOE.2020.3033036) | — | — |
| 2021 | RBPF-SLAM | FLS | 仿真FLS (RexROV2) | IMU, DVL | Underwater SLAM Based on Forward-Looking Sonar | Communications in Computer and Information Science | [10.1007/978-981-16-2336-3_55](https://doi.org/10.1007/978-981-16-2336-3_55) | — | — |
| 2022 | RBPF-SLAM | FLS | 未报告 | IMU, DVL | Underwater Localization and Mapping Based on Multi-Beam Forward Looking Sonar | Frontiers in Neurorobotics | [10.3389/fnbot.2021.801956](https://doi.org/10.3389/fnbot.2021.801956) | — | — |
| 2022 | — （里程计） | FLS | 未报告 | IMU | Bundle Adjustment-Based Sonar-Inertial Odometry for Underwater Navigation | IEEE International Conference on Robotics and Biomimetics (ROBIO) | [10.1109/ROBIO55434.2022.10011721](https://doi.org/10.1109/ROBIO55434.2022.10011721) | — | — |
| 2022 | DRACo-SLAM | FLS | Oculus M750d | DVL, IMU, 深度计 | DRACo-SLAM: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | [10.1109/IROS47612.2022.9981822](https://doi.org/10.1109/IROS47612.2022.9981822) | [DRACo-SLAM](https://github.com/jake3991/DRACo-SLAM) | [![Stars](https://img.shields.io/github/stars/jake3991/DRACo-SLAM?style=flat-square&label=stars)](https://github.com/jake3991/DRACo-SLAM) |
| 2022 | — （SLAM因子） | FLS | 未报告 | DVL, IMU, 俯视RGB图像 | Overhead Image Factors for Underwater Sonar-Based SLAM | IEEE Robotics and Automation Letters | [10.1109/LRA.2022.3154048](https://doi.org/10.1109/LRA.2022.3154048) | — | — |
| 2022 | — | FLS | 未报告 | IMU, DVL, 深度计 | Occupancy Grid-Based AUV SLAM Method with Forward-Looking Sonar | Journal of Marine Science and Engineering | [10.3390/jmse10081056](https://doi.org/10.3390/jmse10081056) | — | — |
| 2022 | — （定位） | FLS | 未报告 | IMU, 深度计 | Robust inertial-aided underwater localization based on imaging sonar keyframes | arXiv | [arXiv](https://arxiv.org/abs/2106.16032) | — | — |
| 2022 | Virtual Maps （主动SLAM） | FLS | 未报告 | 导航传感器 | Virtual Maps for Autonomous Exploration of Cluttered Underwater Environments | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2022.3153897](https://doi.org/10.1109/JOE.2022.3153897) | — | — |
| 2023 | — （定位） | FLS | Kongsberg M3 | DVL, IMU, 深度计 | A localization algorithm based on pose graph using Forward-looking sonar for deep-sea mining vehicle | Ocean Engineering | [10.1016/j.oceaneng.2023.114968](https://doi.org/10.1016/j.oceaneng.2023.114968) | — | — |
| 2023 | — （里程计） | FLS | Sound Metrics DIDSON | DVL, MEMS gyro, 压力计 | A Study on Acoustic Odometry Estimation based on the Image Similarity using Forward-looking Sonar | Journal of Sensor Science and Technology | [10.46670/JSST.2023.32.5.313](https://doi.org/10.46670/JSST.2023.32.5.313) | — | — |
| 2024 | — （里程计） | FLS | Oculus M750d | IMU | An adaptive grouping sonar-inertial odometry for underwater navigation | Ocean Engineering | [10.1016/j.oceaneng.2024.116688](https://doi.org/10.1016/j.oceaneng.2024.116688) | — | — |
| 2024 | — | FLS | Oculus M750d | DVL, IMU, 压力计 | Sonar-Based Simultaneous Localization and Mapping Using the Semi-Direct Method | Journal of Marine Science and Engineering | [10.3390/jmse12122234](https://doi.org/10.3390/jmse12122234) | — | — |
| 2024 | — | FLS | 未报告 | DVL, IMU | Sonar SLAM in structured underwater environments | OCEANS 2024 - Singapore | [10.1109/OCEANS51537.2024.10682261](https://doi.org/10.1109/OCEANS51537.2024.10682261) | — | — |
| 2024 | — | FLS | 未报告 | DVL, IMU, 深度计 | AUV SLAM method based on SO-CFAR and ADT feature extraction | Science Progress | [10.1177/00368504241286969](https://doi.org/10.1177/00368504241286969) | — | — |
| 2024 | DISO （里程计） | FLS | BlueView P900-130 | DVL, IMU | DISO: Direct Imaging Sonar Odometry | IEEE International Conference on Robotics and Automation (ICRA) | [10.1109/ICRA57147.2024.10611064](https://doi.org/10.1109/ICRA57147.2024.10611064) | [DISO](https://github.com/SenseRoboticsLab/DISO) | [![Stars](https://img.shields.io/github/stars/SenseRoboticsLab/DISO?style=flat-square&label=stars)](https://github.com/SenseRoboticsLab/DISO) |
| 2024 | GM SLAM | FLS | Oculus M1200d | DVL, IMU, 深度计 | Graph Matching for Underwater Simultaneous Localization and Mapping Using Multibeam Sonar Imaging | Journal of Marine Science and Engineering | [10.3390/jmse12101859](https://doi.org/10.3390/jmse12101859) | — | — |
| 2024 | Opti-Acoustic Semantic SLAM | FLS | Oculus M1200d / M750d | 相机, DVL, IMU, 压力计 | Opti-Acoustic Semantic SLAM with Unknown Objects in Underwater Environments | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | [10.1109/IROS58592.2024.10802819](https://doi.org/10.1109/IROS58592.2024.10802819) | — | — |
| 2025 | SIO-UV （里程计） | FLS | BlueView M900 | IMU | SIO-UV: Rapid and Robust Sonar Inertial Odometry for Underwater Vehicles | IEEE Transactions on Industrial Electronics | [10.1109/TIE.2025.3561817](https://doi.org/10.1109/TIE.2025.3561817) | — | — |
| 2025 | DRACo-SLAM2 | FLS | Oculus M750d | DVL, IMU | DRACo-SLAM2: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams with Object Graph Matching | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | — | — | — |
| 2025 | RUSSO | FLS | 未报告 | 双目 相机, IMU | RUSSO: Robust Underwater SLAM With Sonar Optimization Against Visual Degradation | IEEE/ASME Transactions on Mechatronics | [10.1109/TMECH.2025.3550730](https://doi.org/10.1109/TMECH.2025.3550730) | [RUSSO](https://github.com/CLASS-Lab/RUSSO) | [![Stars](https://img.shields.io/github/stars/CLASS-Lab/RUSSO?style=flat-square&label=stars)](https://github.com/CLASS-Lab/RUSSO) |
| 2025 | DFLSO （里程计） | FLS | BlueView M900 | 可选 IMU / pose prior | Direct Forward-Looking Sonar Odometry: A Two-Stage Odometry for Underwater Robot Localization | Remote Sensing | [10.3390/rs17132166](https://doi.org/10.3390/rs17132166) | — | — |
| 2026 | Above and Below | FLS | 未报告 | DVL, IMU; 水面激光雷达 | Above and Below: Heterogeneous Multi-Robot SLAM Across Surface and Underwater Domains | IEEE Robotics and Automation Letters | [10.1109/LRA.2025.3632613](https://doi.org/10.1109/LRA.2025.3632613) | [Above-and-Below-SLAM](https://github.com/Jake-maritime-lab/Above-and-Below-SLAM) | [![Stars](https://img.shields.io/github/stars/Jake-maritime-lab/Above-and-Below-SLAM?style=flat-square&label=stars)](https://github.com/Jake-maritime-lab/Above-and-Below-SLAM) |
| 2026 | Multi-Session SLAM | FLS | Oculus M750d | DVL, IMU; 激光雷达先验 | Multi-Session SLAM for Imaging Sonar Equipped Underwater Vehicles Using Semantic Scene Graphs | IEEE Robotics and Automation Letters | [10.1109/LRA.2026.3693583](https://doi.org/10.1109/LRA.2026.3693583) | [Multi-Session-Underwater-SLAM-With-Imaging-Sonar](https://github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar) | [![Stars](https://img.shields.io/github/stars/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar?style=flat-square&label=stars)](https://github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar) |
| 2026 | ISOPoT （里程计） | FLS | Oculus M750d | 可选 里程计 / 磁力计 | ISOPoT: Imaging Sonar Odometry by Point Tracking | arXiv | [arXiv](https://arxiv.org/abs/2606.23006) | — | — |
| 2026 | — （里程计） | FLS | 未报告 | IMU | Deep Learning-Based Fourier Registration for Forward-Looking Sonar Odometry in Texture-Sparse Underwater Environments | IEEE Robotics and Automation Letters | [10.1109/LRA.2026.3668623](https://doi.org/10.1109/LRA.2026.3668623) | — | — |

## 机械扫描成像声呐（MSIS）

| 年份 | 方法 / 系统 | 声呐类别 | 声呐型号 | 其他传感器 | 论文 | 期刊 / 会议 | 论文链接 / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|---|
| 2009 | MSISpIC | MSIS | 未报告 | DVL, MRU / gyro罗经 | Pose-based SLAM with probabilistic scan matching algorithm using a mechanical scanned imaging sonar | Not reported | — | — | — |
| 2020 | RBPF-MSIS | MSIS | 未报告 | IMU, DVL, 深度计 | RBPF-MSIS: Toward Rao-Blackwellized Particle Filter SLAM for Autonomous Underwater Vehicle With Slow Mechanical Scanning Imaging Sonar | IEEE Systems Journal | [10.1109/JSYST.2019.2938599](https://doi.org/10.1109/JSYST.2019.2938599) | — | — |
| 2022 | SVIn2 | MSIS / 剖面声呐 | IMAGENEX 831L DPP | 双目/单目 相机, IMU, 压力计 | SVIn2: A multi-sensor fusion-based underwater SLAM system | The International Journal of Robotics Research | [10.1177/02783649221110259](https://doi.org/10.1177/02783649221110259) | [SVIn2](https://github.com/sharminrahman/SVIn2) | [![Stars](https://img.shields.io/github/stars/sharminrahman/SVIn2?style=flat-square&label=stars)](https://github.com/sharminrahman/SVIn2) |
| 2023 | — | MSIS / 剖面声呐 | Tritech Super SeaKing Profiler | DVL, IMU, 压力计, 磁力计 | Underwater Pose SLAM using GMM scan matching for a mechanical profiling sonar | Journal of Field Robotics | [10.1002/rob.22272](https://doi.org/10.1002/rob.22272) | — | — |
| 2024 | — | MSIS | Tritech Micron | IMU, 深度计, 相机 ground truth | Sonar-based SLAM using Particle Filter and Free-Space Mapping Approach | IEEE/OES Autonomous Underwater Vehicles Symposium (AUV) | [10.1109/AUV61864.2024.11030776](https://doi.org/10.1109/AUV61864.2024.11030776) | — | — |

## 3D声呐

| 年份 | 方法 / 系统 | 声呐类别 | 声呐型号 | 其他传感器 | 论文 | 期刊 / 会议 | 论文链接 / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|---|
| 2022 | 3DupIC （配准） | 3D声呐 | Coda Octopus Echoscope | DVL, 陀螺仪 | 3DupIC: An Underwater Scan Matching Method for Three-Dimensional Sonar Registration | Sensors | [10.3390/s22103631](https://doi.org/10.3390/s22103631) | — | — |
| 2026 | InsSo3D | 3D声呐 | Water Linked Sonar3D-15 | DVL, AHRS, 压力计 | InsSo3D: Inertial Navigation System and 3D Sonar SLAM for Turbid Environment Inspection | arXiv | [arXiv](https://arxiv.org/abs/2601.05805) | — | — |
| 2026 | — | 3D剖面声呐 | Coda Octopus Echoscope | DVL, 陀螺仪 | Underwater SLAM and Calibration with a 3D Profiling Sonar | Remote Sensing | [10.3390/rs18030524](https://doi.org/10.3390/rs18030524) | — | — |
| 2026 | RA-SIDO （里程计） | 3D声呐 | Water Linked Sonar3D-15 | IMU, 深度计 | RA-SIDO: Robust and Adaptive Sonar–Inertial–Depth Odometry for Consistent Underwater Acoustic 3D Mapping | Journal of Marine Science and Engineering | [10.3390/jmse14161520](https://doi.org/10.3390/jmse14161520) | — | — |

## 侧扫声呐（SSS）

| 年份 | 方法 / 系统 | 声呐类别 | 声呐型号 | 其他传感器 | 论文 | 期刊 / 会议 | 论文链接 / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|---|
| 2024 | — | SSS | EdgeTech 2205 | DVL, INS, 罗经, 压力计 | A Fully-automatic Side-scan Sonar SLAM Framework | IET Radar, Sonar & Navigation | [arXiv](https://arxiv.org/abs/2304.01854) | [diasss](https://github.com/halajun/diasss) | [![Stars](https://img.shields.io/github/stars/halajun/diasss?style=flat-square&label=stars)](https://github.com/halajun/diasss) |
| 2025 | — | SSS | DeepVision DE3468D | DVL, 罗经, IMU | Side Scan Sonar-based SLAM for Autonomous Algae Farm Monitoring | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | [10.1109/IROS60139.2025.11246888](https://doi.org/10.1109/IROS60139.2025.11246888) | [sss_farm_slam](https://github.com/julRusVal/sss_farm_slam) | [![Stars](https://img.shields.io/github/stars/julRusVal/sss_farm_slam?style=flat-square&label=stars)](https://github.com/julRusVal/sss_farm_slam) |
| 2025 | Dense Subframe SLAM | SSS | EdgeTech 2205 | DVL, INS | A Dense Subframe-Based SLAM Framework With Side-Scan Sonar | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2024.3503663](https://doi.org/10.1109/JOE.2024.3503663) | [acoustic_slam](https://github.com/halajun/acoustic_slam) | [![Stars](https://img.shields.io/github/stars/halajun/acoustic_slam?style=flat-square&label=stars)](https://github.com/halajun/acoustic_slam) |
| 2025 | NeuRSS | SSS | 未报告 | 航位推算; MBES 参考 | NeuRSS: Enhancing AUV Localization and Bathymetric Mapping With Neural Rendering for Sidescan SLAM | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2024.3501317](https://doi.org/10.1109/JOE.2024.3501317) | — | — |
| 2026 | — | SSS | 未报告 | DVL, IMU, 深度计 / 高度计 | Side-Scan Sonar SLAM Using Ping-Level Landmark Detection in Feature-Poor Seabed Environments | IEEE Robotics and Automation Letters | [10.1109/LRA.2026.3692094](https://doi.org/10.1109/LRA.2026.3692094) | — | — |

## 多波束测深声呐（MBES）

| 年份 | 方法 / 系统 | 声呐类别 | 声呐型号 | 其他传感器 | 论文 | 期刊 / 会议 | 论文链接 / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|---|
| 2020 | PointNetKL （SLAM协方差） | MBES | Kongsberg EM2040 | 导航 / 航位推算 | PointNetKL: Deep Inference for GICP Covariance Estimation in Bathymetric SLAM | IEEE Robotics and Automation Letters | [10.1109/LRA.2020.2988180](https://doi.org/10.1109/LRA.2020.2988180) | — | — |
| 2021 | — | MBES | T-SEA CMBS200 | INS / GPS 参考 | Efficient Bathymetric SLAM with Invalid Loop Closure Identification | IEEE/ASME Transactions on Mechatronics | [10.1109/TMECH.2020.3043136](https://doi.org/10.1109/TMECH.2020.3043136) | — | — |
| 2022 | — （闭环） | MBES | Kongsberg EM2040 | INS / 航位推算 | Data-driven Loop Closure Detection in Bathymetric Point Clouds for Underwater SLAM | arXiv | [arXiv](https://arxiv.org/abs/2209.08578) | [bathy_nn_learning](https://github.com/tjr16/bathy_nn_learning) | [![Stars](https://img.shields.io/github/stars/tjr16/bathy_nn_learning?style=flat-square&label=stars)](https://github.com/tjr16/bathy_nn_learning) |
| 2022 | Cooperative BSLAM | MBES | T-SEA CMBS200 | INS; 水声通信 / 测距 | Communication-constrained cooperative bathymetric simultaneous localisation and mapping with efficient bathymetric data transmission method | The Journal of Navigation | [10.1017/S0373463321000904](https://doi.org/10.1017/S0373463321000904) | — | — |
| 2023 | Active BSLAM | MBES | 未报告 | 光纤陀螺 / INS, 深度计 | Active Bathymetric SLAM for autonomous underwater exploration | Applied Ocean Research | [10.1016/j.apor.2022.103439](https://doi.org/10.1016/j.apor.2022.103439) | — | — |
| 2024 | TTT SLAM | MBES | Kongsberg EM2040 / 测绘MBES | INS / 航位推算 | TTT SLAM: A feature-based bathymetric SLAM framework | Ocean Engineering | [10.1016/j.oceaneng.2024.116777](https://doi.org/10.1016/j.oceaneng.2024.116777) | — | — |
| 2025 | BRSLAM | MBES | T-SEA CMBS200 | INS; 声学信标 | Robust underwater SLAM fusing bathymetric and range information | Measurement | [10.1016/j.measurement.2024.116223](https://doi.org/10.1016/j.measurement.2024.116223) | — | — |
| 2025 | MINS | MBES | 未报告 | IMU, DVL, 压力计 | MINS: Tightly coupled MultiBeam EchoSounder Inertial Navigation System for 3D bathymetric underwater inspection | Journal of Ocean Engineering and Science | [10.1016/j.joes.2025.08.010](https://doi.org/10.1016/j.joes.2025.08.010) | — | — |
| 2026 | MCHS-SLAM | MBES | Teledyne RESON SeaBat T20-S | INS, DVL, 深度计 | MCHS-SLAM: A Multi-Constraint Hybrid Strategy SLAM Framework for AUV-Based Seafloor Terrain Mapping | Journal of Marine Science and Engineering | [10.3390/jmse14090834](https://doi.org/10.3390/jmse14090834) | — | — |

## 缩写

| 缩写 | 含义 |
|---|---|
| FLS | 前视成像声呐 |
| MSIS | 机械扫描成像声呐 |
| SSS | 侧扫声呐 |
| MBES | 多波束测深声呐 |
| IMU | 惯性测量单元 |
| INS | 惯性导航系统 |
| DVL | 多普勒测速仪 |
| DR | 航位推算 |

## 参与维护

- 只新增完整SLAM方法，或直接用于声呐SLAM系统的里程计、配准、闭环和因子组件。
- 保留论文原始题名、期刊/会议名称、年份和持久论文链接。
- 不自行编造方法名称或传感器型号；来源未说明时使用“—”或“未报告”。
- 只链接经过核实的作者或项目仓库；第三方实现必须明确标注为非官方。
- 保持中英文表格同步：条目、顺序、传感器、论文、出版物、链接、仓库和徽章必须完全对应。

