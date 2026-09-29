# Awesome Sonar SLAM

**Research on sonar-based underwater SLAM systems.**

**Languages:** English | [简体中文](README.zh-CN.md)

This public index summarizes sonar-based SLAM methods and organizes the related papers into tables by sonar category.

## Contents

- [Sonar taxonomy](#sonar-taxonomy)
- [Forward-looking imaging sonar (FLS)](#forward-looking-imaging-sonar-fls)
- [Mechanical scanning imaging sonar (MSIS)](#mechanical-scanning-imaging-sonar-msis)
- [3D sonar](#3d-sonar)
- [Side-scan sonar (SSS)](#side-scan-sonar-sss)
- [Multibeam echo sounder (MBES)](#multibeam-echo-sounder-mbes)
- [Abbreviations](#abbreviations)
- [Contributing](#contributing)

## Sonar taxonomy

This index uses five engineering categories based on primary measurement geometry and SLAM usage:

- **FLS:** forward-looking 2-D range–azimuth imaging sonar, commonly implemented with electronic multibeam beamforming. “MFLS” is not treated as a separate category.
- **MSIS:** mechanically scanned imaging or profiling sonar that forms a scan over time.
- **3D sonar:** sonar that directly resolves elevation and outputs 3-D points or range–azimuth–elevation measurements.
- **SSS:** side-looking sonar that forms strip imagery as the platform moves.
- **MBES:** mainly downward- or oblique-looking multibeam echo sounder used for bathymetric swaths and seabed maps.

“Multibeam” is a beamforming property, not a standalone category in this index. Original paper titles are never rewritten, so “multi-beam forward-looking sonar” may still appear inside a title.

## Forward-looking imaging sonar (FLS)

| Year | Method / system | Sensors | Sensor models | Paper | Venue | Paper / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|
| 2008 | ESEIF SLAM | FLS; IMU; DVL; depth | Sound Metrics DIDSON; Honeywell HG1700 IMU | SLAM for Ship Hull Inspection using Exactly Sparse Extended Information Filters | IEEE International Conference on Robotics and Automation (ICRA) | — | — | — |
| 2015 | — | FLS; DVL; IMU | Sound Metrics DIDSON; NavQuest 600 Micro DVL; Honeywell HG1700 IMU | Bundle Adjustment from Sonar Images and SLAM Application for Seafloor Mapping | MTS/IEEE OCEANS | — | — | — |
| 2015 | ASFM | FLS; DVL; IMU | Sound Metrics DIDSON | Towards Acoustic Structure from Motion for Imaging Sonar | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | — | — | — |
| 2018 | Pose-Graph SLAM | FLS; DVL; IMU | Sound Metrics DIDSON; RDI 1200 kHz DVL; Honeywell HG1700 IMU | Pose-Graph SLAM Using Forward-Looking Sonar | IEEE Robotics and Automation Letters | — | — | — |
| 2018 | — | FLS; DVL; IMU | Sound Metrics DIDSON | Feature-Based SLAM for Imaging Sonar with Under-Constrained Landmarks | IEEE International Conference on Robotics and Automation (ICRA) | — | — | — |
| 2020 | — | FLS; DVL; IMU; depth | Sound Metrics DIDSON; RDI 1200 kHz DVL; Honeywell HG1700 IMU | Degeneracy-Aware Imaging Sonar Simultaneous Localization and Mapping | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2019.2937946](https://doi.org/10.1109/JOE.2019.2937946) | — | — |
| 2020 | — (localization) | FLS; IMU; depth | - | Keyframe-Based Imaging Sonar Localization and Navigation using Elastic Windowed Optimization | Global OCEANS 2020 | [10.1109/IEEECONF38699.2020.9389045](https://doi.org/10.1109/IEEECONF38699.2020.9389045) | — | — |
| 2020 | — | FLS | - | 基于多波束声呐的同时定位与地图构建 | Digital Ocean & Underwater Warfare | [10.19838/j.issn.2096-5753.2020.03.013](https://doi.org/10.19838/j.issn.2096-5753.2020.03.013) | — | — |
| 2021 | — | FLS / acoustic camera; 2-DoF rotator | - | Acoustic Camera-Based Pose Graph SLAM for Dense 3-D Mapping in Underwater Environments | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2020.3033036](https://doi.org/10.1109/JOE.2020.3033036) | — | — |
| 2021 | RBPF-SLAM | FLS; IMU; DVL | - | Underwater SLAM Based on Forward-Looking Sonar | Communications in Computer and Information Science | [10.1007/978-981-16-2336-3_55](https://doi.org/10.1007/978-981-16-2336-3_55) | — | — |
| 2022 | RBPF-SLAM | FLS; IMU; DVL | - | Underwater Localization and Mapping Based on Multi-Beam Forward Looking Sonar | Frontiers in Neurorobotics | [10.3389/fnbot.2021.801956](https://doi.org/10.3389/fnbot.2021.801956) | — | — |
| 2022 | — (odometry) | FLS; IMU | - | Bundle Adjustment-Based Sonar-Inertial Odometry for Underwater Navigation | IEEE International Conference on Robotics and Biomimetics (ROBIO) | [10.1109/ROBIO55434.2022.10011721](https://doi.org/10.1109/ROBIO55434.2022.10011721) | — | — |
| 2022 | DRACo-SLAM | FLS; DVL; IMU; depth | Oculus M750d; Rowe SeaPilot DVL; VectorNav VN-100 IMU; BlueRobotics Bar30 pressure sensor | DRACo-SLAM: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | [10.1109/IROS47612.2022.9981822](https://doi.org/10.1109/IROS47612.2022.9981822) | [DRACo-SLAM](https://github.com/jake3991/DRACo-SLAM) | [![Stars](https://img.shields.io/github/stars/jake3991/DRACo-SLAM?style=flat-square&label=stars)](https://github.com/jake3991/DRACo-SLAM) |
| 2022 | — (SLAM factor) | FLS; DVL; IMU; overhead RGB imagery | Oculus M750d; Rowe SeaPilot DVL; VectorNav VN-100 IMU; BlueRobotics Bar30 pressure sensor | Overhead Image Factors for Underwater Sonar-Based SLAM | IEEE Robotics and Automation Letters | [10.1109/LRA.2022.3154048](https://doi.org/10.1109/LRA.2022.3154048) | — | — |
| 2022 | — | FLS; IMU; DVL; depth | - | Occupancy Grid-Based AUV SLAM Method with Forward-Looking Sonar | Journal of Marine Science and Engineering | [10.3390/jmse10081056](https://doi.org/10.3390/jmse10081056) | — | — |
| 2022 | — (localization) | FLS; IMU; depth | - | Robust inertial-aided underwater localization based on imaging sonar keyframes | arXiv | [arXiv](https://arxiv.org/abs/2106.16032) | — | — |
| 2022 | Virtual Maps (active SLAM) | FLS; Navigation sensors | Oculus M750d; Rowe SeaPilot DVL; VectorNav VN100 IMU; BlueRobotics Bar30 pressure sensor | Virtual Maps for Autonomous Exploration of Cluttered Underwater Environments | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2022.3153897](https://doi.org/10.1109/JOE.2022.3153897) | — | — |
| 2023 | — (localization) | FLS; DVL; IMU; depth | Kongsberg M3 | A localization algorithm based on pose graph using Forward-looking sonar for deep-sea mining vehicle | Ocean Engineering | [10.1016/j.oceaneng.2023.114968](https://doi.org/10.1016/j.oceaneng.2023.114968) | — | — |
| 2023 | — (odometry) | FLS; DVL; MEMS gyro; pressure | Sound Metrics DIDSON | A Study on Acoustic Odometry Estimation based on the Image Similarity using Forward-looking Sonar | Journal of Sensor Science and Technology | [10.46670/JSST.2023.32.5.313](https://doi.org/10.46670/JSST.2023.32.5.313) | — | — |
| 2024 | — (odometry) | FLS; IMU | Oculus M750d | An adaptive grouping sonar-inertial odometry for underwater navigation | Ocean Engineering | [10.1016/j.oceaneng.2024.116688](https://doi.org/10.1016/j.oceaneng.2024.116688) | — | — |
| 2024 | — | FLS; DVL; IMU; pressure | Oculus M750d | Sonar-Based Simultaneous Localization and Mapping Using the Semi-Direct Method | Journal of Marine Science and Engineering | [10.3390/jmse12122234](https://doi.org/10.3390/jmse12122234) | — | — |
| 2024 | — | FLS; DVL; IMU | - | Sonar SLAM in structured underwater environments | OCEANS 2024 - Singapore | [10.1109/OCEANS51537.2024.10682261](https://doi.org/10.1109/OCEANS51537.2024.10682261) | — | — |
| 2024 | — | FLS; DVL; IMU; depth | - | AUV SLAM method based on SO-CFAR and ADT feature extraction | Science Progress | [10.1177/00368504241286969](https://doi.org/10.1177/00368504241286969) | — | — |
| 2024 | DISO (odometry) | FLS; DVL; IMU | BlueView P900-130 | DISO: Direct Imaging Sonar Odometry | IEEE International Conference on Robotics and Automation (ICRA) | [10.1109/ICRA57147.2024.10611064](https://doi.org/10.1109/ICRA57147.2024.10611064) | [DISO](https://github.com/SenseRoboticsLab/DISO) | [![Stars](https://img.shields.io/github/stars/SenseRoboticsLab/DISO?style=flat-square&label=stars)](https://github.com/SenseRoboticsLab/DISO) |
| 2024 | GM SLAM | FLS; DVL; IMU; depth | Oculus M1200d | Graph Matching for Underwater Simultaneous Localization and Mapping Using Multibeam Sonar Imaging | Journal of Marine Science and Engineering | [10.3390/jmse12101859](https://doi.org/10.3390/jmse12101859) | — | — |
| 2024 | Opti-Acoustic Semantic SLAM | FLS; Camera; DVL; IMU; pressure | Oculus M1200d / M750d; Teledyne Impulse DVL; VectorNav IMU; BlueRobotics Bar30 pressure sensor | Opti-Acoustic Semantic SLAM with Unknown Objects in Underwater Environments | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | [10.1109/IROS58592.2024.10802819](https://doi.org/10.1109/IROS58592.2024.10802819) | — | — |
| 2025 | SIO-UV (odometry) | FLS; IMU | BlueView M900 | SIO-UV: Rapid and Robust Sonar Inertial Odometry for Underwater Vehicles | IEEE Transactions on Industrial Electronics | [10.1109/TIE.2025.3561817](https://doi.org/10.1109/TIE.2025.3561817) | — | — |
| 2025 | DRACo-SLAM2 | FLS; DVL; IMU | Oculus M750d; Rowe SeaPilot DVL; VectorNav VN100 IMU | DRACo-SLAM2: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams with Object Graph Matching | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | — | — | — |
| 2025 | RUSSO | FLS; Stereo camera; IMU | - | RUSSO: Robust Underwater SLAM With Sonar Optimization Against Visual Degradation | IEEE/ASME Transactions on Mechatronics | [10.1109/TMECH.2025.3550730](https://doi.org/10.1109/TMECH.2025.3550730) | [RUSSO](https://github.com/CLASS-Lab/RUSSO) | [![Stars](https://img.shields.io/github/stars/CLASS-Lab/RUSSO?style=flat-square&label=stars)](https://github.com/CLASS-Lab/RUSSO) |
| 2025 | DFLSO (odometry) | FLS; Optional IMU / pose prior | BlueView M900 | Direct Forward-Looking Sonar Odometry: A Two-Stage Odometry for Underwater Robot Localization | Remote Sensing | [10.3390/rs17132166](https://doi.org/10.3390/rs17132166) | — | — |
| 2026 | Above and Below | FLS; DVL; IMU; surface LiDAR | Oculus M750d; Nortek DVL-1000; VectorNav VN100 IMU; BlueRobotics Bar02 depth sensor; Velodyne VLP-32C LiDAR; Here3+ RTK-GPS | Above and Below: Heterogeneous Multi-Robot SLAM Across Surface and Underwater Domains | IEEE Robotics and Automation Letters | [10.1109/LRA.2025.3632613](https://doi.org/10.1109/LRA.2025.3632613) | [Above-and-Below-SLAM](https://github.com/Jake-maritime-lab/Above-and-Below-SLAM) | [![Stars](https://img.shields.io/github/stars/Jake-maritime-lab/Above-and-Below-SLAM?style=flat-square&label=stars)](https://github.com/Jake-maritime-lab/Above-and-Below-SLAM) |
| 2026 | Multi-Session SLAM | FLS; DVL; IMU; LiDAR prior | Oculus M750d; Nortek DVL1000; VectorNav VN100 IMU; Velodyne VLP-32C LiDAR; Here3+ RTK-GPS | Multi-Session SLAM for Imaging Sonar Equipped Underwater Vehicles Using Semantic Scene Graphs | IEEE Robotics and Automation Letters | [10.1109/LRA.2026.3693583](https://doi.org/10.1109/LRA.2026.3693583) | [Multi-Session-Underwater-SLAM-With-Imaging-Sonar](https://github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar) | [![Stars](https://img.shields.io/github/stars/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar?style=flat-square&label=stars)](https://github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar) |
| 2026 | ISOPoT (odometry) | FLS; Optional odometry / magnetometer | Oculus M750d | ISOPoT: Imaging Sonar Odometry by Point Tracking | arXiv | [arXiv](https://arxiv.org/abs/2606.23006) | — | — |
| 2026 | — (odometry) | FLS; IMU | - | Deep Learning-Based Fourier Registration for Forward-Looking Sonar Odometry in Texture-Sparse Underwater Environments | IEEE Robotics and Automation Letters | [10.1109/LRA.2026.3668623](https://doi.org/10.1109/LRA.2026.3668623) | — | — |

## Mechanical scanning imaging sonar (MSIS)

| Year | Method / system | Sensors | Sensor models | Paper | Venue | Paper / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|
| 2009 | MSISpIC | MSIS; DVL; MRU / gyrocompass | - | Pose-based SLAM with probabilistic scan matching algorithm using a mechanical scanned imaging sonar | Not reported | — | — | — |
| 2020 | RBPF-MSIS | MSIS; IMU; DVL; depth | - | RBPF-MSIS: Toward Rao-Blackwellized Particle Filter SLAM for Autonomous Underwater Vehicle With Slow Mechanical Scanning Imaging Sonar | IEEE Systems Journal | [10.1109/JSYST.2019.2938599](https://doi.org/10.1109/JSYST.2019.2938599) | — | — |
| 2022 | SVIn2 | MSIS / profiling sonar; Stereo/mono camera; IMU; pressure | IMAGENEX 831L DPP; USB-3 uEye cameras; MicroStrain 3DM-GX4-15 IMU; BlueRobotics Bar30 pressure sensor | SVIn2: A multi-sensor fusion-based underwater SLAM system | The International Journal of Robotics Research | [10.1177/02783649221110259](https://doi.org/10.1177/02783649221110259) | [SVIn2](https://github.com/sharminrahman/SVIn2) | [![Stars](https://img.shields.io/github/stars/sharminrahman/SVIn2?style=flat-square&label=stars)](https://github.com/sharminrahman/SVIn2) |
| 2023 | — | MSIS / profiling sonar; DVL; IMU; pressure; magnetometer | Tritech Super SeaKing Profiler | Underwater Pose SLAM using GMM scan matching for a mechanical profiling sonar | Journal of Field Robotics | [10.1002/rob.22272](https://doi.org/10.1002/rob.22272) | — | — |
| 2024 | — | MSIS; IMU; depth; camera ground truth | Tritech Micron | Sonar-based SLAM using Particle Filter and Free-Space Mapping Approach | IEEE/OES Autonomous Underwater Vehicles Symposium (AUV) | [10.1109/AUV61864.2024.11030776](https://doi.org/10.1109/AUV61864.2024.11030776) | — | — |

## 3D sonar

| Year | Method / system | Sensors | Sensor models | Paper | Venue | Paper / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|
| 2022 | 3DupIC (registration) | 3D sonar; DVL; gyroscope | Coda Octopus Echoscope | 3DupIC: An Underwater Scan Matching Method for Three-Dimensional Sonar Registration | Sensors | [10.3390/s22103631](https://doi.org/10.3390/s22103631) | — | — |
| 2026 | InsSo3D | 3D sonar; DVL; AHRS; pressure | Water Linked Sonar3D-15; Nortek Nucleus 1000 | InsSo3D: Inertial Navigation System and 3D Sonar SLAM for Turbid Environment Inspection | arXiv | [arXiv](https://arxiv.org/abs/2601.05805) | — | — |
| 2026 | — | 3D profiling sonar; DVL; gyroscope | Coda Octopus Echoscope | Underwater SLAM and Calibration with a 3D Profiling Sonar | Remote Sensing | [10.3390/rs18030524](https://doi.org/10.3390/rs18030524) | — | — |
| 2026 | RA-SIDO (odometry) | 3D sonar; IMU; depth | Water Linked Sonar3D-15 | RA-SIDO: Robust and Adaptive Sonar–Inertial–Depth Odometry for Consistent Underwater Acoustic 3D Mapping | Journal of Marine Science and Engineering | [10.3390/jmse14161520](https://doi.org/10.3390/jmse14161520) | — | — |

## Side-scan sonar (SSS)

| Year | Method / system | Sensors | Sensor models | Paper | Venue | Paper / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|
| 2024 | — | SSS; DVL; INS; compass; pressure | EdgeTech 2205 | A Fully-automatic Side-scan Sonar SLAM Framework | IET Radar, Sonar & Navigation | [arXiv](https://arxiv.org/abs/2304.01854) | [diasss](https://github.com/halajun/diasss) | [![Stars](https://img.shields.io/github/stars/halajun/diasss?style=flat-square&label=stars)](https://github.com/halajun/diasss) |
| 2025 | — | SSS; DVL; compass; IMU | DeepVision DE3468D | Side Scan Sonar-based SLAM for Autonomous Algae Farm Monitoring | IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | [10.1109/IROS60139.2025.11246888](https://doi.org/10.1109/IROS60139.2025.11246888) | [sss_farm_slam](https://github.com/julRusVal/sss_farm_slam) | [![Stars](https://img.shields.io/github/stars/julRusVal/sss_farm_slam?style=flat-square&label=stars)](https://github.com/julRusVal/sss_farm_slam) |
| 2025 | Dense Subframe SLAM | SSS; DVL; INS | EdgeTech 2205 | A Dense Subframe-Based SLAM Framework With Side-Scan Sonar | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2024.3503663](https://doi.org/10.1109/JOE.2024.3503663) | [acoustic_slam](https://github.com/halajun/acoustic_slam) | [![Stars](https://img.shields.io/github/stars/halajun/acoustic_slam?style=flat-square&label=stars)](https://github.com/halajun/acoustic_slam) |
| 2025 | NeuRSS | SSS; Dead reckoning; MBES reference | - | NeuRSS: Enhancing AUV Localization and Bathymetric Mapping With Neural Rendering for Sidescan SLAM | IEEE Journal of Oceanic Engineering | [10.1109/JOE.2024.3501317](https://doi.org/10.1109/JOE.2024.3501317) | — | — |
| 2026 | — | SSS; DVL; IMU; depth / altimeter | - | Side-Scan Sonar SLAM Using Ping-Level Landmark Detection in Feature-Poor Seabed Environments | IEEE Robotics and Automation Letters | [10.1109/LRA.2026.3692094](https://doi.org/10.1109/LRA.2026.3692094) | — | — |

## Multibeam echo sounder (MBES)

| Year | Method / system | Sensors | Sensor models | Paper | Venue | Paper / DOI | GitHub | Stars |
|---:|---|---|---|---|---|---|---|---|
| 2020 | PointNetKL (SLAM covariance) | MBES; Navigation / dead reckoning | Kongsberg EM2040 | PointNetKL: Deep Inference for GICP Covariance Estimation in Bathymetric SLAM | IEEE Robotics and Automation Letters | [10.1109/LRA.2020.2988180](https://doi.org/10.1109/LRA.2020.2988180) | — | — |
| 2021 | — | MBES; INS / GPS reference | T-SEA CMBS200; StarNeto XW-GI5651 INS/GNSS | Efficient Bathymetric SLAM with Invalid Loop Closure Identification | IEEE/ASME Transactions on Mechatronics | [10.1109/TMECH.2020.3043136](https://doi.org/10.1109/TMECH.2020.3043136) | — | — |
| 2022 | — (loop closure) | MBES; INS / dead reckoning | Kongsberg EM2040 | Data-driven Loop Closure Detection in Bathymetric Point Clouds for Underwater SLAM | arXiv | [arXiv](https://arxiv.org/abs/2209.08578) | [bathy_nn_learning](https://github.com/tjr16/bathy_nn_learning) | [![Stars](https://img.shields.io/github/stars/tjr16/bathy_nn_learning?style=flat-square&label=stars)](https://github.com/tjr16/bathy_nn_learning) |
| 2022 | Cooperative BSLAM | MBES; INS; acoustic communication / ranging | T-SEA CMBS200 | Communication-constrained cooperative bathymetric simultaneous localisation and mapping with efficient bathymetric data transmission method | The Journal of Navigation | [10.1017/S0373463321000904](https://doi.org/10.1017/S0373463321000904) | — | — |
| 2023 | Active BSLAM | MBES; FOG / INS; depth | - | Active Bathymetric SLAM for autonomous underwater exploration | Applied Ocean Research | [10.1016/j.apor.2022.103439](https://doi.org/10.1016/j.apor.2022.103439) | — | — |
| 2024 | TTT SLAM | MBES; INS / dead reckoning | Kongsberg EM2040 | TTT SLAM: A feature-based bathymetric SLAM framework | Ocean Engineering | [10.1016/j.oceaneng.2024.116777](https://doi.org/10.1016/j.oceaneng.2024.116777) | — | — |
| 2025 | BRSLAM | MBES; INS; acoustic beacons | T-SEA CMBS200; StarNeto XW-GI5651 INS/GNSS | Robust underwater SLAM fusing bathymetric and range information | Measurement | [10.1016/j.measurement.2024.116223](https://doi.org/10.1016/j.measurement.2024.116223) | — | — |
| 2025 | MINS | MBES; IMU; DVL; pressure | Imagenex 837B DELTA T; Phins Compact C3 IMU/INS; Nortek DVL1000-4000 m; Valeport miniSVS1000; Reach Alpha Pan & Tilt | MINS: Tightly coupled MultiBeam EchoSounder Inertial Navigation System for 3D bathymetric underwater inspection | Journal of Ocean Engineering and Science | [10.1016/j.joes.2025.08.010](https://doi.org/10.1016/j.joes.2025.08.010) | — | — |
| 2026 | MCHS-SLAM | MBES; INS; DVL; depth | Teledyne RESON SeaBat T20-S | MCHS-SLAM: A Multi-Constraint Hybrid Strategy SLAM Framework for AUV-Based Seafloor Terrain Mapping | Journal of Marine Science and Engineering | [10.3390/jmse14090834](https://doi.org/10.3390/jmse14090834) | — | — |

## Abbreviations

| Abbreviation | Meaning |
|---|---|
| FLS | Forward-looking imaging sonar |
| MSIS | Mechanical scanning imaging sonar |
| SSS | Side-scan sonar |
| MBES | Multibeam echo sounder |
| IMU | Inertial measurement unit |
| INS | Inertial navigation system |
| DVL | Doppler velocity log |
| DR | Dead reckoning |

## Contributing

- Add only methods that perform SLAM or provide a direct odometry, registration, loop-closure, or factor component used by a sonar SLAM system.
- Preserve the original paper title, venue title, year, and persistent paper link.
- Do not invent a method name or sensor model. Use “—” for an unnamed method and “-” when no specific hardware model is reported.
- Link only verified author/project repositories. Mark third-party implementations explicitly as unofficial.
- Keep the English and Chinese tables synchronized: the same rows, order, sensors, papers, venues, links, repositories, and badges.

