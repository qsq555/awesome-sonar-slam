# Awesome Sonar SLAM

**A curated list of papers, datasets, and reusable methods for sonar-based underwater SLAM.**

**Languages:** English | [简体中文](README.zh-CN.md)

This first release is compiled from a curated 205-paper research corpus. The primary scope is **forward-looking sonar (FLS), including multibeam forward-looking sonar (MFLS), with IMU and depth**, while related imaging-sonar, mechanical-scanning, multibeam, side-scan, bathymetric, and cross-modal work is included when it contributes a reusable SLAM component.

> **Status:** v0.1 · 2026-09-28  
> **Curation note:** This is a corpus-grounded research index, not a claim of exhaustive coverage. Paper titles are kept in their source language for retrieval. Paper links resolve to DOI/arXiv URLs when those URLs are reported in the underlying source records; `metadata-only` means that a stable URL was not reported and should be completed in a later bibliographic pass. “Code / data” is listed only when the source record reports a public resource.

## Contents

- [Scope and taxonomy](#scope-and-taxonomy)
- [Master table](#master-table)
- [Core FLS SLAM systems (including MFLS)](#core-fls-slam-systems-including-mfls)
- [Sonar-inertial odometry and SLAM front ends](#sonar-inertial-odometry-and-slam-front-ends)
- [3D imaging-sonar, acoustic-camera, and neural mapping](#3d-imaging-sonar-acoustic-camera-and-neural-mapping)
- [Loop closure, place recognition, and graph methods](#loop-closure-place-recognition-and-graph-methods)
- [MSIS, multibeam, side-scan, and bathymetric SLAM](#msis-multibeam-side-scan-and-bathymetric-slam)
- [Multisensor, cooperative, and active SLAM](#multisensor-cooperative-and-active-slam)
- [Learning-based sonar perception for SLAM](#learning-based-sonar-perception-for-slam)
- [Datasets, simulators, and reviews](#datasets-simulators-and-reviews)
- [Useful repositories and data resources](#useful-repositories-and-data-resources)
- [Notes for contributors](#notes-for-contributors)

## Scope and taxonomy

The categories are **functional and overlapping**: one paper may appear in more than one section when it supplies both a SLAM system and a reusable front-end or loop-closure method.

| Tag | Meaning |
|---|---|
| `FLS` | Forward-looking sonar; the umbrella term used throughout this index |
| `MFLS` | Multibeam forward-looking sonar; a multibeam subtype of FLS, retained when the source explicitly makes that distinction |
| `3D sonar` | Sonar with explicit elevation or 3-D point/depth output |
| `MSIS/MBES` | Mechanical scanning imaging sonar or multibeam echo sounder |
| `SSS` | Side-scan sonar |
| `Odom` | Relative pose / odometry front end rather than a complete global SLAM system |
| `Loop` | Place recognition, loop-closure detection, or graph consistency |
| `Map` | Occupancy, volumetric, bathymetric, TSDF, neural, or semantic map construction |
| `Fusion` | IMU, DVL, depth, camera, optical, acoustic, or multi-robot fusion |
| `Review` | Survey or review paper; useful for navigation rather than primary evidence |

## Master table

A single quick-reference table for public readers. Sensor names are given at the family level; a model name is included only where it is explicit in the reviewed source material. An empty DOI cell means that the current source record did not provide a stable DOI or URL.

| Sensor(s) | Method / role | Year | Paper | DOI / link |
|---|---|---:|---|---|
| FLS; IMU; depth/DVL | FLS navigation; imaging-sonar-aided localization | 2010 | Imaging Sonar-Aided Navigation for Autonomous Underwater Harbor Surveillance |  |
| FLS; IMU; depth/DVL | Sonar SLAM; neuro-evolutionary optimization | 2010 | [Sonar-Based Simultaneous Localization and Mapping Using a Neuro-Evolutionary Optimization](https://doi.org/10.1163/016918610X501435) | 10.1163/016918610X501435 |
| FLS; IMU; depth/DVL | FLS pose-graph SLAM | 2018 | Pose-Graph SLAM Using Forward-Looking Sonar |  |
| FLS; IMU; depth/DVL | Imaging sonar; under-constrained landmarks | 2018 | Feature-Based SLAM for Imaging Sonar with Under-Constrained Landmarks |  |
| FLS; IMU; depth/DVL | FLS; adaptive filtering / navigation | 2020 | [2D forward looking SONAR in underwater navigation aiding: An AUKF-based strategy for AUVs](https://doi.org/10.1016/j.ifacol.2020.12.1463) | 10.1016/j.ifacol.2020.12.1463 |
| FLS; IMU; DVL (RexROV2/UUV-Simulator) | FLS + IMU + DVL; RBPF occupancy mapping | 2021 | [Underwater SLAM Based on Forward-Looking Sonar](https://doi.org/10.1007/978-981-16-2336-3_55) | 10.1007/978-981-16-2336-3_55 |
| MFLS; DVL; IMU (RexROV2/BlueROV2) | MFLS localization and mapping | 2022 | [Underwater Localization and Mapping Based on Multi-Beam Forward Looking Sonar](https://doi.org/10.3389/fnbot.2021.801956) | 10.3389/fnbot.2021.801956 |
| FLS; IMU; depth/DVL | Imaging sonar keyframes + inertial aiding | 2022 | [Robust inertial-aided underwater localization based on imaging sonar keyframes](https://arxiv.org/abs/2106.16032) | arXiv:2106.16032 |
| FLS; IMU; depth/DVL | Occupancy-grid FLS SLAM | 2022 | [Occupancy Grid-Based AUV SLAM Method with Forward-Looking Sonar](https://doi.org/10.3390/jmse10081056) | 10.3390/jmse10081056 |
| FLS; IMU; depth/DVL | FLS pose graph for deep-sea mining | 2023 | [A localization algorithm based on pose graph using Forward-looking sonar for deep-sea mining vehicle](https://doi.org/10.1016/j.oceaneng.2023.114968) | 10.1016/j.oceaneng.2023.114968 |
| FLS; IMU; depth/DVL | Structured underwater environments | 2024 | [Sonar SLAM in structured underwater environments](https://doi.org/10.1109/OCEANS51537.2024.10682261) | 10.1109/OCEANS51537.2024.10682261 |
| Oculus M750d; DVL; IMU; pressure sensor | Semi-direct sonar-image SLAM | 2024 | [Sonar-Based Simultaneous Localization and Mapping Using the Semi-Direct Method](https://doi.org/10.3390/jmse12122234) | 10.3390/jmse12122234 |
| FLS; IMU; depth/DVL | SO-CFAR + ADT features | 2024 | [AUV SLAM method based on SO-CFAR and ADT feature extraction](https://doi.org/10.1177/00368504241286969) | 10.1177/00368504241286969 |
| FLS; IMU; depth/DVL | Multibeam sonar graph matching | 2024 | [Graph Matching for Underwater Simultaneous Localization and Mapping Using Multibeam Sonar Imaging](https://doi.org/10.3390/jmse12101859) | 10.3390/jmse12101859 |
| FLS; IMU; depth/DVL | Sonar preprocessing for AUV positioning / SLAM | 2025 | [A Novel Sonar Image Preprocessing Method for AUV Positioning Based on Underwater SLAM](https://doi.org/10.1109/TIM.2025.3595226) | 10.1109/TIM.2025.3595226 |
| Sonar; IMU | Slow-sampling sonar + graph optimization | 2015 | [Improving Localization Accuracy for an Underwater Robot With a Slow-Sampling Sonar Through Graph Optimization](https://doi.org/10.1109/JSEN.2015.2432082) | 10.1109/JSEN.2015.2432082 |
| Sonar; IMU | Bundle adjustment; sonar-inertial odometry | 2022 | [Bundle Adjustment-Based Sonar-Inertial Odometry for Underwater Navigation](https://doi.org/10.1109/ROBIO55434.2022.10011721) | 10.1109/ROBIO55434.2022.10011721 |
| Sonar; IMU | Acoustic-inertial features + graph optimization | 2022 | An Acoustic-Inertial Pose Estimation Method with Robust Feature Match and Graph Optimization |  |
| BlueROV2/M750D FLS; IMU | Adaptive grouping sonar-inertial odometry | 2024 | [An adaptive grouping sonar-inertial odometry for underwater navigation](https://doi.org/10.1016/j.oceaneng.2024.116688) | 10.1016/j.oceaneng.2024.116688 |
| BlueView P900-130; IMU/DVL (when available) | Direct imaging-sonar odometry | 2024 | [DISO: Direct Imaging Sonar Odometry](https://doi.org/10.1109/ICRA57147.2024.10611064) | 10.1109/ICRA57147.2024.10611064 |
| Water Linked Sonar 3D-15; IMU; depth sensor | Robust sonar-inertial-depth odometry | 2026 | [RA-SIDO: Robust and Adaptive Sonar–Inertial–Depth Odometry for Consistent Underwater Acoustic 3D Mapping](https://doi.org/10.3390/jmse14161520) | 10.3390/jmse14161520 |
| FLS; IMU (model not reported) | Tightly coupled inertial-sonar fusion | 2025 | A Tightly Coupled Inertial-Sonar Fusion for Localization of Underwater Robots |  |
| BlueView M900 FLS; IMU/relative-pose prior | Two-stage direct FLS odometry | 2025 | [Direct Forward-Looking Sonar Odometry: A Two-Stage Odometry for Underwater Robot Localization](https://doi.org/10.3390/rs17132166) | 10.3390/rs17132166 |
| FLS (model not reported) | Point-tracking imaging-sonar odometry | 2026 | [ISOPoT: Imaging Sonar Odometry by Point Tracking](https://arxiv.org/abs/2606.23006) | arXiv:2606.23006 |
| FLS; IMU pose-graph factors | Fourier registration for FLS odometry | 2026 | [Deep Learning-Based Fourier Registration for Forward-Looking Sonar Odometry in Texture-Sparse Underwater Environments](https://doi.org/10.1109/LRA.2026.3668623) | 10.1109/LRA.2026.3668623 |
| Sonar; IMU | Image-similarity acoustic odometry | 2023 | [A Study on Acoustic Odometry Estimation based on the Image Similarity using Forward-looking Sonar](https://doi.org/10.46670/JSST.2023.32.5.313) | 10.46670/JSST.2023.32.5.313 |
| 3D imaging sonar; INS/DVL | Acoustic structure from motion | 2015 | Towards Acoustic Structure from Motion for Imaging Sonar |  |
| 3D imaging sonar; INS/DVL | Acoustic-lens multibeam point clouds | 2018 | [AUV-Based Underwater 3-D Point Cloud Generation Using Acoustic Lens-Based Multibeam Sonar](https://doi.org/10.1109/JOE.2017.2751139) | 10.1109/JOE.2017.2751139 |
| 3D imaging sonar; INS/DVL | 3-D scan matching | 2022 | [3DupIC: An Underwater Scan Matching Method for Three-Dimensional Sonar Registration](https://doi.org/10.3390/s22103631) | 10.3390/s22103631 |
| 3D imaging sonar; INS/DVL | Fermat-path reconstruction | 2020 | [A Theory of Fermat Paths for 3D Imaging Sonar Reconstruction](https://doi.org/10.1109/IROS45743.2020.9341613) | 10.1109/IROS45743.2020.9341613 |
| 3D imaging sonar; INS/DVL | Volumetric albedo | 2020 | A Volumetric Albedo Framework for 3D Imaging Sonar Reconstruction |  |
| 3D imaging sonar; INS/DVL | Differentiable / volumetric reconstruction | 2020 | [Fusing concurrent orthogonal wide-aperture sonar images for dense underwater 3D reconstruction](https://arxiv.org/abs/2007.10407) | arXiv:2007.10407 |
| Tritech Gemini 720i; DVL; INS | Spatial acoustic projection + neural TSDF | 2022 | [Spatial Acoustic Projection for 3D Imaging Sonar Reconstruction](https://doi.org/10.1109/ICRA46639.2022.9812277) | 10.1109/ICRA46639.2022.9812277 |
| Two imaging sonars | Two-sonar probabilistic reconstruction | 2022 | [Probabilistic 3D Reconstruction Using Two Sonar Devices](https://doi.org/10.3390/s22062094) | 10.3390/s22062094 |
| 3D imaging sonar; INS/DVL | Differentiable space carving | 2024 | [Differentiable Space Carving for 3D Reconstruction Using Imaging Sonar](https://doi.org/10.1109/LRA.2024.3469778) | 10.1109/LRA.2024.3469778 |
| 3D imaging sonar; INS/DVL | Volumetric free-space mapping | 2024 | [Underwater Volumetric Mapping using Imaging Sonar and Free-Space Modeling Approach](https://doi.org/10.1109/ICRA57147.2024.10611082) | 10.1109/ICRA57147.2024.10611082 |
| FLS; INS/DVL | Neural fields for FLS reconstruction | 2025 | [NFFLS: Rapid and Accurate Underwater 3-D Reconstruction With Neural Fields for Forward-Looking Sonar](https://doi.org/10.1109/JOE.2025.3590076) | 10.1109/JOE.2025.3590076 |
| 3D imaging sonar; INS/DVL | Neural acoustic reconstruction under pose drift | 2025 | [Acoustic Neural 3D Reconstruction Under Pose Drift](https://doi.org/10.1109/IROS60139.2025.11247485) | 10.1109/IROS60139.2025.11247485 |
| WaterLinked Sonar3D-15; Nortek Nucleus 1000 DVL/AHRS/pressure; stereo camera for reference | 3-D sonar + INS submaps, GICP, TSDF | 2026 | [InsSo3D: Inertial Navigation System and 3D Sonar SLAM for Turbid Environment Inspection](https://arxiv.org/abs/2601.05805) | arXiv:2601.05805 |
| 3D imaging sonar; INS/DVL | Neural implicit surface reconstruction | 2026 | [Sonar-neus: voxel-based efficient neural implicit surface reconstruction for forward-looking sonar](https://doi.org/10.1016/j.neunet.2026.108664) | 10.1016/j.neunet.2026.108664 |
| 3D imaging sonar; INS/DVL | Noise-aware sonar Gaussian splatting | 2026 | [NAS-GS: Noise-Aware Sonar Gaussian Splatting](https://doi.org/10.1109/LRA.2026.3706932) | 10.1109/LRA.2026.3706932 |
| 3D imaging sonar; INS/DVL | Sonar-guided Gaussian-splatting SLAM | 2026 | [SonarReg-GS SLAM: Sparse Sonar-Guided Depth Regularization for Underwater Gaussian Splatting SLAM](https://doi.org/10.3390/s26154713) | 10.3390/s26154713 |
| Imaging sonar/FLS | Sonar-based feature relocation | 2013 | [Relocating Underwater Features Autonomously Using Sonar-Based SLAM](https://doi.org/10.1109/JOE.2012.2235664) | 10.1109/JOE.2012.2235664 |
| Imaging sonar/FLS | Topological FLS place recognition | 2018 | [Underwater place recognition using forward-looking sonar images: A topological approach](https://doi.org/10.1002/rob.21822) | 10.1002/rob.21822 |
| MSIS | MSIS loop closure with PHD filtering | 2019 | [Underwater Loop-Closure Detection for Mechanical Scanning Imaging Sonar by Filtering the Similarity Matrix With Probability Hypothesis Density Filter](https://doi.org/10.1109/ACCESS.2019.2952445) | 10.1109/ACCESS.2019.2952445 |
| Bathymetric sonar/MBES | Bathymetric loop-closure invalidation | 2021 | [Efficient Bathymetric SLAM with Invalid Loop Closure Identification](https://doi.org/10.1109/TMECH.2020.3043136) | 10.1109/TMECH.2020.3043136 |
| Bathymetric sonar/MBES | Learned bathymetric loop closure | 2022 | [Data-driven Loop Closure Detection in Bathymetric Point Clouds for Underwater SLAM](https://arxiv.org/abs/2209.08578) | arXiv:2209.08578 |
| Imaging sonar/FLS | Overhead-image factors | 2022 | [Overhead Image Factors for Underwater Sonar-Based SLAM](https://doi.org/10.1109/LRA.2022.3154048) | 10.1109/LRA.2022.3154048 |
| Imaging sonar/FLS | Robust imaging-sonar place recognition | 2023 | [Robust Imaging Sonar-based Place Recognition and Localization in Underwater Environments](https://doi.org/10.1109/ICRA48891.2023.10161518) | 10.1109/ICRA48891.2023.10161518 |
| Imaging sonar/FLS | Learned FLS descriptors | 2023 | [Improving Generalization of Synthetically Trained Sonar Image Descriptors for Underwater Place Recognition](https://doi.org/10.1007/978-3-031-44137-0_28) | 10.1007/978-3-031-44137-0_28 |
| Imaging sonar/FLS | FLS feature-based place recognition | 2023 | [Feature-Based Place Recognition Using Forward-Looking Sonar](https://doi.org/10.3390/jmse11112198) | 10.3390/jmse11112198 |
| Imaging sonar/FLS | Communication-constrained cooperative loop closure | 2024 | [An efficient loop closure detection method for communication-constrained bathymetric cooperative SLAM](https://doi.org/10.1016/j.oceaneng.2024.117720) | 10.1016/j.oceaneng.2024.117720 |
| Side-scan sonar | Side-scan topology matching | 2024 | [Side-Scan Sonar Image Matching Method Based on Topology Representation](https://doi.org/10.3390/jmse12050782) | 10.3390/jmse12050782 |
| Imaging sonar/FLS | Multi-session semantic scene graphs | 2026 | [Multi-Session SLAM for Imaging Sonar Equipped Underwater Vehicles Using Semantic Scene Graphs](https://doi.org/10.1109/LRA.2026.3693583) | 10.1109/LRA.2026.3693583 |
| MSIS/imaging sonar | Mechanical scanning imaging sonar; probabilistic scan matching | 2009 | Pose-based SLAM with probabilistic scan matching algorithm using a mechanical scanned imaging sonar |  |
| MSIS/imaging sonar | Ship-hull inspection; sparse extended information filter | 2008 | SLAM for Ship Hull Inspection using Exactly Sparse Extended Information Filters |  |
| MSIS/imaging sonar | MSIS; Rao–Blackwellized particle filter | 2020 | [RBPF-MSIS: Toward Rao-Blackwellized Particle Filter SLAM for Autonomous Underwater Vehicle With Slow Mechanical Scanning Imaging Sonar](https://doi.org/10.1109/JSYST.2019.2938599) | 10.1109/JSYST.2019.2938599 |
| WASSP 120 kHz MBES; Norbit WBMS 400 kHz; RTK-GPS; AHRS/IMU; DVL; CTD | Bathymetric SLAM dataset and ground truth | 2022 | [A bathymetric mapping and SLAM dataset with high-precision ground truth for marine robotics](https://doi.org/10.1177/02783649211044749) | 10.1177/02783649211044749 |
| Bathymetric sonar/MBES | Active bathymetric exploration | 2023 | [Active Bathymetric SLAM for autonomous underwater exploration](https://doi.org/10.1016/j.apor.2022.103439) | 10.1016/j.apor.2022.103439 |
| Bathymetric sonar/MBES | Cooperative bathymetric SLAM | 2022 | [Communication-constrained cooperative bathymetric simultaneous localisation and mapping with efficient loop closures](https://doi.org/10.1017/S0373463321000904) | 10.1017/S0373463321000904 |
| Bathymetric sonar/MBES | Feature-based bathymetric SLAM | 2024 | [TTT SLAM: A feature-based bathymetric SLAM framework](https://doi.org/10.1016/j.oceaneng.2024.116777) | 10.1016/j.oceaneng.2024.116777 |
| MSIS/imaging sonar | GMM scan matching for profiling sonar | 2023 | [Underwater Pose SLAM using GMM scan matching for a mechanical profiling sonar](https://doi.org/10.1002/rob.22272) | 10.1002/rob.22272 |
| Forward-looking acoustic camera; 2-DoF roll/pitch rotator (no IMU/DVL required) | Acoustic-camera pose graph and dense 3-D mapping | 2021 | [Acoustic Camera-Based Pose Graph SLAM for Dense 3-D Mapping in Underwater Environments](https://doi.org/10.1109/JOE.2020.3033036) | 10.1109/JOE.2020.3033036 |
| Side-scan sonar | Fully automatic side-scan SLAM | 2024 | [A Fully-automatic Side-scan Sonar SLAM Framework](https://arxiv.org/abs/2304.01854) | arXiv:2304.01854 |
| Bathymetric sonar/MBES | Bathymetric + range fusion | 2025 | [Robust underwater SLAM fusing bathymetric and range information](https://doi.org/10.1016/j.measurement.2024.116223) | 10.1016/j.measurement.2024.116223 |
| Side-scan sonar | Side-scan SLAM in algae-farm monitoring | 2025 | [Side Scan Sonar-based SLAM for Autonomous Algae Farm Monitoring](https://doi.org/10.1109/IROS60139.2025.11246888) | 10.1109/IROS60139.2025.11246888 |
| Side-scan sonar | Dense subframe side-scan SLAM | 2025 | [A Dense Subframe-Based SLAM Framework With Side-Scan Sonar](https://doi.org/10.1109/JOE.2024.3503663) | 10.1109/JOE.2024.3503663 |
| MBES; IMU; DVL; depth/pressure | Multibeam echo-sounder + INS | 2025 | [MINS: Tightly coupled MultiBeam EchoSounder Inertial Navigation System for 3D bathymetric underwater inspection](https://doi.org/10.1016/j.joes.2025.08.010) | 10.1016/j.joes.2025.08.010 |
| Side-scan sonar | Neural rendering for side-scan SLAM | 2025 | [NeuRSS: Enhancing AUV Localization and Bathymetric Mapping With Neural Rendering for Sidescan SLAM](https://doi.org/10.1109/JOE.2024.3501317) | 10.1109/JOE.2024.3501317 |
| MSIS/imaging sonar | High-resolution imaging-sonar mapping | 2026 | [High-resolution underwater mapping in low-visibility and confined environments using imaging sonar](https://doi.org/10.1016/j.apor.2026.104959) | 10.1016/j.apor.2026.104959 |
| Sonar; camera/optical | Optical + acoustic pose-graph SLAM | 2024 | [Pose-graph underwater simultaneous localization and mapping for autonomous monitoring and 3D reconstruction by means of optical and acoustic sensors](https://doi.org/10.1002/rob.22375) | 10.1002/rob.22375 |
| Sonar; camera/optical | Multi-session opti-acoustic factor graph | 2021 | [Multi-session Underwater Pose-graph SLAM using Inter-session Opti-acoustic Two-view Factor](https://doi.org/10.1109/ICRA48506.2021.9561161) | 10.1109/ICRA48506.2021.9561161 |
| Sonar; camera/optical | Visual SLAM with acoustic sensing | 2021 | [Robust Underwater Visual SLAM Fusing Acoustic Sensing](https://doi.org/10.1109/ICRA48506.2021.9561537) | 10.1109/ICRA48506.2021.9561537 |
| Sonar; camera; IMU; depth/DVL | Sonar, visual, inertial, and depth | 2019 | SVIn2: An Underwater SLAM System Using Sonar, Visual, Inertial, and Depth Sensor |  |
| Sonar; camera/IMU | Open multi-sensor SVIn2 system | 2022 | [SVIn2: A multi-sensor fusion-based underwater SLAM system](https://doi.org/10.1177/02783649221110259) | 10.1177/02783649221110259 |
| Imaging sonar; inter-robot communication | Distributed acoustic multi-robot SLAM | 2022 | [DRACo-SLAM: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams](https://doi.org/10.1109/IROS47612.2022.9981822) | 10.1109/IROS47612.2022.9981822 |
| Imaging sonar; navigation sensors | Virtual maps for active exploration | 2022 | [Virtual Maps for Autonomous Exploration of Cluttered Underwater Environments](https://doi.org/10.1109/JOE.2022.3153897) | 10.1109/JOE.2022.3153897 |
| Sonar; camera/optical | Opti-acoustic semantic SLAM | 2024 | [Opti-Acoustic Semantic SLAM with Unknown Objects in Underwater Environments](https://doi.org/10.1109/IROS58592.2024.10802819) | 10.1109/IROS58592.2024.10802819 |
| Sonar; camera; IMU; depth/DVL | Visual–inertial–acoustic SLAM with DVL | 2025 | [VIA-SLAM: An Underwater Visual–Inertial–Acoustic SLAM With Integrated DVL](https://doi.org/10.1109/TIM.2025.3571157) | 10.1109/TIM.2025.3571157 |
| Sonar; camera/optical | Sonar optimization under visual degradation | 2025 | [RUSSO: Robust Underwater SLAM With Sonar Optimization Against Visual Degradation](https://doi.org/10.1109/TMECH.2025.3550730) | 10.1109/TMECH.2025.3550730 |
| Imaging sonar; inter-robot communication | Distributed acoustic SLAM sequel | 2025 | DRACo-SLAM2: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams with Object Graph Matching |  |
| Sonar; camera/optical | Tightly coupled acoustic–visual–inertial calibration | 2025 | [AQUA-SLAM Tightly coupled underwater acoustic-visual-inertial SLAM with sensor calibration](https://doi.org/10.1109/TRO.2025.3554396) | 10.1109/TRO.2025.3554396 |
| Surface/underwater sonar; multi-robot sensors | Heterogeneous surface–underwater multi-robot SLAM | 2026 | [Above and Below: Heterogeneous Multi-Robot SLAM Across Surface and Underwater Domains](https://doi.org/10.1109/LRA.2025.3632613) | 10.1109/LRA.2025.3632613 |
| FLS/imaging sonar | Pseudo-front-view elevation estimation | 2021 | [Elevation Angle Estimation in 2D Acoustic Images Using Pseudo Front View](https://doi.org/10.1109/LRA.2021.3058911) | 10.1109/LRA.2021.3058911 |
| FLS/imaging sonar | Learned pseudo-front depth / multi-view stereo | 2022 | [Learning Pseudo Front Depth for 2D Forward-Looking Sonar-based Multi-view Stereo](https://doi.org/10.1109/IROS47612.2022.9982049) | 10.1109/IROS47612.2022.9982049 |
| Imaging sonar | cGAN sonar filtering for occupancy mapping | 2023 | [Conditional GANs for Sonar Image Filtering with Applications to Underwater Occupancy Mapping](https://doi.org/10.1109/ICRA48891.2023.10160646) | 10.1109/ICRA48891.2023.10160646 |
| Imaging sonar | Self-supervised elevation and motion degeneracy | 2023 | [Motion Degeneracy in Self-supervised Learning of Elevation Angle Estimation for 2D Forward-Looking Sonar](https://doi.org/10.1109/IROS55552.2023.10341601) | 10.1109/IROS55552.2023.10341601 |
| Imaging sonar | Pose-supervised sonar correspondences | 2024 | [SONIC: Sonar Image Correspondence using Pose Supervised Learning for Imaging Sonars](https://doi.org/10.1109/ICRA57147.2024.10611678) | 10.1109/ICRA57147.2024.10611678 |
| Imaging sonar | Global/local flow registration | 2022 | [GPLFR—Global perspective and local flow registration for forward-looking sonar images](https://doi.org/10.1007/s00521-022-07113-8) | 10.1007/s00521-022-07113-8 |
| Acoustic camera | Differentiable acoustic-camera pose refinement | 2023 | [Acoustic Camera Pose Refinement Using Differentiable Rendering](https://doi.org/10.1109/SII55687.2023.10039267) | 10.1109/SII55687.2023.10039267 |
| FLS/imaging sonar | Rolling-shutter compensation for acoustic lens FLS | 2024 | [Analysis and Compensation of Acoustic Rolling Shutter Effect of Acoustic-Lens-Based Forward-Looking Sonar](https://doi.org/10.1109/JOE.2023.3341466) | 10.1109/JOE.2023.3341466 |
| FLS/imaging sonar | Acoustic-n-point estimation | 2025 | [BESTAnP: Bi-Step Efficient and Statistically Optimal Estimator for Acoustic-n-Point Problem](https://doi.org/10.1109/LRA.2025.3558451) | 10.1109/LRA.2025.3558451 |
| FLS/imaging sonar | Convex global PnP for 2-D FLS | 2025 | [A Convex and Global Solution for the PnP Problem in 2D Forward-Looking Sonar](https://doi.org/10.1109/OCEANS58557.2025.11104528) | 10.1109/OCEANS58557.2025.11104528 |
| FLS/imaging sonar | Outlier rejection for FLS correspondences | 2025 | [Rejecting Outliers in 2D-3D Point Correspondences from 2D Forward-Looking Sonar Observations](https://doi.org/10.1109/IROS60139.2025.11246791) | 10.1109/IROS60139.2025.11246791 |
| Sonar; IMU | Sonar-inertial odometry with wavelets | 2026 | [DeepWavelet: A Multimodal Wavelet-Based Network for Sonar-Inertial Odometry in Underwater Robots](https://doi.org/10.1109/JOE.2025.3630404) | 10.1109/JOE.2025.3630404 |
| MFLS | MFLS SLAM | 2020 | [基于多波束声呐的同时定位与地图构建](https://doi.org/10.19838/j.issn.2096-5753.2020.03.013) | 10.19838/j.issn.2096-5753.2020.03.013 |
| FLS; camera/IMU | FLS–visual–inertial SLAM thesis | 2023 | 基于前视声呐-视觉-惯性的水下SLAM算法研究 |  |
| FLS; camera/IMU | FLS SLAM thesis | 2024 | 基于前视声呐的水下机器人SLAM技术研究 |  |
| MFLS | MFLS SLAM thesis | 2024 | 基于多波束声呐的水下同步定位与地图构建 |  |
| Sonar; camera/IMU/depth | Multi-sensor underwater SLAM thesis | 2024 | Research on Multi-Sensor Simultaneous Localization and Mapping Method for Underwater Robots |  |
| Sonar | Underwater SLAM review | 2025 | [水下机器人同步定位与建图关键技术进展与展望](https://doi.org/10.3969/j.issn.1003-2029.2025.03.011) | 10.3969/j.issn.1003-2029.2025.03.011 |
| FLS; camera/IMU | FLS 3-D odometry review / method | 2026 | [前视声呐三维视觉里程计技术](https://doi.org/10.12395/0371-0025.2025015) | 10.12395/0371-0025.2025015 |

## Core FLS SLAM systems (including MFLS)

Direct localization-and-mapping systems closest to the minimal FLS (including MFLS) + IMU + depth research stack.

| Year | Sensor / method | Paper |
|---:|---|---|
| 2010 | FLS navigation; imaging-sonar-aided localization | Imaging Sonar-Aided Navigation for Autonomous Underwater Harbor Surveillance |
| 2010 | Sonar SLAM; neuro-evolutionary optimization | Sonar-Based Simultaneous Localization and Mapping Using a Neuro-Evolutionary Optimization ([paper](https://doi.org/10.1163/016918610X501435)) |
| 2018 | FLS pose-graph SLAM | Pose-Graph SLAM Using Forward-Looking Sonar |
| 2018 | Imaging sonar; under-constrained landmarks | Feature-Based SLAM for Imaging Sonar with Under-Constrained Landmarks |
| 2020 | FLS; adaptive filtering / navigation | 2D forward looking SONAR in underwater navigation aiding: An AUKF-based strategy for AUVs ([paper](https://doi.org/10.1016/j.ifacol.2020.12.1463)) |
| 2021 | FLS + IMU + DVL; RBPF occupancy mapping | Underwater SLAM Based on Forward-Looking Sonar ([paper](https://doi.org/10.1007/978-981-16-2336-3_55)) |
| 2022 | MFLS localization and mapping | Underwater Localization and Mapping Based on Multi-Beam Forward Looking Sonar ([paper](https://doi.org/10.3389/fnbot.2021.801956)) |
| 2022 | Imaging sonar keyframes + inertial aiding | Robust inertial-aided underwater localization based on imaging sonar keyframes ([paper](https://arxiv.org/abs/2106.16032)) |
| 2022 | Occupancy-grid FLS SLAM | Occupancy Grid-Based AUV SLAM Method with Forward-Looking Sonar ([paper](https://doi.org/10.3390/jmse10081056)) |
| 2023 | FLS pose graph for deep-sea mining | A localization algorithm based on pose graph using Forward-looking sonar for deep-sea mining vehicle ([paper](https://doi.org/10.1016/j.oceaneng.2023.114968)) |
| 2024 | Structured underwater environments | Sonar SLAM in structured underwater environments ([paper](https://doi.org/10.1109/OCEANS51537.2024.10682261)) |
| 2024 | Semi-direct sonar-image SLAM | Sonar-Based Simultaneous Localization and Mapping Using the Semi-Direct Method ([paper](https://doi.org/10.3390/jmse12122234)) |
| 2024 | SO-CFAR + ADT features | AUV SLAM method based on SO-CFAR and ADT feature extraction ([paper](https://doi.org/10.1177/00368504241286969)) |
| 2024 | Multibeam sonar graph matching | Graph Matching for Underwater Simultaneous Localization and Mapping Using Multibeam Sonar Imaging ([paper](https://doi.org/10.3390/jmse12101859)) |
| 2025 | Sonar preprocessing for AUV positioning / SLAM | A Novel Sonar Image Preprocessing Method for AUV Positioning Based on Underwater SLAM ([paper](https://doi.org/10.1109/TIM.2025.3595226)) |

## Sonar-inertial odometry and SLAM front ends

Relative-pose estimation methods that can serve as the front end of an FLS SLAM system, including systems using MFLS devices.

| Year | Front end | Paper |
|---:|---|---|
| 2015 | Slow-sampling sonar + graph optimization | Improving Localization Accuracy for an Underwater Robot With a Slow-Sampling Sonar Through Graph Optimization ([paper](https://doi.org/10.1109/JSEN.2015.2432082)) |
| 2022 | Bundle adjustment; sonar-inertial odometry | Bundle Adjustment-Based Sonar-Inertial Odometry for Underwater Navigation ([paper](https://doi.org/10.1109/ROBIO55434.2022.10011721)) |
| 2022 | Acoustic-inertial features + graph optimization | An Acoustic-Inertial Pose Estimation Method with Robust Feature Match and Graph Optimization |
| 2024 | Adaptive grouping sonar-inertial odometry | An adaptive grouping sonar-inertial odometry for underwater navigation ([paper](https://doi.org/10.1016/j.oceaneng.2024.116688)) |
| 2024 | Direct imaging-sonar odometry | DISO: Direct Imaging Sonar Odometry ([paper](https://doi.org/10.1109/ICRA57147.2024.10611064)) |
| 2026 | Robust sonar-inertial-depth odometry | RA-SIDO: Robust and Adaptive Sonar–Inertial–Depth Odometry for Consistent Underwater Acoustic 3D Mapping ([paper](https://doi.org/10.3390/jmse14161520)) |
| 2025 | Tightly coupled inertial-sonar fusion | A Tightly Coupled Inertial-Sonar Fusion for Localization of Underwater Robots |
| 2025 | Two-stage direct FLS odometry | Direct Forward-Looking Sonar Odometry: A Two-Stage Odometry for Underwater Robot Localization ([paper](https://doi.org/10.3390/rs17132166)) |
| 2026 | Point-tracking imaging-sonar odometry | ISOPoT: Imaging Sonar Odometry by Point Tracking ([paper](https://arxiv.org/abs/2606.23006)) |
| 2026 | Fourier registration for FLS odometry | Deep Learning-Based Fourier Registration for Forward-Looking Sonar Odometry in Texture-Sparse Underwater Environments ([paper](https://doi.org/10.1109/LRA.2026.3668623)) |
| 2023 | Image-similarity acoustic odometry | A Study on Acoustic Odometry Estimation based on the Image Similarity using Forward-looking Sonar ([paper](https://doi.org/10.46670/JSST.2023.32.5.313)) |

## 3D imaging-sonar, acoustic-camera, and neural mapping

Methods that recover elevation, 3-D structure, volumetric maps, or neural scene representations from acoustic measurements.

| Year | Representation / method | Paper |
|---:|---|---|
| 2015 | Acoustic structure from motion | Towards Acoustic Structure from Motion for Imaging Sonar |
| 2018 | Acoustic-lens multibeam point clouds | AUV-Based Underwater 3-D Point Cloud Generation Using Acoustic Lens-Based Multibeam Sonar ([paper](https://doi.org/10.1109/JOE.2017.2751139)) |
| 2022 | 3-D scan matching | 3DupIC: An Underwater Scan Matching Method for Three-Dimensional Sonar Registration ([paper](https://doi.org/10.3390/s22103631)) |
| 2020 | Fermat-path reconstruction | A Theory of Fermat Paths for 3D Imaging Sonar Reconstruction ([paper](https://doi.org/10.1109/IROS45743.2020.9341613)) |
| 2020 | Volumetric albedo | A Volumetric Albedo Framework for 3D Imaging Sonar Reconstruction |
| 2020 | Differentiable / volumetric reconstruction | Fusing concurrent orthogonal wide-aperture sonar images for dense underwater 3D reconstruction ([paper](https://arxiv.org/abs/2007.10407)) |
| 2022 | Spatial acoustic projection + neural TSDF | Spatial Acoustic Projection for 3D Imaging Sonar Reconstruction ([paper](https://doi.org/10.1109/ICRA46639.2022.9812277)) |
| 2022 | Two-sonar probabilistic reconstruction | Probabilistic 3D Reconstruction Using Two Sonar Devices ([paper](https://doi.org/10.3390/s22062094)) |
| 2024 | Differentiable space carving | Differentiable Space Carving for 3D Reconstruction Using Imaging Sonar ([paper](https://doi.org/10.1109/LRA.2024.3469778)) |
| 2024 | Volumetric free-space mapping | Underwater Volumetric Mapping using Imaging Sonar and Free-Space Modeling Approach ([paper](https://doi.org/10.1109/ICRA57147.2024.10611082)) |
| 2025 | Neural fields for FLS reconstruction | NFFLS: Rapid and Accurate Underwater 3-D Reconstruction With Neural Fields for Forward-Looking Sonar ([paper](https://doi.org/10.1109/JOE.2025.3590076)) |
| 2025 | Neural acoustic reconstruction under pose drift | Acoustic Neural 3D Reconstruction Under Pose Drift ([paper](https://doi.org/10.1109/IROS60139.2025.11247485)) |
| 2026 | 3-D sonar + INS submaps, GICP, TSDF | InsSo3D: Inertial Navigation System and 3D Sonar SLAM for Turbid Environment Inspection ([paper](https://arxiv.org/abs/2601.05805)) |
| 2026 | Neural implicit surface reconstruction | Sonar-neus: voxel-based efficient neural implicit surface reconstruction for forward-looking sonar ([paper](https://doi.org/10.1016/j.neunet.2026.108664)) |
| 2026 | Noise-aware sonar Gaussian splatting | NAS-GS: Noise-Aware Sonar Gaussian Splatting ([paper](https://doi.org/10.1109/LRA.2026.3706932)) |
| 2026 | Sonar-guided Gaussian-splatting SLAM | SonarReg-GS SLAM: Sparse Sonar-Guided Depth Regularization for Underwater Gaussian Splatting SLAM ([paper](https://doi.org/10.3390/s26154713)) |

## Loop closure, place recognition, and graph methods

The loop-closure and relocalization layer is often the difference between locally plausible sonar odometry and globally useful maps.

| Year | Component | Paper |
|---:|---|---|
| 2013 | Sonar-based feature relocation | Relocating Underwater Features Autonomously Using Sonar-Based SLAM ([paper](https://doi.org/10.1109/JOE.2012.2235664)) |
| 2018 | Topological FLS place recognition | Underwater place recognition using forward-looking sonar images: A topological approach ([paper](https://doi.org/10.1002/rob.21822)) |
| 2019 | MSIS loop closure with PHD filtering | Underwater Loop-Closure Detection for Mechanical Scanning Imaging Sonar by Filtering the Similarity Matrix With Probability Hypothesis Density Filter ([paper](https://doi.org/10.1109/ACCESS.2019.2952445)) |
| 2021 | Bathymetric loop-closure invalidation | Efficient Bathymetric SLAM with Invalid Loop Closure Identification ([paper](https://doi.org/10.1109/TMECH.2020.3043136)) |
| 2022 | Learned bathymetric loop closure | Data-driven Loop Closure Detection in Bathymetric Point Clouds for Underwater SLAM ([paper](https://arxiv.org/abs/2209.08578)) |
| 2022 | Overhead-image factors | Overhead Image Factors for Underwater Sonar-Based SLAM ([paper](https://doi.org/10.1109/LRA.2022.3154048)) |
| 2023 | Robust imaging-sonar place recognition | Robust Imaging Sonar-based Place Recognition and Localization in Underwater Environments ([paper](https://doi.org/10.1109/ICRA48891.2023.10161518)) |
| 2023 | Learned FLS descriptors | Improving Generalization of Synthetically Trained Sonar Image Descriptors for Underwater Place Recognition ([paper](https://doi.org/10.1007/978-3-031-44137-0_28)) |
| 2023 | FLS feature-based place recognition | Feature-Based Place Recognition Using Forward-Looking Sonar ([paper](https://doi.org/10.3390/jmse11112198)) |
| 2024 | Communication-constrained cooperative loop closure | An efficient loop closure detection method for communication-constrained bathymetric cooperative SLAM ([paper](https://doi.org/10.1016/j.oceaneng.2024.117720)) |
| 2024 | Side-scan topology matching | Side-Scan Sonar Image Matching Method Based on Topology Representation ([paper](https://doi.org/10.3390/jmse12050782)) |
| 2026 | Multi-session semantic scene graphs | Multi-Session SLAM for Imaging Sonar Equipped Underwater Vehicles Using Semantic Scene Graphs ([paper](https://doi.org/10.1109/LRA.2026.3693583)) |

## MSIS, multibeam, side-scan, and bathymetric SLAM

These systems are outside the minimal FLS stack but provide mature alternatives for sparse, slow, wide-area, or seabed-mapping missions.

| Year | Sonar family / method | Paper |
|---:|---|---|
| 2009 | Mechanical scanning imaging sonar; probabilistic scan matching | Pose-based SLAM with probabilistic scan matching algorithm using a mechanical scanned imaging sonar |
| 2008 | Ship-hull inspection; sparse extended information filter | SLAM for Ship Hull Inspection using Exactly Sparse Extended Information Filters |
| 2020 | MSIS; Rao–Blackwellized particle filter | RBPF-MSIS: Toward Rao-Blackwellized Particle Filter SLAM for Autonomous Underwater Vehicle With Slow Mechanical Scanning Imaging Sonar ([paper](https://doi.org/10.1109/JSYST.2019.2938599)) |
| 2022 | Bathymetric SLAM dataset and ground truth | A bathymetric mapping and SLAM dataset with high-precision ground truth for marine robotics ([paper](https://doi.org/10.1177/02783649211044749)) |
| 2023 | Active bathymetric exploration | Active Bathymetric SLAM for autonomous underwater exploration ([paper](https://doi.org/10.1016/j.apor.2022.103439)) |
| 2022 | Cooperative bathymetric SLAM | Communication-constrained cooperative bathymetric simultaneous localisation and mapping with efficient loop closures ([paper](https://doi.org/10.1017/S0373463321000904)) |
| 2024 | Feature-based bathymetric SLAM | TTT SLAM: A feature-based bathymetric SLAM framework ([paper](https://doi.org/10.1016/j.oceaneng.2024.116777)) |
| 2023 | GMM scan matching for profiling sonar | Underwater Pose SLAM using GMM scan matching for a mechanical profiling sonar ([paper](https://doi.org/10.1002/rob.22272)) |
| 2021 | Acoustic-camera pose graph and dense 3-D mapping | Acoustic Camera-Based Pose Graph SLAM for Dense 3-D Mapping in Underwater Environments ([paper](https://doi.org/10.1109/JOE.2020.3033036)) |
| 2024 | Fully automatic side-scan SLAM | A Fully-automatic Side-scan Sonar SLAM Framework ([paper](https://arxiv.org/abs/2304.01854)) |
| 2025 | Bathymetric + range fusion | Robust underwater SLAM fusing bathymetric and range information ([paper](https://doi.org/10.1016/j.measurement.2024.116223)) |
| 2025 | Side-scan SLAM in algae-farm monitoring | Side Scan Sonar-based SLAM for Autonomous Algae Farm Monitoring ([paper](https://doi.org/10.1109/IROS60139.2025.11246888)) |
| 2025 | Dense subframe side-scan SLAM | A Dense Subframe-Based SLAM Framework With Side-Scan Sonar ([paper](https://doi.org/10.1109/JOE.2024.3503663)) |
| 2025 | Multibeam echo-sounder + INS | MINS: Tightly coupled MultiBeam EchoSounder Inertial Navigation System for 3D bathymetric underwater inspection ([paper](https://doi.org/10.1016/j.joes.2025.08.010)) |
| 2025 | Neural rendering for side-scan SLAM | NeuRSS: Enhancing AUV Localization and Bathymetric Mapping With Neural Rendering for Sidescan SLAM ([paper](https://doi.org/10.1109/JOE.2024.3501317)) |
| 2026 | High-resolution imaging-sonar mapping | High-resolution underwater mapping in low-visibility and confined environments using imaging sonar ([paper](https://doi.org/10.1016/j.apor.2026.104959)) |

## Multisensor, cooperative, and active SLAM

Sonar is often strongest when paired with inertial, depth, DVL, camera, optical, or multi-robot constraints. These papers are useful for later sensor-stack extensions.

| Year | Fusion / system | Paper |
|---:|---|---|
| 2024 | Optical + acoustic pose-graph SLAM | Pose-graph underwater simultaneous localization and mapping for autonomous monitoring and 3D reconstruction by means of optical and acoustic sensors ([paper](https://doi.org/10.1002/rob.22375)) |
| 2021 | Multi-session opti-acoustic factor graph | Multi-session Underwater Pose-graph SLAM using Inter-session Opti-acoustic Two-view Factor ([paper](https://doi.org/10.1109/ICRA48506.2021.9561161)) |
| 2021 | Visual SLAM with acoustic sensing | Robust Underwater Visual SLAM Fusing Acoustic Sensing ([paper](https://doi.org/10.1109/ICRA48506.2021.9561537)) |
| 2019 | Sonar, visual, inertial, and depth | SVIn2: An Underwater SLAM System Using Sonar, Visual, Inertial, and Depth Sensor |
| 2022 | Open multi-sensor SVIn2 system | SVIn2: A multi-sensor fusion-based underwater SLAM system ([paper](https://doi.org/10.1177/02783649221110259)) |
| 2022 | Distributed acoustic multi-robot SLAM | DRACo-SLAM: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams ([paper](https://doi.org/10.1109/IROS47612.2022.9981822)) |
| 2022 | Virtual maps for active exploration | Virtual Maps for Autonomous Exploration of Cluttered Underwater Environments ([paper](https://doi.org/10.1109/JOE.2022.3153897)) |
| 2024 | Opti-acoustic semantic SLAM | Opti-Acoustic Semantic SLAM with Unknown Objects in Underwater Environments ([paper](https://doi.org/10.1109/IROS58592.2024.10802819)) |
| 2025 | Visual–inertial–acoustic SLAM with DVL | VIA-SLAM: An Underwater Visual–Inertial–Acoustic SLAM With Integrated DVL ([paper](https://doi.org/10.1109/TIM.2025.3571157)) |
| 2025 | Sonar optimization under visual degradation | RUSSO: Robust Underwater SLAM With Sonar Optimization Against Visual Degradation ([paper](https://doi.org/10.1109/TMECH.2025.3550730)) |
| 2025 | Distributed acoustic SLAM sequel | DRACo-SLAM2: Distributed Robust Acoustic Communication-efficient SLAM for Imaging Sonar Equipped Underwater Robot Teams with Object Graph Matching |
| 2025 | Tightly coupled acoustic–visual–inertial calibration | AQUA-SLAM Tightly coupled underwater acoustic-visual-inertial SLAM with sensor calibration ([paper](https://doi.org/10.1109/TRO.2025.3554396)) |
| 2026 | Heterogeneous surface–underwater multi-robot SLAM | Above and Below: Heterogeneous Multi-Robot SLAM Across Surface and Underwater Domains ([paper](https://doi.org/10.1109/LRA.2025.3632613)) |

## Learning-based sonar perception for SLAM

These works are front-end, correspondence, denoising, elevation, or neural-rendering modules rather than all being complete SLAM systems.

| Year | Module | Paper |
|---:|---|---|
| 2021 | Pseudo-front-view elevation estimation | Elevation Angle Estimation in 2D Acoustic Images Using Pseudo Front View ([paper](https://doi.org/10.1109/LRA.2021.3058911)) |
| 2022 | Learned pseudo-front depth / multi-view stereo | Learning Pseudo Front Depth for 2D Forward-Looking Sonar-based Multi-view Stereo ([paper](https://doi.org/10.1109/IROS47612.2022.9982049)) |
| 2023 | cGAN sonar filtering for occupancy mapping | Conditional GANs for Sonar Image Filtering with Applications to Underwater Occupancy Mapping ([paper](https://doi.org/10.1109/ICRA48891.2023.10160646)) |
| 2023 | Self-supervised elevation and motion degeneracy | Motion Degeneracy in Self-supervised Learning of Elevation Angle Estimation for 2D Forward-Looking Sonar ([paper](https://doi.org/10.1109/IROS55552.2023.10341601)) |
| 2024 | Pose-supervised sonar correspondences | SONIC: Sonar Image Correspondence using Pose Supervised Learning for Imaging Sonars ([paper](https://doi.org/10.1109/ICRA57147.2024.10611678)) |
| 2022 | Global/local flow registration | GPLFR—Global perspective and local flow registration for forward-looking sonar images ([paper](https://doi.org/10.1007/s00521-022-07113-8)) |
| 2023 | Differentiable acoustic-camera pose refinement | Acoustic Camera Pose Refinement Using Differentiable Rendering ([paper](https://doi.org/10.1109/SII55687.2023.10039267)) |
| 2024 | Rolling-shutter compensation for acoustic lens FLS | Analysis and Compensation of Acoustic Rolling Shutter Effect of Acoustic-Lens-Based Forward-Looking Sonar ([paper](https://doi.org/10.1109/JOE.2023.3341466)) |
| 2025 | Acoustic-n-point estimation | BESTAnP: Bi-Step Efficient and Statistically Optimal Estimator for Acoustic-n-Point Problem ([paper](https://doi.org/10.1109/LRA.2025.3558451)) |
| 2025 | Convex global PnP for 2-D FLS | A Convex and Global Solution for the PnP Problem in 2D Forward-Looking Sonar ([paper](https://doi.org/10.1109/OCEANS58557.2025.11104528)) |
| 2025 | Outlier rejection for FLS correspondences | Rejecting Outliers in 2D-3D Point Correspondences from 2D Forward-Looking Sonar Observations ([paper](https://doi.org/10.1109/IROS60139.2025.11246791)) |
| 2026 | Sonar-inertial odometry with wavelets | DeepWavelet: A Multimodal Wavelet-Based Network for Sonar-Inertial Odometry in Underwater Robots ([paper](https://doi.org/10.1109/JOE.2025.3630404)) |

## Datasets, simulators, and reviews

| Type | Resource | Paper |
|---|---|---|
| Dataset | Bathymetric mapping and SLAM with high-precision ground truth | A bathymetric mapping and SLAM dataset with high-precision ground truth for marine robotics ([paper](https://doi.org/10.1177/02783649211044749)) |
| Dataset | Natural-scenario AUV navigation data | Underwater AUV Navigation Dataset in Natural Scenarios ([paper](https://doi.org/10.3390/electronics12183788)) |
| Dataset / simulator | Scanning sonar with ground-truth localization | Scanning Sonar Data From an Underwater Robot With Ground Truth Localization ([paper](https://doi.org/10.1109/ACCESS.2024.3420766)) |
| Simulator | Synthetic scans from low-cost mechanical scanning sonar | Synthetic Scan Formation for Underwater Mapping with Low-Cost Mechanical Scanning Sonars (MSS) ([paper](https://doi.org/10.1109/ACCESS.2023.3312186)) |
| Review | Underwater SLAM technologies | An Overview of Key SLAM Technologies for Underwater Scenes ([paper](https://doi.org/10.3390/rs15102496)) |
| Review | Deep learning and multi-sensor integration | Underwater SLAM Meets Deep Learning: Challenges, Multi-Sensor Integration, and Future Directions ([paper](https://doi.org/10.3390/s25113258)) |
| Review | Bathymetric SLAM | A review of AUV-based bathymetric SLAM technology ([paper](https://doi.org/10.1016/j.oceaneng.2025.122858)) |
| Review | Sonar-based SLAM methods | Research on Sonar-based Simultaneous Localization and Mapping Methods for Autonomous Underwater Robots |

## Chinese-language and thesis entries in the corpus

These entries are retained because they describe implementations, sensor configurations, or reviews that may not have an English journal counterpart in the current corpus. Titles are kept in the source language for retrieval.

| Year | Type / focus | Paper or thesis |
|---:|---|---|
| 2020 | MFLS SLAM | 基于多波束声呐的同时定位与地图构建 ([paper](https://doi.org/10.19838/j.issn.2096-5753.2020.03.013)) |
| 2023 | FLS–visual–inertial SLAM thesis | 基于前视声呐-视觉-惯性的水下SLAM算法研究 |
| 2024 | FLS SLAM thesis | 基于前视声呐的水下机器人SLAM技术研究 |
| 2024 | MFLS SLAM thesis | 基于多波束声呐的水下同步定位与地图构建 |
| 2024 | Multi-sensor underwater SLAM thesis | Research on Multi-Sensor Simultaneous Localization and Mapping Method for Underwater Robots |
| 2025 | Underwater SLAM review | 水下机器人同步定位与建图关键技术进展与展望 ([paper](https://doi.org/10.3969/j.issn.1003-2029.2025.03.011)) |
| 2026 | FLS 3-D odometry review / method | 前视声呐三维视觉里程计技术 ([paper](https://doi.org/10.12395/0371-0025.2025015)) |

## Useful repositories and data resources

The following links are reported in the source records. Availability, license, and revision should be checked before using them in an experiment.

| Resource | Link |
|---|---|
| OpenSonarDatasets | [github.com/remaro-network/OpenSonarDatasets](https://github.com/remaro-network/OpenSonarDatasets) |
| SONIC correspondence code and data | [github.com/rpl-cmu/sonic](https://github.com/rpl-cmu/sonic) |
| Sonar-context place recognition | [github.com/sparolab/sonar_context](https://github.com/sparolab/sonar_context) |
| Bathymetric dataset / parsing resources | [seaward.science/data/pos](https://www.seaward.science/data/pos) |
| DRACo-SLAM | [github.com/jake3991/DRACo-SLAM](https://github.com/jake3991/DRACo-SLAM) |
| Above-and-Below heterogeneous SLAM | [github.com/Jake-maritime-lab/Above-and-Below-SLAM](https://github.com/Jake-maritime-lab/Above-and-Below-SLAM/) |
| Multi-session imaging-sonar SLAM | [github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar](https://github.com/Maritime-Autonomy-Lab/Multi-Session-Underwater-SLAM-With-Imaging-Sonar) |
| RUSSO | [github.com/CLASS-Lab/RUSSO](https://github.com/CLASS-Lab/RUSSO) |
| SVIn2 | [github.com/sharminrahman/SVIn2](https://github.com/sharminrahman/SVIn2) |
| SonarGraph | [github.com/matheusbg8/SonarGraph](https://github.com/matheusbg8/SonarGraph) |
| BESTAnP | [github.com/LIAS-CUHKSZ/BESTAnP](https://github.com/LIAS-CUHKSZ/BESTAnP) |
| Bathymetric loop-closure learning | [github.com/tjr16/bathy_nn_learning](https://github.com/tjr16/bathy_nn_learning) |
| Side-scan algae-farm SLAM | [github.com/julRusVal/sss_farm_slam](https://github.com/julRusVal/sss_farm_slam) |
| Acoustic-camera simulator | [github.com/sollynoay](https://github.com/sollynoay) |
| A2FNet | [github.com/sollynoay/A2FNet](https://github.com/sollynoay/A2FNet) |
| EPSSN | [github.com/sollynoay/EPSSN](https://github.com/sollynoay/EPSSN) |
| Sonar simulator (Blender) | [github.com/sollynoay/Sonar-simulator-blender](https://github.com/sollynoay/Sonar-simulator-blender) |
| DISO | [github.com/SenseRoboticsLab/DISO](https://github.com/SenseRoboticsLab/DISO) |
| AQUA-SLAM | [github.com/SenseRoboticsLab/AQUA-SLAM](https://github.com/SenseRoboticsLab/AQUA-SLAM) |
| Side-scan SLAM framework | [github.com/halajun/diasss](https://github.com/halajun/diasss) |
| Dense subframe side-scan SLAM | [github.com/halajun/acoustic_slam](https://github.com/halajun/acoustic_slam) |
| Side-scan sonar data | [github.com/YDY-andy/Sonar-dataset](https://github.com/YDY-andy/Sonar-dataset) |
| AUV navigation dataset | [github.com/nature1949/AUV_navigation_dataset](https://github.com/nature1949/AUV_navigation_dataset) |

## Metadata-only entries

Some older papers, theses, or supplied PDFs do not yet have a stable DOI/URL in the current source records; those entries are intentionally left with an empty DOI/link cell for later verification.

## Notes for contributors

- Keep paper titles and persistent links together so that later bibliographic corrections remain traceable.
- Add a paper only after verifying the title, year, venue, and persistent URL from the paper card or an authoritative publication page.
- Put a method in the most specific functional section first; duplicate it in another section only when it provides a distinct reusable component.
- Report code/data links separately from paper links, and do not infer that “authors state code will be released” means that a repository is already public.
- In future releases, expand the Chinese-language and thesis appendix, add license/status columns for repositories, and record benchmark/sensor configuration in a machine-readable companion table.

