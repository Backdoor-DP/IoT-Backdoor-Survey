# Backdoor Attacks and Defenses for Machine Learning in the Internet of Things

A curated list of the studies collected for our survey *Backdoor Attacks and Defenses for Machine Learning in the Internet of Things: A Survey From Sensing to On-Device Inference* (under review at IEEE Internet of Things Journal).

The list covers 349 studies published from 2019 to 2026: 215 attacks, 94 defenses, and 40 evaluations, benchmarks, surveys, and standards. Each attack and defense is labeled with its class in our taxonomy, its trigger type, the highest validation level it reaches, and whether it is IoT-specific or a general study that transfers to IoT. The same data are available as [`papers.csv`](papers.csv).

## Taxonomy

- **Attacks** are grouped by where the attacker intervenes: data poisoning, attacks on collaborative learning, model supply chain attacks, and hardware attacks.
- **Defenses** are grouped by where they are deployed: data level, training level, model level, and inference level.
- **Trigger**: *digital* (added to stored or transmitted data), *physical* (produced in the real world and captured by the sensor), *natural* (a condition that arises without attacker action at inference), *processing or fault* (activated by the victim's quantization or compilation, or by a hardware fault).
- **Validation**: *simulation*; *recorded data* with triggers added in software; *physical trigger* captured by a real sensor but evaluated offline; *real system* (a live device, a physical channel, or a closed loop; for defenses, execution on real hardware).
- **Scope**: *IoT-specific* if the study uses IoT data, explicitly models an IoT system, or targets an IoT sensing modality; *general* if IoT serves only as motivation and all experiments use generic benchmarks.

## Search Strategy

Sources: OpenAlex, Crossref, Semantic Scholar, arXiv, IEEE Xplore, the ACM Digital Library, and the proceedings of major security venues, followed by citation chasing. Window: 1 January 2019 to 18 November 2026.

Each query combined the backdoor term `B = backdoor OR backdoors OR trojan OR trojaned OR (trigger AND poisoning)` with one group of scenario terms:

| Group | Scenario terms |
|---|---|
| Sensing | "radio frequency" OR "RF fingerprint" OR "modulation recognition" OR "semantic communication" OR "wireless sensing" OR CSI OR mmWave OR radar OR RFID OR "human activity recognition" OR IMU OR wearable OR EEG OR ECG OR "time series" OR "keyword spotting" OR "speaker verification" OR "voice assistant" OR "physical backdoor" OR LiDAR OR "traffic sign" OR "autonomous driving" OR surveillance OR UAV |
| Network | "intrusion detection" OR NIDS OR "network traffic" OR "traffic classification" OR packet OR flow OR "device identification" |
| Collaborative | ("federated learning" OR "split learning" OR "vertical federated" OR decentralized OR "continual learning" OR "federated unlearning") AND (IoT OR IIoT OR vehicular OR IoV OR UAV OR edge OR IoMT OR "smart grid") |
| Deployment | quantization OR pruning OR compression OR "model conversion" OR compiler OR "bit-flip" OR rowhammer OR "fault injection" OR ("hardware trojan" AND ("neural network" OR DNN)) OR "on-device model" OR TinyML OR microcontroller OR OTA OR "model supply chain" OR "edge deployment" |
| Foundation models | ("large language model" OR LLM OR "foundation model" OR "vision-language" OR embodied OR agent) AND (IoT OR "smart home" OR AIoT OR edge OR robot OR "autonomous driving") |
| Defenses | (defense OR detection OR mitigation OR "robust aggregation" OR certified) AND any of the scenario terms above |

Selection: 473 records, 45 duplicates removed, 428 screened on title and abstract (67 excluded), 361 assessed for eligibility (12 not eligible), 349 included. Foundational works published before 2019 are cited in the survey but not listed here.

## Contents

- [Data poisoning](#data-poisoning)
- [Attacks on collaborative learning](#attacks-on-collaborative-learning)
- [Model supply chain attacks](#model-supply-chain-attacks)
- [Hardware attacks](#hardware-attacks)
- [Data-level defenses](#data-level-defenses)
- [Training-level defenses](#training-level-defenses)
- [Model-level defenses](#model-level-defenses)
- [Inference-level defenses](#inference-level-defenses)
- [Evaluations, benchmarks, surveys, and standards](#evaluations-benchmarks-surveys-and-standards)

## Data poisoning

### Camera

- [A Depth-Aware Backdoor Attack on LiDAR-Camera Fusion for 3-D Object Detection](https://doi.org/10.1109/access.2026.3749650). Miju Kim et al., IEEE Access, 2026. `DAB · trigger: digital · recorded data`
- [BadDreamer: Transferable Backdoor Attacks against Video World Models for Autonomous Driving](https://arxiv.org/abs/2606.21172). Zhe Shuai et al., preprint (arXiv), 2026. `BadDreamer · trigger: physical · recorded data`
- [BlindDet: Towards Robust Physical-World Backdoor Attack in Low-Light Scenarios Against Object Detection](https://doi.org/10.1109/icassp55912.2026.11464443). Yuxi Li et al., ICASSP 2026, 2026. `BlindDet · trigger: digital, physical · physical trigger`
- [Clean-Label Physical Backdoor Attacks with Data Distillation](https://doi.org/10.1609/aaai.v40i5.37349). Thinh Dao et al., AAAI 2026, 2026. `CLPBA · trigger: physical · physical trigger`
- [FIGhost: Fluorescent Ink-based Stealthy and Flexible Backdoor Attacks on Physical Traffic Sign Recognition](https://doi.org/10.1109/tdsc.2026.3665300). Shuai Yuan et al., IEEE TDSC, 2026. `FIGhost · trigger: physical · physical trigger`
- [When Backdoors Meet Partial Observability: Attacking Real-World Reinforcement Learning](https://arxiv.org/abs/2601.14104). Tairan Huang et al., preprint (arXiv), 2026. `DGBA · trigger: physical · real system`
- [BadDepth: Backdoor Attacks Against Monocular Depth Estimation in the Physical World](https://arxiv.org/abs/2505.16154). Ji Guo et al., preprint (arXiv), 2025. `BadDepth · trigger: digital, physical · physical trigger`
- [BadVLA: Towards Backdoor Attacks on Vision-Language-Action Models via Objective-Decoupled Optimization](https://doi.org/10.52202/085713-4247). Xueyang Zhou et al., NeurIPS 2025, 2025. `BadVLA · trigger: digital · simulation`
- [DropVLA: An Action-Level Backdoor Attack on Vision-Language-Action Models](https://arxiv.org/abs/2510.10932). Zonghuan Xu et al., IROS 2026, 2025. `DropVLA · trigger: digital, physical · real system`
- [Flashy Backdoor: Real-world Environment Backdoor Attack on SNNs with DVS Cameras](https://doi.org/10.1109/ACSAC67867.2025.00081). Roberto Riaño et al., ACSAC 2025, 2025. `Flashy Backdoor · trigger: digital, physical · physical trigger`
- [LaserGuider: A Laser Based Physical Backdoor Attack against Deep Neural Networks](https://doi.org/10.1007/978-3-031-95767-3_13). Yongjie Xu et al., ACNS 2025 (LNCS), 2025. `LaserGuider · trigger: digital, physical · physical trigger`
- [Natural Reflection Backdoor Attack on Vision Language Model for Autonomous Driving](https://arxiv.org/abs/2505.06413). Ming Liu et al., preprint (arXiv), 2025. `Natural Reflection Backdoor · trigger: digital · recorded data`
- [ShrinkBox: Backdoor Attack on Object Detection to Disrupt Collision Avoidance in Machine Learning-based Advanced Driver Assistance Systems](https://doi.org/10.1109/ijcnn64981.2025.11228721). Muhammad Zaeem Shahzad et al., IJCNN 2025, 2025. `ShrinkBox · trigger: digital · recorded data`
- [Stealthy Physical Backdoor Attacks Against Traffic Sign Recognition Systems](https://doi.org/10.1109/icc52391.2025.11161037). Wenbo Jiang et al., IEEE ICC 2025, 2025. `trigger: physical · physical trigger`
- [Temporal Logic-Based Multi-Vehicle Backdoor Attacks against Offline RL Agents in End-to-end Autonomous Driving](https://doi.org/10.52202/085713-2356). Xuan Chen et al., NeurIPS 2025, 2025. `trigger: physical · simulation`
- [Towards Stealthy and Effective Backdoor Attacks on Lane Detection: A Naturalistic Data Poisoning Approach](https://arxiv.org/abs/2508.15778). Yifan Liao et al., CVPR 2026, 2025. `DBALD · trigger: digital, physical · physical trigger`
- [BadFusion: 2D-Oriented Backdoor Attacks against 3D Object Detection](https://doi.org/10.24963/ijcai.2024/39). Saket S. Chaturvedi et al., IJCAI 2024, 2024. `BadFusion · trigger: digital · recorded data`
- [Detector Collapse: Backdooring Object Detection to Catastrophic Overload or Blindness in the Physical World](https://doi.org/10.24963/ijcai.2024/185). Hangtao Zhang et al., IJCAI 2024, 2024. `Detector Collapse · trigger: digital, physical · physical trigger`
- [DiffPhysBA: Diffusion-based Physical Backdoor Attack against Person Re-Identification in Real-World](https://arxiv.org/abs/2405.19990). Wenli Sun et al., preprint (arXiv), 2024. `DiffPhysBA · trigger: digital, physical · physical trigger`
- [PUBA: A Physical Undirected Backdoor Attack in Vision-based UAV Detection and Tracking Systems](https://doi.org/10.1109/ijcnn60899.2024.10650950). Haoyu Jiang et al., IJCNN 2024, 2024. `PUBA · trigger: physical · real system`
- [Physical Backdoor Attack can Jeopardize Driving with Vision-Large-Language Models](https://arxiv.org/abs/2404.12916). Zhenyang Ni et al., preprint (arXiv), 2024. `BadVLMDriver · trigger: physical · physical trigger`
- [Physical Backdoor: Towards Temperature-Based Backdoor Attacks in the Physical World](https://doi.org/10.1109/cvpr52733.2024.01210). Wen Yin et al., CVPR 2024, 2024. `OAA / RAA · trigger: digital, physical · physical trigger`
- [Sneaky Spikes: Uncovering Stealthy Backdoor Attacks in Spiking Neural Networks with Neuromorphic Data](https://doi.org/10.14722/ndss.2024.24334). Gorka Abad et al., NDSS 2024, 2024. `Sneaky Spikes · trigger: digital · recorded data`
- [Towards Physical World Backdoor Attacks against Skeleton Action Recognition](https://doi.org/10.1007/978-3-031-73195-2_13). Zheng et al., ECCV 2024, 2024. `PSBA · trigger: physical · physical trigger`
- [Towards Robust Physical-world Backdoor Attacks on Lane Detection](https://doi.org/10.1145/3664647.3680766). Xinwei Zhang et al., ACM MM 2024, 2024. `BadLANE · trigger: digital, physical · real system`
- [Moiré Backdoor Attack (MBA): A Novel Trigger for Pedestrian Detectors in the Physical World](https://doi.org/10.1145/3581783.3611910). Hui Wei et al., ACM MM 2023, 2023. `MBA · trigger: digital, physical · physical trigger`
- [Physical Invisible Backdoor Based on Camera Imaging](https://doi.org/10.1145/3581783.3612476). Yusheng Guo et al., ACM MM 2023, 2023. `trigger: physical · physical trigger`
- [TransCAB: Transferable Clean-Annotation Backdoor to Object Detection with Natural Trigger in Real-World](https://doi.org/10.1109/srds60354.2023.00018). Hua Ma et al., SRDS 2023, 2023. `TransCAB · trigger: physical · physical trigger`
- [Trojan Triggers for Poisoning Unmanned Aerial Vehicles Navigation: A Deep Learning Approach](https://doi.org/10.1109/csr57506.2023.10224932). Mohammed Mynuddin et al., IEEE CSR 2023, 2023. `trigger: digital · recorded data`
- [Few-Shot Backdoor Attacks on Visual Object Tracking](https://arxiv.org/abs/2201.13178). Yiming Li et al., ICLR 2022, 2022. `FSBA · trigger: digital, physical · physical trigger`
- [Physical Backdoor Attacks to Lane Detection Systems in Autonomous Driving](https://doi.org/10.1145/3503161.3548171). Xingshuo Han et al., ACM MM 2022, 2022. `trigger: physical · real system`
- [Backdoor Attacks Against Deep Learning Systems in the Physical World](https://doi.org/10.1109/cvpr46437.2021.00614). Emily Wenger et al., CVPR 2021, 2021. `trigger: physical · physical trigger`

### Network traffic

- [BDpackets: A Clean-label Backdoor Attack on Network Traffic Classifiers via Feature Fusion](https://doi.org/10.1109/infocom59046.2026.11571249). Zhang et al., IEEE INFOCOM 2026, 2026. `BDpackets · trigger: digital · recorded data`
- [GNN-Guided Selection of Benign-like Anomalies for Backdoor Attacks Against Network Intrusion Detection Systems](https://doi.org/10.3390/electronics15194560). An et al., Electronics, 2026. `trigger: digital · recorded data`
- [MEHGB: Meta-Path Pruned and Explainable Heterogeneous Graph Backdoor for Stealthy NIDS Evasion](https://doi.org/10.1109/ijcnn69854.2026.11728619). Sui et al., IJCNN 2026, 2026. `MEHGB · trigger: digital · recorded data`
- [PCAP-Backdoor: Backdoor Generator in Network Traffic for Intrusion Detection Systems](https://doi.org/10.1145/3805033). Chathoth et al., ACM Transactions on Cyber-Physical Systems, 2026. `PCAP-Backdoor · trigger: digital · recorded data`
- [Restorable Trojan Packet: a practical neural backdoor attack against network traffic classifiers](https://doi.org/10.1007/s44443-026-00780-w). Yuan et al., Journal of King Saud University - Computer and Information Sciences, 2026. `Restorable Trojan Packet · trigger: digital · recorded data`
- [A steganographic backdoor attack scheme on encrypted traffic](https://doi.org/10.1007/s12083-024-01893-7). Rao et al., Peer-to-Peer Networking and Applications, 2025. `trigger: digital · recorded data`
- [Backdoor Adversarial Machine Learning Attack on Graph Convolutional Networks for IoMT Traffic Misclassification](https://doi.org/10.1007/978-3-031-95652-2_16). Georgiades et al., Springer LNNS, 2025. `trigger: digital · recorded data`
- [Backdoor Attack and Defense Methods for AI-Based IoT Intrusion Detection System](https://doi.org/10.1049/ise2/6664900). Ma et al., IET Information Security, 2025. `trigger: digital · recorded data`
- [Clean-Label Backdoor Attack on CNN-Based Network Traffic Classifiers with RhythmicFlow](https://doi.org/10.1109/icoco67189.2025.11334106). Guo et al., IEEE ICOCO 2025, 2025. `RhythmicFlow · trigger: digital · recorded data`
- [Insider Backdoors in Medical IoT Intrusion Detection: Risks and Lightweight Defenses](https://doi.org/10.1109/cins67018.2025.11412108). Alajaji et al., CINS 2025, 2025. `trigger: digital · recorded data`
- [Poisoning Network Flow Classifiers](https://doi.org/10.1145/3627106.3627123). Severi et al., ACSAC 2023, 2023. `trigger: digital · recorded data`
- [Backdoor Poisoning of Encrypted Traffic Classifiers](https://doi.org/10.1109/icdmw58026.2022.00080). Holodnak et al., IEEE ICDM Workshops 2022, 2022. `trigger: digital · recorded data`
- [Triggerability of Backdoor Attacks in Multi-Source Transfer Learning-based Intrusion Detection](https://doi.org/10.1109/bdcat56447.2022.00013). Alhussien et al., IEEE/ACM BDCAT 2022, 2022. `trigger: digital · recorded data`
- [TrojanFlow: A Neural Backdoor Attack to Deep Learning-based Network Traffic Classifiers](https://doi.org/10.1109/infocom48880.2022.9796878). Ning et al., IEEE INFOCOM 2022, 2022. `TrojanFlow · trigger: digital · recorded data`
- [VulnerGAN: a backdoor attack through vulnerability amplification against machine learning-based network intrusion detection systems](https://doi.org/10.1007/s11432-021-3455-1). Liu et al., Science China Information Sciences, 2022. `VulnerGAN · trigger: digital · recorded data`
- [Walling up Backdoors in Intrusion Detection Systems](https://doi.org/10.1145/3359992.3366638). Bachl et al., Big-DAMA '19 (ACM CoNEXT Workshop), 2019. `trigger: digital · recorded data`

### Other

- [MOBA: A Material-Oriented Backdoor Attack against LiDAR-based 3D Object Detection Systems](https://doi.org/10.1609/aaai.v40i42.40842). Saket S. Chaturvedi et al., AAAI 2026, 2026. `MOBA · trigger: digital, physical · physical trigger`
- [PointDetBA: Backdoor Attacks Against 3D Object Detection in Autonomous Driving](https://doi.org/10.1109/ijcnn69854.2026.11729176). Lei Zhang et al., IJCNN 2026, 2026. `PointDetBA · trigger: digital · recorded data`
- [State Backdoor: Towards Stealthy Real-world Poisoning Attack on Vision-Language-Action Model in State Space](https://arxiv.org/abs/2601.04266). Ji Guo et al., preprint (arXiv), 2026. `State Backdoor · trigger: physical · real system`
- [StepTrigger: Contact-State-Triggered Backdoor Attacks on VLM-Powered Legged Robots](https://arxiv.org/abs/2609.26131). Jiageng Zhang et al., preprint (arXiv), 2026. `StepTrigger · trigger: physical · simulation`
- [Towards Dynamic Backdoor Attacks against LiDAR Semantic Segmentation in Autonomous Driving](https://doi.org/10.1109/trustcom60117.2023.00034). Shuai Li et al., IEEE TrustCom 2023, 2023. `BadLiSeg · trigger: digital · recorded data`

### RF and wireless sensing

- [A Channel-Triggered Backdoor Attack on Wireless Semantic Image Reconstruction](https://doi.org/10.1109/tmc.2026.3676425). Wan et al., IEEE TMC, 2026. `CT-BA · trigger: natural, physical · recorded data`
- [BadAMC: A Model-Agnostic Digital Backdoor Attack for Automatic Modulation Classification in Crowdsourced Platforms](https://doi.org/10.1109/ton.2026.3688147). Ahmadi et al., IEEE Transactions on Networking, 2026. `BadAMC · trigger: digital · recorded data`
- [On the Vulnerability of Deep Automatic Modulation Classifiers to Explainable Backdoor Threats](https://arxiv.org/abs/2603.25310). Salmi et al., arXiv, 2026. `XAI-guided backdoor attack · trigger: digital · simulation`
- [Over-the-Air Backdoor Injection in Deep Learning-Based Semantic Communication Systems](https://doi.org/10.1109/icccn69946.2026.11662945). Zhou et al., ICCCN 2026, 2026. `OABI · trigger: physical · simulation`
- [Position-Robust Backdoor Threats Against Domain-Generalized Specific Emitter Identification](https://doi.org/10.1109/ccai69603.2026.11642040). Gan et al., CCAI 2026, 2026. `trigger: digital · recorded data`
- [Wireless Backdoor Attack and Defense for Semantic Communications over Multiple Access Channel](https://arxiv.org/abs/2606.30595). Sagduyu et al., arXiv, 2026. `Selective over-the-air backdoor attack · trigger: physical · recorded data`
- [A Multitarget Backdoor Attack Against Automatic Modulation Recognition for IoT Wireless Signals](https://doi.org/10.1109/jiot.2025.3563204). Gan et al., IEEE Internet of Things Journal, 2025. `SMBA · trigger: digital · recorded data`
- [Explanation-Guided Backdoor Attacks Against Model-Agnostic RF Fingerprinting Systems](https://doi.org/10.1109/tmc.2024.3487967). Zhao et al., IEEE TMC, 2025. `trigger: digital · recorded data`
- [On the Invisible Backdoor Attacks on Peer-to-Peer Semantic Vehicular Networks](https://doi.org/10.1049/ell2.70431). Yuanhang He et al., Electronics Letters, 2025. `IBPS · trigger: digital · simulation`
- [Physical Backdoor Attack Against Deep Learning-Based Modulation Classification](https://doi.org/10.1109/meditcom64437.2025.11104329). Salmi et al., IEEE MeditCom 2025, 2025. `Physical backdoor attack · trigger: physical · simulation`
- [Physical Backdoor Attacks against mmWave-based Human Activity Recognition](https://doi.org/10.1109/icdcs63083.2025.00079). Bi et al., IEEE ICDCS 2025, 2025. `trigger: physical · physical trigger`
- [SFDT: A Signal Frequency-Domain Backdoor Attack With Sample-Specific Trigger Against Automatic Modulation Recognition](https://doi.org/10.1109/lwc.2025.3586799). Gan et al., IEEE Wireless Communications Letters, 2025. `SFDT · trigger: digital · recorded data`
- [Spatially Distributed Multi-Target Backdoor Attacks Against Automatic Modulation Recognition](https://doi.org/10.1109/ccai65422.2025.11189478). Gan et al., CCAI 2025, 2025. `trigger: digital · simulation`
- [Stealthy Backdoor Attack Using Frequency-Phase Trigger Injection Against Automatic Modulation Classification](https://doi.org/10.1109/ucom67224.2025.11336936). Li et al., Ucom 2025, 2025. `FPTI · trigger: digital · simulation`
- [Backdoor Attacks Against Low-Earth Orbit Satellite Fingerprinting](https://doi.org/10.1109/infocomwkshps61880.2024.10620841). Zhao et al., IEEE INFOCOM Workshops 2024, 2024. `trigger: digital · recorded data`
- [CSBA: Covert Semantic Backdoor Attack Against Intelligent Connected Vehicles](https://doi.org/10.1109/tvt.2024.3427713). Xiaodong Xu et al., IEEE TVT, 2024. `CSBA · trigger: natural · simulation`
- [Input Agnostic Trojan Attack for Deep Learning-Based Wireless Signal Classification](https://doi.org/10.1109/ncc60321.2024.10485792). Vavilapalli et al., NCC 2024, 2024. `trigger: digital · simulation`
- [RF Domain Backdoor Attack on Signal Classification via Stealthy Trigger](https://doi.org/10.1109/tmc.2024.3404341). Tang et al., IEEE TMC, 2024. `trigger: digital · recorded data`
- [Wavelet Domain Frequency Steganography Backdoor Attack for Misleading Automatic Modulation Classification](https://doi.org/10.1109/jiot.2024.3454668). Zhang et al., IEEE Internet of Things Journal, 2024. `WDFS · trigger: digital · recorded data`
- [Backdoor Attacks Against Deep Learning-Based Massive MIMO Localization](https://doi.org/10.1109/globecom54140.2023.10437534). Zhao et al., IEEE GLOBECOM 2023, 2023. `trigger: digital · simulation`
- [Hidden Backdoor Attack Against Deep Learning-Based Wireless Signal Modulation Classifiers](https://doi.org/10.1109/tvt.2023.3267455). Huang et al., IEEE TVT, 2023. `Hidden backdoor attack · trigger: digital · simulation`
- [Random Location Poisoning Backdoor Attack Against Automatic Modulation Classification in Wireless Networks](https://doi.org/10.1109/iccc57788.2023.10233544). Li et al., IEEE/CIC ICCC 2023, 2023. `trigger: digital · simulation`
- [Vulnerabilities of Deep Learning-Driven Semantic Communications to Backdoor (Trojan) Attacks](https://doi.org/10.1109/ciss56502.2023.10089692). Sagduyu et al., CISS 2023, 2023. `trigger: digital · recorded data`
- [Trojan Attacks on Wireless Signal Classification with Adversarial Machine Learning](https://doi.org/10.1109/dyspan.2019.8935782). Davaslioglu et al., IEEE DySPAN 2019, 2019. `trigger: digital · simulation`

### Voice and audio

- [Acoustic backdoor attacks on speech recognition via frequency offset perturbation](https://doi.org/10.1016/j.asoc.2025.113188). Tang et al., Applied Soft Computing, 2025. `trigger: digital · recorded data`
- [CBA: Backdoor Attack on Deep Speech Classification via Audio Compression](https://doi.org/10.21437/interspeech.2025-372). Huang et al., Interspeech 2025, 2025. `CBA · trigger: digital · recorded data`
- [CuckooAttack: Towards Practical Backdoor Attack against Automatic Speech Recognition Systems](https://doi.org/10.1109/tdsc.2025.3548611). Li et al., IEEE TDSC, 2025. `CuckooAttack · trigger: digital, physical · real system`
- [Hidden in the Noise: Unveiling Backdoors in Audio LLMs Alignment through Latent Acoustic Pattern Triggers](https://arxiv.org/abs/2508.02175). Lin et al., arXiv, 2025. `HIN · trigger: digital · simulation`
- [Multi-Target Backdoor Attacks Against Speaker Recognition](https://arxiv.org/abs/2508.08559). Fortier et al., IEEE ASRU 2025, 2025. `trigger: digital · recorded data`
- [SPBA: Utilizing Speech Large Language Model for Backdoor Attacks on Speech Classification Models](https://arxiv.org/abs/2506.08346). Yao et al., IJCNN 2025, 2025. `SPBA · trigger: digital · recorded data`
- [Devil in the Room: Triggering Audio Backdoors in the Physical World](https://www.usenix.org/conference/usenixsecurity24/presentation/chen-meng). Chen et al., USENIX Security 2024, 2024. `TrojanRoom · trigger: natural · real system`
- [EmoAttack: Utilizing Emotional Voice Conversion for Speech Backdoor Attacks on Deep Speech Classification Models](https://arxiv.org/abs/2408.15508). Yao et al., arXiv, 2024. `EmoAttack · trigger: digital · recorded data`
- [Enrollment-stage Backdoor Attacks on Speaker Recognition Systems via Adversarial Ultrasound](https://doi.org/10.1109/jiot.2023.3328253). Li et al., IEEE Internet of Things Journal, 2024. `TUNER · trigger: physical · real system`
- [FlowMur: A Stealthy and Practical Audio Backdoor Attack with Limited Knowledge](https://doi.org/10.1109/sp54263.2024.00148). Lan et al., IEEE S&P 2024, 2024. `FlowMur · trigger: digital, physical · real system`
- [Hidden in Plain Sound: Environmental Backdoor Poisoning Attacks on Whisper, and Mitigations](https://arxiv.org/abs/2409.12553). Bartolini et al., arXiv, 2024. `trigger: digital · recorded data`
- [Inaudible Backdoor Attack via Stealthy Frequency Trigger Injection in Audio Spectrogram](https://doi.org/10.1145/3636534.3649345). Zhang et al., ACM MobiCom 2024, 2024. `trigger: digital, physical · real system`
- [Toward Stealthy Backdoor Attacks Against Speech Recognition via Elements of Sound](https://doi.org/10.1109/tifs.2024.3404885). Cai et al., IEEE TIFS, 2024. `PBSM;VSVC · trigger: digital, physical · real system`
- [Fake the Real: Backdoor Attack on Deep Speech Classification via Voice Conversion](https://doi.org/10.21437/interspeech.2023-733). Ye et al., INTERSPEECH 2023, 2023. `trigger: digital · recorded data`
- [Going In Style: Audio Backdoors Through Stylistic Transformations](https://doi.org/10.1109/icassp49357.2023.10096332). Koffas et al., ICASSP 2023, 2023. `JingleBack · trigger: digital · recorded data`
- [MASTERKEY: Practical Backdoor Attack Against Speaker Verification Systems](https://doi.org/10.1145/3570361.3613261). Guo et al., ACM MobiCom 2023, 2023. `MasterKey · trigger: digital, physical · real system`
- [Stealthy Backdoor Attack Against Speaker Recognition Using Phase-Injection Hidden Trigger](https://doi.org/10.1109/lsp.2023.3293429). Ye et al., IEEE Signal Processing Letters, 2023. `PhaseBack · trigger: digital · recorded data`
- [The Silent Manipulator: A Practical and Inaudible Backdoor Attack against Speech Recognition Systems](https://doi.org/10.1145/3581783.3613843). Zheng et al., ACM MM 2023, 2023. `SMA · trigger: physical · real system`
- [Audio-domain Position-independent Backdoor Attack via Unnoticeable Triggers](https://doi.org/10.1145/3495243.3560531). Shi et al., ACM MobiCom 2022, 2022. `trigger: digital, physical · real system`
- [Opportunistic Backdoor Attacks: Exploring Human-imperceptible Vulnerabilities on Speech Recognition Systems](https://doi.org/10.1145/3503161.3548261). Liu et al., ACM MM 2022, 2022. `DABA · trigger: natural · physical trigger`
- [PBSM: Backdoor attack against Keyword spotting based on pitch boosting and sound masking](https://arxiv.org/abs/2211.08697). Cai et al., arXiv, 2022. `PBSM · trigger: digital · recorded data`
- [UltraBD: Backdoor Attack against Automatic Speaker Verification Systems via Adversarial Ultrasound](https://doi.org/10.1109/icpads56603.2022.00033). Ze et al., IEEE ICPADS 2022, 2022. `UltraBD · trigger: physical · real system`
- [VSVC: Backdoor attack against Keyword Spotting based on Voiceprint Selection and Voice Conversion](https://arxiv.org/abs/2212.10103). Cai et al., arXiv, 2022. `VSVC · trigger: digital · recorded data`
- [Backdoor Attack against Speaker Verification](https://doi.org/10.1109/icassp39728.2021.9413468). Zhai et al., ICASSP 2021, 2021. `trigger: digital · recorded data`
- [Can You Hear It? Backdoor Attacks via Ultrasonic Triggers](https://arxiv.org/abs/2107.14569). Koffas et al., arXiv, 2021. `trigger: digital, physical · real system`

### Wearable and time series

- [Backdoor Attacks on Fault Detection and Localization in Cyber-Physical Systems](https://arxiv.org/abs/2605.27674). Jean et al., arXiv, 2026. `trigger: digital · simulation`
- [CLIP-guided Diffusion Model for Backdoor Generation in Sensor-based Human Activity Recognition](https://arxiv.org/abs/2606.22837). Briston et al., arXiv, 2026. `IMU-DM-CLIP · trigger: digital · recorded data`
- [Synchronization-Free Backdoor Attacks on Edge-Deployed Neural Network for IoT Systems](https://doi.org/10.1109/tc.2026.3699817). Bing Zhang et al., IEEE TC, 2026. `trigger: digital · recorded data`
- [Revisiting Backdoor Attacks on Time Series Classification in the Frequency Domain](https://doi.org/10.1145/3696410.3714827). Huang et al., WWW 2025, 2025. `FreqBack · trigger: digital · recorded data`
- [Spatialspectral-Backdoor: Realizing backdoor attack for deep neural networks in brain-computer interface via EEG characteristics](https://doi.org/10.1016/j.neucom.2024.128902). Li et al., Neurocomputing, 2025. `Spatialspectral-Backdoor · trigger: digital · recorded data`
- [Adversarial filtering based evasion and backdoor attacks to EEG-based brain-computer interfaces](https://doi.org/10.1016/j.inffus.2024.102316). Meng et al., Information Fusion, 2024. `trigger: digital · recorded data`
- [BackTime: Backdoor Attacks on Multivariate Time Series Forecasting](https://doi.org/10.52202/079017-4174). Lin et al., NeurIPS 2024, 2024. `BackTime · trigger: digital · recorded data`
- [Dynamic Black-box Backdoor Attacks on IoT Sensory Data](https://doi.org/10.1109/tps-isa62245.2024.00030). Chathoth et al., IEEE TPS-ISA 2024, 2024. `trigger: digital · recorded data`
- [Position-Independent and Stealthy Backdoor Attack of IMU Systems](https://doi.org/10.1109/globecom52923.2024.10901755). Chen et al., IEEE GLOBECOM 2024, 2024. `trigger: digital · recorded data`
- [Professor X: Manipulating EEG BCI with Invisible and Robust Backdoor Attack](https://arxiv.org/abs/2409.20158). Liu et al., arXiv, 2024. `Professor X · trigger: digital · recorded data`
- [Repetitive Backdoor Attacks and Countermeasures for Smart Grid Reinforcement Incremental Learning](https://doi.org/10.1109/jiot.2024.3476458). El-Toukhy et al., IEEE Internet of Things Journal, 2024. `trigger: digital · recorded data`
- [Backdoor Attacks on Time Series: A Generative Approach](https://doi.org/10.1109/satml54575.2023.00034). Jiang et al., IEEE SaTML 2023, 2023. `TSBA · trigger: digital · recorded data`
- [EEG-Based Brain-Computer Interfaces Are Vulnerable to Backdoor Attacks](https://doi.org/10.1109/tnsre.2023.3273214). Meng et al., IEEE TNSRE, 2023. `NPP backdoor · trigger: digital · recorded data`
- [Towards Backdoor Attack on Deep Learning based Time Series Classification](https://doi.org/10.1109/icde53745.2022.00100). Ding et al., ICDE 2022, 2022. `TimeTrojan · trigger: digital · recorded data`

## Attacks on collaborative learning

### Decentralized learning

- [Targeted Attacks and Defenses for Distributed Federated Learning in Vehicular Networks](https://arxiv.org/abs/2510.15109). Demir et al., arXiv, 2025. `trigger: digital · simulation`

### Federated learning

- [Applying Patch-Based Backdoor Attacks to In-Orbit Federated Learning for Satellite Constellations](https://doi.org/10.1109/aero66936.2026.11519919). Rahmanian et al., IEEE Aerospace Conference 2026, 2026. `trigger: digital · recorded data`
- [Context-Aware Dynamic-Trigger Backdoor Attack in Federated Industrial Intrusion Detection Systems](https://doi.org/10.1109/tii.2026.3712476). Bhutta et al., IEEE TII, 2026. `CDB · trigger: digital · recorded data`
- [Exploiting Layer-Specific Vulnerabilities to Backdoor Attack in Federated Learning](https://arxiv.org/abs/2602.15161). Foroughi et al., IEEE ICC 2026, 2026. `Layer Smoothing Attack · trigger: digital · recorded data`
- [STAIN-FL: Stealthy Targeted Attack Injection with Contextual Triggers in Federated Learning](https://arxiv.org/abs/2608.23952). arXiv, 2026. `STAIN-FL · trigger: natural · physical trigger`
- [BadHAR: Backdoor Attacks in Federated Human Activity Recognition Systems](https://doi.org/10.1007/978-981-96-1148-5_1). Dongping Zhang et al., Springer LNCS, 2025. `BadHAR · trigger: digital · recorded data`
- [LBKD: Rethinking Federated Backdoors for Low-Altitude Economy via LLMs and Bidirectional Knowledge Distillation](https://doi.org/10.1109/tnse.2025.3626056). Wang et al., IEEE Transactions on Network Science and Engineering, 2025. `LBKD · trigger: digital · recorded data`
- [On the Out-of-Distribution Backdoor Attack for Federated Learning](https://arxiv.org/abs/2509.13219). Xu et al., MobiHoc 2025, 2025. `OBA / SoDa · trigger: natural · recorded data`
- [Spikewhisper: Temporal Spike Backdoor Attacks on Federated Neuromorphic Learning over Low-power Devices](https://doi.org/10.1007/978-981-96-7005-5_17). Fu et al., Springer CCIS, 2025. `Spikewhisper · trigger: digital · recorded data`
- [Act in Collusion: Distributed Multi-Target Backdoor Attacks in Federated Learning](https://arxiv.org/abs/2411.03926). Liu et al., arXiv, 2024. `DMBA · trigger: digital · recorded data`
- [Backdoor Attack and Defense in Asynchronous Federated Learning for Multiple Unmanned Vehicles](https://doi.org/10.1109/fasta61401.2024.10595233). Wang et al., FASTA 2024, 2024. `OAMU · trigger: digital · simulation`
- [Collusive Backdoor Attacks in Federated Learning Frameworks for IoT Systems](https://doi.org/10.1109/jiot.2024.3368754). Alharbi et al., IEEE Internet of Things Journal, 2024. `CBA · trigger: digital · recorded data`
- [Covert and Persistent Backdoor Attacks in Federated Learning-Powerd Autonomous Driving](https://doi.org/10.1109/hpcc64274.2024.00114). Wang et al., IEEE HPCC/SmartCity/DSS 2024, 2024. `CPBA · trigger: digital · recorded data`
- [Lurking in the shadows: Unveiling Stealthy Backdoor Attacks against Personalized Federated Learning](https://arxiv.org/abs/2406.06207). Lyu et al., USENIX Security 2024, 2024. `PFedBA · trigger: digital · recorded data`
- [Poisoning Attacks on Federated Learning for Autonomous Driving](https://doi.org/10.3384/ecp208002). Garg et al., SCAI 2024, 2024. `Off-Track Attack · trigger: digital, physical · physical trigger`
- [Backdoor attack and defense in federated generative adversarial network-based medical image synthesis](https://doi.org/10.1016/j.media.2023.102965). Ruinan Jin et al., Medical Image Analysis, 2023. `FedDetect · trigger: digital · recorded data`
- [Facilitating Early-Stage Backdoor Attacks in Federated Learning With Whole Population Distribution Inference](https://doi.org/10.1109/jiot.2023.3237806). Liu et al., IEEE Internet of Things Journal, 2023. `trigger: digital · recorded data`
- [Genetic Algorithm-Based Dynamic Backdoor Attack on Federated Learning-Based Network Traffic Classification](https://doi.org/10.1109/fmec59375.2023.10306137). Nazzal et al., FMEC 2023, 2023. `GABAttack · trigger: digital · recorded data`
- [Parameterizing poisoning attacks in federated learning-based intrusion detection](https://doi.org/10.1145/3600160.3605090). Merzouk et al., ARES 2023, 2023. `trigger: digital · recorded data`
- [Clean-label poisoning attacks on federated learning for IoT](https://doi.org/10.1111/exsy.13161). Yang et al., Expert Systems, 2022. `trigger: digital · simulation`
- [SBPA: Sybil-Based Backdoor Poisoning Attacks for Distributed Big Data in AIoT-Based Federated Learning System](https://doi.org/10.1109/tbdata.2022.3224392). Xiao et al., IEEE Transactions on Big Data, 2022. `SBPA · trigger: digital · recorded data`
- [On the Neural Backdoor of Federated Generative Models in Edge Computing](https://doi.org/10.1145/3425662). Wang et al., ACM Transactions on Internet Technology, 2021. `trigger: digital · simulation`
- [PoisonGAN: Generative Poisoning Attacks Against Federated Learning in Edge Computing Systems](https://doi.org/10.1109/jiot.2020.3023126). Zhang et al., IEEE Internet of Things Journal, 2021. `PoisonGAN · trigger: natural · recorded data`
- [Poisoning Attacks on Federated Learning-based IoT Intrusion Detection System](https://doi.org/10.14722/diss.2020.23003). Nguyen et al., NDSS Workshop DISS 2020, 2020. `trigger: digital · recorded data`

### Split and vertical learning

- [Backspin: A backdoor attack framework for split learning based on smashed data](https://doi.org/10.1016/j.neunet.2026.109402). Hu et al., Neural Networks, 2026. `Backspin · trigger: digital · recorded data`
- [FeSBA: A Feature-Level Shadow-Aligned Backdoor Attack Against Split Learning in Edge-IoT Systems](https://doi.org/10.1109/jiot.2026.3731378). Wu et al., IEEE Internet of Things Journal, 2026. `FeSBA · trigger: digital · recorded data`
- [HBA: Hijacking-Based Backdoor Attack for Vertical Federated Learning](https://doi.org/10.1109/jiot.2026.3702700). Zhang et al., IEEE Internet of Things Journal, 2026. `HBA · trigger: digital · recorded data`
- [SFI: A Practical and Efficient Backdoor Attack Framework Against Split Learning](https://doi.org/10.1109/tdsc.2026.3654766). Yu et al., IEEE TDSC, 2026. `SFI · trigger: digital · recorded data`
- [Snail: Scheduler-Driven Backdoor Injection in Split Federated Learning via Gradual Perturbation](https://doi.org/10.1109/cns69863.2026.11720909). Jiang et al., IEEE CNS 2026, 2026. `Snail · trigger: digital · recorded data`
- [Cooperative Decentralized Backdoor Attacks on Vertical Federated Learning](https://doi.org/10.1109/ton.2025.3636809). Lee et al., IEEE Transactions on Networking, 2025. `trigger: digital · recorded data`
- [IBAS: Imperceptible Backdoor Attacks in Split Learning with Limited Information](https://doi.org/10.1609/aaai.v39i26.34986). Peng et al., AAAI 2025, 2025. `IBAS · trigger: digital · recorded data`
- [BadVFL: Backdoor Attacks in Vertical Federated Learning](https://doi.org/10.1109/sp54263.2024.00008). Naseri et al., IEEE S&P 2024, 2024. `BadVFL · trigger: digital · recorded data`
- [Dullahan: Stealthy Backdoor Attack against Without-Label-Sharing Split Learning](https://arxiv.org/abs/2405.12751). Pu et al., arXiv, 2024. `Dullahan · trigger: digital · recorded data`
- [Backdoor Attack Against Split Neural Network-Based Vertical Federated Learning](https://doi.org/10.1109/tifs.2023.3327853). He et al., IEEE TIFS, 2023. `trigger: digital · recorded data`
- [How to backdoor split learning](https://doi.org/10.1016/j.neunet.2023.09.037). Yu et al., Neural Networks, 2023. `trigger: digital · recorded data`
- [On Feasibility of Server-side Backdoor Attacks on Split Learning](https://doi.org/10.1109/spw59333.2023.00014). Tajalli et al., IEEE S&P Workshops 2023, 2023. `trigger: digital · recorded data`
- [Universal adversarial backdoor attacks to fool vertical federated learning](https://doi.org/10.1016/j.cose.2023.103601). Chen et al., Computers & Security, 2023. `UAB · trigger: digital · recorded data`
- [VILLAIN: Backdoor Attacks Against Vertical Split Learning](https://www.usenix.org/conference/usenixsecurity23/presentation/bai). Bai et al., USENIX Security 2023, 2023. `VILLAIN · trigger: digital · recorded data`

### Unlearning and continual updates

- [Backdoor Attacks on Contrastive Continual Learning for IoT Systems](https://arxiv.org/abs/2602.13062). Tim et al., arXiv, 2026. `trigger: digital`
- [Continual Backdoor Training in IoT/CPS](https://arxiv.org/abs/2606.14987). Salish et al., arXiv, 2026. `trigger: digital · recorded data`
- [Exploiting the Recovery Trap of Federated Unlearning for Latent and Persistent Backdoors in Edge Systems](https://doi.org/10.1109/tce.2026.3735776). Chen et al., IEEE Transactions on Consumer Electronics, 2026. `LURA · trigger: digital · recorded data`

## Model supply chain attacks

### Compression-activated

- [Mask2Keep: Mask-guided information transfer for backdoors resilient to compression-oriented pruning](https://doi.org/10.1016/j.neunet.2026.109463). Jing Shang et al., Neural Networks, 2027. `Mask2Keep · trigger: digital · recorded data`
- [AGENTQ: Quantization-Conditioned Backdoor Attacks on LLM Agents](https://doi.org/10.18653/2026.emnlp-main.1566). Xiaoqun Liu et al., EMNLP 2026, 2026. `AGENTQ · trigger: digital, processing or fault · recorded data`
- [Rounding-Guided Backdoor Injection in Deep Learning Model Quantization](https://doi.org/10.14722/ndss.2026.230113). Xiangxiang Chen et al., NDSS 2026, 2026. `QURA · trigger: digital, processing or fault · recorded data`
- [Your Compiler is Backdooring Your Model: Understanding and Exploiting Compilation Inconsistency Vulnerabilities in Deep Learning Compilers](https://doi.org/10.1109/SP63933.2026.00097). Simin Chen et al., IEEE S&P 2026, 2026. `DcL-BD · trigger: digital, processing or fault · recorded data`
- [Mind the Gap: A Practical Attack on GGUF Quantization](https://arxiv.org/abs/2505.23786). Kazuki Egashira et al., ICML 2025, 2025. `Error-based interval estimation · trigger: processing or fault · recorded data`
- [Silent Until Sparse: Backdoor Attacks on Semi-Structured Sparsity](https://arxiv.org/abs/2509.08747). Wei Guo et al., arXiv preprint, 2025. `Silent Until Sparse · trigger: digital, processing or fault · recorded data`
- [Taught Well Learned Ill: Towards Distillation-conditional Backdoor Attack](https://doi.org/10.52202/085713-5240). Yukun Chen et al., NeurIPS 2025, 2025. `SCAR · trigger: digital, processing or fault · recorded data`
- [Exploiting LLM Quantization](https://doi.org/10.52202/079017-1319). Kazuki Egashira et al., NeurIPS 2024, 2024. `LLM quantization exploit · trigger: processing or fault · recorded data`
- [ImpNet: Imperceptible and blackbox-undetectable backdoors in compiled neural networks](https://doi.org/10.1109/SaTML59370.2024.00024). Eleanor Clifford et al., IEEE SaTML 2024, 2024. `ImpNet · trigger: digital · recorded data`
- [Mind Your Heart: Stealthy Backdoor Attack on Dynamic Deep Neural Network in Edge Computing](https://doi.org/10.1109/infocom53939.2023.10229092). Tian Dong et al., IEEE INFOCOM 2023, 2023. `trigger: digital, processing or fault · recorded data`
- [Quantization Backdoors to Deep Learning Commercial Frameworks](https://doi.org/10.1109/tdsc.2023.3271956). Hua Ma et al., IEEE TDSC, 2023. `PQ backdoor · trigger: digital, processing or fault · recorded data`
- [RIBAC: Towards Robust and Imperceptible Backdoor Attack against Compact DNN](https://doi.org/10.1007/978-3-031-19772-7_41). Huy Phan et al., ECCV 2022 (LNCS), 2022. `RIBAC · trigger: digital · recorded data`
- [Stealthy Backdoors as Compression Artifacts](https://doi.org/10.1109/TIFS.2022.3160359). Yulong Tian et al., IEEE TIFS, 2022. `Compression-artifact backdoor · trigger: digital, processing or fault · recorded data`
- [Qu-ANTI-zation: Exploiting Quantization Artifacts for Achieving Adversarial Outcomes](https://arxiv.org/abs/2110.13541). Sanghyun Hong et al., NeurIPS 2021, 2021. `Qu-ANTI-zation · trigger: digital, processing or fault · recorded data`
- [Understanding the Threats of Trojaned Quantized Neural Network in Model Supply Chains](https://doi.org/10.1145/3485832.3485881). Xudong Pan et al., ACSAC 2021, 2021. `QUASI · trigger: digital, processing or fault · recorded data`

### Pre-trained and foundation models

- [BEAT: Visual Backdoor Attacks on VLM-based Embodied Agents via Contrastive Trigger Learning](https://arxiv.org/abs/2510.27623). Qiusi Zhan et al., ICLR 2026, 2026. `BEAT · trigger: physical · simulation`
- [Backdooring Acoustic Foundation Models for Physically Realizable Triggers](https://doi.org/10.1007/978-3-032-42939-1_15). Zebin Yun et al., RAID 2026 (LNCS), 2026. `FAB · trigger: physical · real system`
- [Data-free Backdoor Attacks on Pre-trained Human Activity Sensing Models in IoT Systems](https://doi.org/10.1109/tmc.2026.3745275). Zhao et al., IEEE TMC, 2026. `Data-free PTM backdoor · trigger: digital · recorded data`
- [Delayed Backdoor: Let the Trigger Fly for a While in Backdoor Attack on Internet of Things](https://doi.org/10.1109/jiot.2026.3686078). Bo Liu et al., IEEE IoT-J, 2026. `Delayed Backdoor · trigger: digital · recorded data`
- [From Prompt to Physical Action: Structured Backdoor Attacks on LLM-Mediated Robotic Control Systems](https://arxiv.org/abs/2604.03890). Mingyang Xie et al., preprint (arXiv), 2026. `trigger: digital · real system`
- [Hardware-Triggered Backdoors](https://arxiv.org/abs/2601.21902). Jonas Möller et al., arXiv preprint, 2026. `Hardware-Triggered Backdoors · trigger: natural, processing or fault · real system`
- [Over-the-Air Backdoor Threats Against Pre-Trained Models for Automatic Modulation Recognition](https://doi.org/10.1109/tccn.2026.3692196). Gan et al., IEEE TCCN, 2026. `CDBA · trigger: digital, physical · real system`
- [TrojanEdge: Mutual Information-Enhanced Robust and Persistent Backdoor Attacks for Edge and On-Device Deployments](https://doi.org/10.1109/infocom59046.2026.11571574). Zemin Chen et al., IEEE INFOCOM 2026, 2026. `TrojanEdge · trigger: digital · recorded data`
- [Unveiling the Threat: Data-Free Backdoor Attacks on Pre-Trained Models for RF Fingerprinting](https://doi.org/10.1109/tmc.2025.3628527). Zhao et al., IEEE TMC, 2026. `Protocol-agnostic data-free PTM backdoor · trigger: digital · recorded data`
- [Watch Out Your Industrial Copilots: Stealthy Backdoor Attack Against LLM-Based PLC Code Generation](https://doi.org/10.18653/v1/2026.findings-acl.609). Xinyuan An et al., Findings of ACL 2026, 2026. `STBack · trigger: digital · recorded data`
- [Backdoor Attacks on Large Language Model Based Semantic Communication Systems](https://doi.org/10.1109/iccworkshops67674.2025.11162215). Duc Trong Minh Hoang et al., IEEE ICC Workshops 2025, 2025. `trigger: digital · simulation`
- [Can We Trust Embodied Agents? Exploring Backdoor Attacks against Embodied LLM-based Decision-Making Systems](https://arxiv.org/abs/2405.20774). Ruochen Jiao et al., ICLR 2025, 2025. `BALD · trigger: digital, physical · simulation`
- [Hidden Ghost Hand: Unveiling Backdoor Vulnerabilities in MLLM-Powered Mobile GUI Agents](https://doi.org/10.18653/v1/2025.findings-emnlp.411). Pengzhou Cheng et al., Findings of EMNLP 2025, 2025. `AgentGhost · trigger: digital · recorded data`
- [Protocol-agnostic and Data-free Backdoor Attacks on Pre-trained Models in RF Fingerprinting](https://doi.org/10.1109/infocom55648.2025.11044704). Tianya Zhao et al., IEEE INFOCOM 2025, 2025. `trigger: digital · recorded data`
- [Compromising Embodied Agents with Contextual Backdoor Attacks](https://arxiv.org/abs/2408.02882). Aishan Liu et al., preprint (arXiv), 2024. `Contextual Backdoor Attack · trigger: digital, physical · real system`
- [Robot Collapse: Supply Chain Backdoor Attacks Against VLM-based Robotic Manipulation](https://arxiv.org/abs/2411.11683). Xianlong Wang et al., preprint (arXiv), 2024. `TrojanRobot · trigger: physical · real system`
- [Architectural Backdoors in Neural Networks](https://doi.org/10.1109/CVPR52729.2023.02356). Mikel Bober-Irizar et al., CVPR 2023, 2023. `MAB · trigger: digital · recorded data`
- [Anti-Distillation Backdoor Attacks: Backdoors Can Really Survive in Knowledge Distillation](https://doi.org/10.1145/3474085.3475254). Yunjie Ge et al., ACM MM 2021, 2021. `ADBA · trigger: digital · recorded data`

### Tampering after training

- [A Novel and Efficient Multi-Target Backdoor Attack for Deep Learning-Based Wireless Signal Classifiers](https://doi.org/10.1109/access.2025.3558276). Baishya et al., IEEE Access, 2025. `BackdoorNet · trigger: digital · simulation`
- [ShadowLogic: Backdoors in Any Whitebox LLM](https://arxiv.org/abs/2511.00664). Kasimir Schulz et al., CAMLIS 2025 (PMLR 299), 2025. `ShadowLogic · trigger: digital · recorded data`
- [Stealthy Backdoor Attack to Real-world Models in Android Apps](https://arxiv.org/abs/2501.01263). Jiali Wei et al., arXiv preprint, 2025. `BARWM · trigger: digital · recorded data`
- [TrojanTime: Backdoor Attacks on Time Series Classification](https://doi.org/10.1007/978-981-96-8183-9_13). Dong et al., Springer LNCS 2025, 2025. `TrojanTime · trigger: digital · recorded data`
- [TrojanModel: A Practical Trojan Attack against Automatic Speech Recognition Systems](https://doi.org/10.1109/sp46215.2023.10179331). Zong et al., IEEE S&P 2023, 2023. `TrojanModel · trigger: digital, physical · real system`
- [Towards Practical Deployment-Stage Backdoor Attack on Deep Neural Networks](https://doi.org/10.1109/CVPR52688.2022.01299). Xiangyu Qi et al., CVPR 2022, 2022. `SRA · trigger: digital, physical · physical trigger`
- [DeepPayload: Black-box Backdoor Attack on Deep Learning Models through Neural Payload Injection](https://doi.org/10.1109/ICSE43902.2021.00035). Yuanchun Li et al., ICSE 2021, 2021. `DeepPayload · trigger: physical · real system`

## Hardware attacks

### Hardware trojans and faults

- [HAMLOCK: HArdware-Model LOgically Combined attacK](https://arxiv.org/abs/2510.19145). Sanskar Amgain et al., USENIX Security 2026, 2026. `HAMLOCK · trigger: digital, processing or fault · recorded data`
- [Triggering Stealthy Feature Map Backdoors via Physical Fault Injection in Embedded Neural Networks](https://arxiv.org/abs/2607.09473). Steyn Hommes et al., arXiv preprint, 2026. `LATCH · trigger: processing or fault · real system`
- [Input-Triggered Hardware Trojan Attack on Spiking Neural Networks](https://arxiv.org/abs/2503.21793). Spyridon Raptis et al., arXiv preprint, 2025. `Input-triggered SNN hardware Trojan · trigger: digital, processing or fault · real system`
- [DeepBaR: Fault Backdoor Attack on Deep Neural Network Layers](https://arxiv.org/abs/2407.21220). C. A. Martínez-Mejía et al., arXiv preprint, 2024. `DeepBaR · trigger: digital · recorded data`
- [Evil from Within: Machine Learning Backdoors Through Dormant Hardware Trojans](https://doi.org/10.1109/ACSAC63791.2024.00077). Alexander Warnecke et al., ACSAC 2024, 2024. `Evil from Within · trigger: digital · real system`
- [Backdoor Attack on Deep Neural Networks Triggered by Fault Injection Attack on Image Sensor Interface](https://doi.org/10.3390/s23104742). Tatsuya Oyama et al., Sensors (MDPI), 2023. `MIPI fault-injection-triggered backdoor · trigger: processing or fault · real system`
- [FooBaR: Fault Fooling Backdoor Attack on Neural Network Training](https://doi.org/10.1109/TDSC.2022.3166671). Jakub Breier et al., IEEE TDSC, 2022. `FooBaR · trigger: digital · recorded data`
- [FeSHI: Feature Map-Based Stealthy Hardware Intrinsic Attack](https://doi.org/10.1109/ACCESS.2021.3104520). Tolulope A. Odetola et al., IEEE Access, 2021. `FeSHI · trigger: natural, processing or fault · real system`
- [NeuroAttack: Undermining Spiking Neural Networks Security through Externally Triggered Bit-Flips](https://doi.org/10.1109/IJCNN48605.2020.9207351). Valerio Venceslai et al., IJCNN 2020, 2020. `NeuroAttack · trigger: digital · recorded data`
- [Sequence Triggered Hardware Trojan in Neural Network Accelerator](https://doi.org/10.1109/VTS48691.2020.9107582). Zizhen Liu et al., IEEE VTS 2020, 2020. `Sequence-triggered hardware Trojan · trigger: digital, processing or fault · recorded data`

### Memory bit flips

- [ROBBIN: Rowhammer-Based Backdoor Injection during Inference](https://arxiv.org/abs/2608.23774). Saion K. Roy et al., ICCAD 2026, 2026. `ROBBIN · trigger: digital · real system`
- [Rowhammer-Based Trojan Injection: One Bit Flip Is Sufficient for Backdooring DNNs](https://www.usenix.org/conference/usenixsecurity25/presentation/li-xiang). Xiang Li et al., USENIX Security 2025, 2025. `ONEFLIP · trigger: digital · real system`
- [DeepVenom: Persistent DNN Backdoors Exploiting Transient Weight Perturbations in Memories](https://doi.org/10.1109/SP54263.2024.00223). Kunbei Cai et al., IEEE S&P 2024, 2024. `DeepVenom · trigger: digital · real system`
- [Don't Knock! Rowhammer at the Backdoor of DNN Models](https://doi.org/10.1109/DSN58367.2023.00023). M. Caner Tol et al., IEEE/IFIP DSN 2023, 2023. `CFT+BR · trigger: digital · real system`
- [One-bit Flip is All You Need: When Bit-flip Attack Meets Model Training](https://doi.org/10.1109/ICCV51070.2023.00432). Jianshuo Dong et al., ICCV 2023, 2023. `TBA · trigger: natural, processing or fault · recorded data`
- [TrojViT: Trojan Insertion in Vision Transformers](https://doi.org/10.1109/CVPR52729.2023.00392). Mengxin Zheng et al., CVPR 2023, 2023. `TrojViT · trigger: digital · recorded data`
- [ProFlip: Targeted Trojan Attack with Progressive Bit Flips](https://doi.org/10.1109/ICCV48922.2021.00762). Huili Chen et al., ICCV 2021, 2021. `ProFlip · trigger: digital · recorded data`
- [Live Trojan Attacks on Deep Neural Networks](https://doi.org/10.1109/CVPRW50498.2020.00406). Robby Costales et al., CVPR Workshops 2020, 2020. `Live Trojan · trigger: digital · recorded data`
- [TBT: Targeted Neural Network Attack With Bit Trojan](https://doi.org/10.1109/CVPR42600.2020.01321). Adnan Siraj Rakin et al., CVPR 2020, 2020. `TBT · trigger: digital · recorded data`

## Data-level defenses

- [EvoACC-BD-MIDS: Evolutionary Activation Clustering Combination-Based Backdoor Defense for Multi-Class Intrusion Detection Systems in Smart Grids](https://doi.org/10.1109/tifs.2026.3744644). Rong Wang et al., IEEE TIFS, 2026. `EvoACC-BD-MIDS · trigger: digital · recorded data`
- [Backdozer: A Backdoor Detection Methodology for DRL-based Traffic Controllers](https://doi.org/10.1145/3639828). Yue Wang et al., ACM Journal on Autonomous Transportation Systems, 2024. `Backdozer · trigger: digital · simulation`
- [Model-agnostic clean-label backdoor mitigation in cybersecurity environments](https://arxiv.org/abs/2407.08159). Severi et al., arXiv, 2024. `trigger: digital · recorded data`
- [Try to Avoid Attacks: A Federated Data Sanitization Defense for Healthcare IoMT Systems](https://arxiv.org/abs/2211.01592). arXiv, 2022. `Federated Data Sanitization Defense · trigger: digital · recorded data`

## Training-level defenses

- [Cert-ADD: Certified Adaptive Directional Defense Against Backdoor Attacks in Smart Homes Vision](https://doi.org/10.1109/jiot.2026.3696003). Ting Qiao et al., IEEE IoT-J, 2026. `Cert-ADD · trigger: digital · recorded data`
- [Defending Backdoor Attacks in Task-Oriented Multi-User Semantic Communication: A Contrastive Training Approach (Reject-BD)](https://doi.org/10.1109/tnse.2026.3666663). Jincheng Peng et al., IEEE TNSE, 2026. `Reject-BD · trigger: digital · recorded data`
- [Detecting and Mitigating Backdoor Attacks in OTA-FL Systems: A Two-Stage Robust Aggregation Scheme](https://arxiv.org/abs/2605.19253). Ma et al., arXiv, 2026. `TTI · trigger: digital · recorded data`
- [ECS-Guard: Online Logit-Geometry Monitoring for Backdoor Defense in Split Learning](https://doi.org/10.1109/icce70609.2026.11658438). Ma Viet Duc et al., ICCE 2026, 2026. `ECS-Guard · trigger: digital, natural · real system`
- [FedMCLA: Multi-Cluster Label-Shift-Aware Backdoor Defense for Heterogeneous IoT Federations](https://doi.org/10.1109/jiot.2026.3733041). Xiaoyu Zhang et al., IEEE IoT-J, 2026. `FedMCLA · trigger: digital · recorded data`
- [FedQmc: A Federated Learning Backdoor Defense Method Based on Quantum State Encoding and Multiscale Aggregation in Industrial Internet of Things](https://doi.org/10.1109/jiot.2026.3653444). Y. A. Tang et al., IEEE IoT-J, 2026. `FedQmc · trigger: digital · recorded data`
- [FedULBD: Unlearning-Driven Lightweight Backdoor Defense for Resource-Constrained Consumer Electronics Federated Learning](https://doi.org/10.1109/tce.2026.3709974). Junyan Hu et al., IEEE TCE, 2026. `FedULBD · trigger: digital · recorded data`
- [PEFL: A Privacy-Enhanced Federated Learning Framework for Mobile Edge CrowdSensing in the Presence of Collusion and Backdoor Attacks](https://doi.org/10.1109/tmc.2026.3656307). Mengyao Chen et al., IEEE TMC, 2026. `PEFL · trigger: digital · recorded data`
- [QuantDoor: A Quantum Randomized AoI Aware Learning Framework for defense against Backdoor Attacks in Wireless Channels](https://doi.org/10.1145/3748522.3779883). Nishat Mahdiya Khan et al., ACM SAC 2026, 2026. `QuantDoor · trigger: digital · recorded data`
- [Receiver-Domain Behavioral Probing for Backdoor-Resilient Federated GPS Spoofing Detection in UAV Networks](https://doi.org/10.48550/arxiv.2610.10360). Will Jedrzejczak et al., arXiv, 2026. `Receiver-domain behavioral probing · trigger: digital · recorded data`
- [SecureSplit: Mitigating Backdoor Attacks in Split Learning](https://doi.org/10.1145/3774904.3792484). Zhihao Dou et al., WWW 2026, 2026. `SecureSplit · trigger: digital · recorded data`
- [Sign-Only Federated Compressive Learning with Dual-View Trust Filtering against Backdoor Attacks (SFCLDT)](https://doi.org/10.1109/jiot.2026.3736542). Maolan Zhang et al., IEEE IoT-J, 2026. `SFCLDT · trigger: digital · recorded data`
- [Spectrum-Based Backdoor Defense for Federated Learning in Consumer Electronics](https://doi.org/10.1109/mce.2026.3708163). Jun Cheng et al., IEEE Consumer Electronics Magazine, 2026. `SpecGuard · trigger: digital · recorded data`
- [TASER: Task-Aware Spectral Energy Refine for Backdoor Suppression in UAV Swarms Decentralized Federated Learning](https://doi.org/10.48550/arxiv.2603.10075). Sizhe Huang et al., arXiv, 2026. `TASER · trigger: digital, natural · recorded data`
- [TimeGuard: Channel-wise Pool Training for Backdoor Defense in Time Series Forecasting](https://doi.org/10.48550/arxiv.2605.22365). Quang Duc Nguyen et al., arXiv, 2026. `TimeGuard · trigger: digital · recorded data`
- [Backdoor-Aware Adaptive Aggregation for Wireless Ad Hoc Federated Learning](https://doi.org/10.1109/tps-isa67132.2025.00083). Atsuya Muramatsu et al., IEEE TPS-ISA 2025, 2025. `WAFL-BAA · trigger: digital · recorded data`
- [DPCTS: Dual-Perspective Cross-Client Trust Scoring for Robust Backdoor Defense of Federated Learning Over 6G Networks](https://doi.org/10.1109/tnse.2025.3645850). Yaohua Luo et al., IEEE TNSE, 2025. `DPCTS · trigger: digital · recorded data`
- [Defending the Edge: Representative-Attention Defense against Backdoor Attacks in Federated Learning (FeRA)](https://doi.org/10.48550/arxiv.2505.10297). Chibueze Peace Obioma et al., arXiv, 2025. `FeRA · trigger: digital, natural · recorded data`
- [EarlyExodus: Leveraging early exits to mitigate backdoor vulnerability in deep learning](https://doi.org/10.1016/j.rineng.2025.106404). Salmane Douch et al., Results in Engineering, 2025. `EarlyExodus · trigger: digital · recorded data`
- [Eliminating Stealthy Backdoors via Occupying and Withdrawing for Secure Personalized Federated Learning in UAV Swarms (PFL-OW)](https://doi.org/10.1109/tccn.2025.3627915). Bo Wang et al., IEEE TCCN, 2025. `PFL-OW · trigger: digital · recorded data`
- [Krum Federated Chain (KFC): Using blockchain to defend against adversarial attacks in Federated Learning](https://arxiv.org/abs/2502.06917). arXiv, 2025. `Krum Federated Chain · trigger: digital · recorded data`
- [MoCC-BD-FID: Multi-Objective Clustering Combination-Based Backdoor Defense for Federated Intrusion Detection of Industrial Control Systems](https://doi.org/10.1109/tifs.2025.3586479). Guo-Qiang Zeng et al., IEEE TIFS, 2025. `MoCC-BD-FID · trigger: digital · recorded data`
- [RDCBA-FEL: Robust Defense Against Colluded Backdoor Attacks in Federated Edge Learning](https://doi.org/10.1109/tifs.2025.3629550). Pan Zhang et al., IEEE TIFS, 2025. `RDCBA-FEL · trigger: digital · recorded data`
- [SafeSplit: A Novel Defense Against Client-Side Backdoor Attacks in Split Learning](https://doi.org/10.14722/ndss.2025.241698). Phillip Rieger et al., NDSS 2025, 2025. `SafeSplit · trigger: digital, natural · recorded data`
- [Secure Transfer Learning: Training Clean Models Against Backdoor in (Both) Pre-trained Encoders and Downstream Datasets](https://doi.org/10.48550/arxiv.2504.11990). Yechao Zhang et al., IEEE S&P 2025, 2025. `T-Core · trigger: digital · recorded data`
- [A Stability-Enhanced Dynamic Backdoor Defense in Federated Learning for IIoT](https://doi.org/10.1109/tii.2024.3410319). Zhongcui Ma et al., IEEE TII, 2024. `Stability-enhanced dynamic backdoor defe · trigger: digital · recorded data`
- [Adaptive Robust Learning Against Backdoor Attacks in Smart Homes (ARL)](https://doi.org/10.1109/jiot.2024.3392772). Jiahui Zhang et al., IEEE IoT-J, 2024. `ARL · trigger: digital · recorded data`
- [CrowdGuard: Federated Backdoor Detection in Federated Learning](https://arxiv.org/abs/2210.07714). Phillip Rieger et al., NDSS 2024, 2024. `CrowdGuard · trigger: digital, natural · recorded data`
- [Dual-Layered Model Protection Scheme Against Backdoor Attacks in Fog Computing-Based Federated Learning](https://doi.org/10.1109/tnsm.2024.3509983). Ke Gu et al., IEEE TNSM, 2024. `Dual-layered model protection scheme · trigger: digital · recorded data`
- [FedBlock: A Blockchain Approach to Federated Learning against Backdoor Attacks](https://doi.org/10.1109/bigdata62323.2024.10825703). Duong Huong Nguyen et al., IEEE BigData 2024, 2024. `FedBlock · trigger: natural · recorded data`
- [A Blockchain-Based Federated-Learning Framework for Defense against Backdoor Attacks](https://doi.org/10.3390/electronics12112500). Li Lü et al., Electronics, 2023. `trigger: digital · recorded data`
- [BayBFed: Bayesian Backdoor Defense for Federated Learning](https://doi.org/10.1109/sp46215.2023.10179362). Kavita Kumari et al., IEEE S&P 2023, 2023. `BayBFed · trigger: digital, natural · recorded data`
- [Edge-Cloud Collaborative Defense against Backdoor Attacks in Federated Learning](https://doi.org/10.3390/s23031052). Jie Yang et al., Sensors, 2023. `Layered · trigger: digital · recorded data`
- [Joint Energy-Based Model for Robust Speech Classification System Against Dirty-Label Backdoor Poisoning Attacks](https://doi.org/10.1109/asru57964.2023.10389697). Martin Sustek et al., IEEE ASRU 2023, 2023. `JEM · trigger: digital · recorded data`
- [MITDBA: Mitigating Dynamic Backdoor Attacks in Federated Learning for IoT Applications](https://doi.org/10.1109/jiot.2023.3325634). Yongkang Wang et al., IEEE Internet of Things Journal, 2023. `MITDBA · trigger: digital · recorded data`
- [PerVK: A Robust Personalized Federated Framework to Defend Against Backdoor Attacks for IoT Applications](https://doi.org/10.1109/tii.2023.3329688). Yongkang Wang et al., IEEE TII, 2023. `PerVK · trigger: digital · recorded data`
- [Two-phase Defense Against Poisoning Attacks on Federated Learning-based Intrusion Detection (DPA-FL)](https://doi.org/10.1016/j.cose.2023.103205). Yuan-Cheng Lai et al., Computers & Security, 2023. `DPA-FL · trigger: digital · recorded data`
- [A Federated Learning Backdoor Attack Defense Method Based on Dual Attention Mechanism (FDDAM)](https://doi.org/10.1109/bigdataservice55688.2022.00030). Jin Yan et al., IEEE BigDataService 2022, 2022. `FDDAM · trigger: digital · recorded data`
- [A Secure Federated Learning Framework for Residential Short Term Load Forecasting](https://arxiv.org/abs/2209.14547). arXiv, 2022. `trigger: digital · recorded data`
- [DeepSight: Mitigating Backdoor Attacks in Federated Learning Through Deep Model Inspection](https://arxiv.org/abs/2201.00763). Phillip Rieger et al., NDSS 2022, 2022. `DeepSight · trigger: digital, natural · recorded data`
- [FLAME: Taming Backdoors in Federated Learning](https://arxiv.org/abs/2101.02281). Thien Duc Nguyen et al., arXiv, 2022. `FLAME · trigger: digital · recorded data`
- [Robust Federated Learning for Ubiquitous Computing through Mitigation of Edge-Case Backdoor Attacks (ARMOR)](https://doi.org/10.1145/3569492). Fatima Elhattab et al., ACM IMWUT, 2022. `ARMOR · trigger: natural · recorded data`
- [FLTrust: Byzantine-robust Federated Learning via Trust Bootstrapping](https://arxiv.org/abs/2012.13995). Xiaoyu Cao et al., NDSS 2021, 2021. `FLTrust · trigger: digital · recorded data`
- [Stability-Based Analysis and Defense against Backdoor Attacks on Edge Computing Services](https://doi.org/10.1109/mnet.011.2000265). Yi Zhao et al., IEEE Network, 2021. `Stability-based defense · trigger: digital · recorded data`

## Model-level defenses

- [Compile-Time Backdoor Neutralization via LLM-Guided Localized Edits](https://doi.org/10.1109/TIFS.2026.3753307). Minghui Li et al., IEEE TIFS, 2026. `CBN · trigger: processing or fault · recorded data`
- [Data Distillation Boundary Decision for Modulation Recognition Backdoor Attack Detection](https://doi.org/10.1109/ccsb71176.2026.11716451). Tao Jiang et al., CCSB 2026, 2026. `trigger: digital · simulation`
- [Detecting and Eliminating Neural Network Backdoors Through Active Paths with Application to Intrusion Detection](https://doi.org/10.48550/arxiv.2603.10641). Eirik Høyheim et al., arXiv, 2026. `trigger: digital · recorded data`
- [Efficient Backdoor Mitigation in Federated Learning With Contrastive Loss](https://doi.org/10.1109/jiot.2026.3711587). H. C. Ferguson et al., IEEE IoT-J, 2026. `trigger: digital · recorded data`
- [Fast and Effective Backdoor Removal in Federated Spiking Neural Networks via Temporal Synaptic Sanitization (FedTSR)](https://doi.org/10.3390/electronics15132904). Baoping Wang et al., Electronics, 2026. `FedTSR · trigger: digital · recorded data`
- [FlipGuard: Defending Large Language Models Against Quantization-Conditioned Backdoor Attacks](https://arxiv.org/abs/2606.28962). Aoying Zheng et al., IEEE ICME 2026, 2026. `FlipGuard · trigger: processing or fault · recorded data`
- [Lightweight and Fast Backdoor Model Detection (DFBScanner)](https://doi.org/10.48550/arxiv.2605.18907). Yinbo Yu et al., arXiv, 2026. `DFBScanner · trigger: digital, processing or fault · recorded data`
- [PRISM-TS: A Personalized Backdoor Defense Method for Power Load Time-Series Classification](https://doi.org/10.3390/sym18111852). Yaohui Wang et al., Symmetry, 2026. `PRISM-TS · trigger: digital · recorded data`
- [Backdoor Defense in Transportation Cyber-Physical Systems Using Frequency Domain Hybrid Distillation (FDHD)](https://doi.org/10.1109/tits.2025.3539887). Bin Hu et al., IEEE T-ITS, 2025. `FDHD · trigger: digital · recorded data`
- [Gradient Norm-based Fine-Tuning for Backdoor Defense in Automatic Speech Recognition (GN-FT)](https://doi.org/10.1109/icassp49660.2025.10889177). Nanjun Zhou et al., ICASSP 2025, 2025. `GN-FT · trigger: digital · recorded data`
- [MEB: A Backdoor Detection Framework for Pre-training Based Malicious Traffic Detection](https://doi.org/10.1109/trustcom66490.2025.00043). Kai Wang et al., TrustCom 2025, 2025. `MEB · trigger: digital · recorded data`
- [Offense as Defense: Efficient Detection of Backdoor Attacks With Adversarial Samples in Cyber-Physical Social Systems (OAD)](https://doi.org/10.1109/tcss.2025.3615651). Hengqi Guo et al., IEEE TCSS, 2025. `OAD · trigger: digital · recorded data`
- [Poster: A Lightweight Pruning for Mitigating Neural Network Backdoor on Edge (ALobot)](https://doi.org/10.1145/3769102.3774378). Gabriel Wolff Taveira et al., ACM/IEEE SEC 2025, 2025. `ALobot · trigger: digital · recorded data`
- [Semantic Communication Unlearning: A Variational Information Bottleneck Approach for Backdoor Defense in Wireless Systems](https://doi.org/10.3390/fi18010017). Sümeye Nur Karahan et al., Future Internet, 2025. `SCU · trigger: digital · simulation`
- [Towards Robust Speech Models: Mitigating Backdoor Attacks via Audio Signal Enhancement and Fine-Pruning Techniques](https://doi.org/10.3390/math13060984). Heyan Sun et al., Mathematics, 2025. `ASAP · trigger: digital · recorded data`
- [Unsupervised Backdoor Detection and Mitigation for Spiking Neural Networks](https://doi.org/10.1109/raid67961.2025.00025). Jiachen Li et al., RAID 2025, 2025. `TMPBD + NDSBM · trigger: digital · recorded data`
- [A New Data-Free Backdoor Removal Method via Adversarial Self-Knowledge Distillation (ADBR)](https://doi.org/10.1109/jiot.2024.3520642). Xuexiang Li et al., IEEE IoT-J, 2024. `ADBR · trigger: digital · recorded data`
- [Clean and Compact: Efficient Data-Free Backdoor Defense with Model Compactness](https://doi.org/10.1007/978-3-031-73027-6_16). Huy Phan et al., ECCV 2024, 2024. `Clean & Compact · trigger: digital · recorded data`
- [Feature Distraction Based Backdoor Defense for Federated Trained Intrusion Detection System (FDDF)](https://doi.org/10.1109/globecom52923.2024.10901202). Yuwen Chen et al., IEEE Globecom 2024, 2024. `FDDF · trigger: digital · recorded data`
- [Nearest is Not Dearest: Towards Practical Defense Against Quantization-Conditioned Backdoor Attacks (EFRAP)](https://doi.org/10.1109/cvpr52733.2024.02315). Boheng Li et al., CVPR 2024, 2024. `EFRAP · trigger: digital, processing or fault · recorded data`
- [ODSCAN: Backdoor Scanning for Object Detection Models](https://doi.org/10.1109/sp54263.2024.00119). Siyuan Cheng et al., IEEE S&P 2024, 2024. `ODSCAN · trigger: digital · recorded data`
- [Precise Defense Approach Against Small-Scale Backdoor Attacks in Industrial Internet of Things](https://doi.org/10.1109/jiot.2024.3490579). Ziyong Ran et al., IEEE IoT-J, 2024. `trigger: digital · recorded data`
- [Repairing Backdoor Model With Dynamic Gradient Clipping for Intelligent Vehicles (DGC)](https://doi.org/10.1109/tdsc.2024.3419040). Xindi Ma et al., IEEE TDSC, 2024. `DGC · trigger: digital · recorded data`
- [TRGE: A Backdoor Detection After Quantization](https://doi.org/10.1007/978-981-97-0945-8_24). Renhua Xie et al., LNCS, 2024. `TRGE · trigger: digital · recorded data`
- [Trojan Attack and Defense for Deep Learning-Based Navigation Systems of Unmanned Aerial Vehicles](https://doi.org/10.1109/access.2024.3419800). Mohammed Mynuddin et al., IEEE Access, 2024. `UAP-based Trojan detector · trigger: digital · recorded data`
- [Aegis: Mitigating Targeted Bit-flip Attacks against Deep Neural Networks](https://arxiv.org/abs/2302.13520). Jialai Wang et al., USENIX Security 2023, 2023. `Aegis · trigger: digital, processing or fault · real system`
- [A collaborative deep learning microservice for backdoor defenses in Industrial IoT networks (CoDefend)](https://doi.org/10.1016/j.adhoc.2021.102727). Qin Liu et al., Ad Hoc Networks, 2021. `CoDefend · trigger: digital · recorded data`
- [Identifying Physically Realizable Triggers for Backdoored Face Recognition Networks](https://doi.org/10.1109/icip42928.2021.9506564). Ankita Raj et al., ICIP 2021, 2021. `DTD · trigger: digital · recorded data`

## Inference-level defenses

- [Lightweight Inference-Time Backdoor Attack Detection for Resource-Constrained Internet of Drones using Tiny Vision Transformers](https://doi.org/10.1109/icicv68925.2026.11554865). Rahgul M S et al., ICICV 2026, 2026. `trigger: digital · recorded data`
- [ODPure: Backdoor Purification for Object Detection via Ensemble Corruption Consensus](https://arxiv.org/abs/2609.28239). Li Zeng et al., preprint (arXiv), 2026. `ODPure · trigger: digital · recorded data`
- [Real-Time Out-of-Band Defense for Mobile Edge UAVs: A Physics-Aware Digital Twin Power Side-Channel Architecture Against Vision Backdoors](https://doi.org/10.1109/jiot.2026.3745089). Ruigang Dong et al., IEEE IoT-J, 2026. `PADT + SSP · trigger: digital · simulation`
- [TMT: Runtime Backdoor Detection for Vision-Language-Action Policies on Unseen Tasks](https://arxiv.org/abs/2610.09462). Zirun Zhou et al., preprint (arXiv), 2026. `TMT · trigger: digital, physical · real system`
- [When Attention Betrays: Erasing Backdoor Attacks in Robotic Policies by Reconstructing Visual Tokens](https://doi.org/10.1109/icra57385.2026.11695774). Xuetao Li et al., ICRA 2026, 2026. `Bera · trigger: physical · real system`
- [Adaptive hybrid convolutional neural network-autoencoder framework for backdoor detection in GenAI-driven semantic communication systems](https://doi.org/10.52953/shzx4571). Hassan El Alami et al., ITU Journal on Future and Evolving Technologies, 2025. `CNN-AAE · trigger: digital · recorded data`
- [Michscan: Black-Box Neural Network Integrity Checking at Runtime Through Power Analysis](https://doi.org/10.1109/HOST64725.2025.11050062). Robi Paul et al., IEEE HOST 2025, 2025. `Michscan · trigger: digital, processing or fault · real system`
- [RandEye: On-Sensor Stochastic Image Transformation for Backdoor-Resistant Edge Inference](https://doi.org/10.1145/3716368.3735245). Wantong Li et al., ACM GLSVLSI 2025, 2025. `RandEye · trigger: digital · recorded data`
- [Saliency-Guided Lightweight Backdoor Defense for Edge Intelligence](https://doi.org/10.1145/3769102.3774437). Zijian Zhang et al., ACM/IEEE SEC 2025, 2025. `trigger: digital · real system`
- [Detecting Backdoor Attacks in Black-Box Neural Networks through Hardware Performance Counters](https://doi.org/10.23919/date58400.2024.10546739). Manaar Alam et al., DATE 2024, 2024. `trigger: digital · real system`
- [Novel Lightweight Method for Detecting Backdoor Attacks in Edge-Deployed Neural Networks](https://doi.org/10.1109/commnet63022.2024.10793359). Salmane Douch et al., CommNet 2024, 2024. `trigger: digital · recorded data`
- [SpeechGuard: Online Defense against Backdoor Attacks on Speech Recognition Models](https://doi.org/10.1109/ijcnn60899.2024.10650300). Jinwen Xin et al., IJCNN 2024, 2024. `SpeechGuard · trigger: digital · recorded data`
- [Knowledge Distillation Based Defense for Audio Trigger Backdoor in Federated Learning (KDDF)](https://doi.org/10.1109/globecom54140.2023.10437601). Yuwen Chen et al., IEEE Globecom 2023, 2023. `KDDF · trigger: digital · recorded data`
- [Backdoor Defence for Voice Print Recognition Model Based on Speech Enhancement and Weight Pruning](https://doi.org/10.1109/access.2022.3217322). Jiawei Zhu et al., IEEE Access, 2022. `trigger: digital · recorded data`
- [Mitigating the Backdoor Attack by Federated Filters for Industrial IoT Applications](https://doi.org/10.1109/tii.2021.3112100). Boyu Hou et al., IEEE TII, 2021. `Federated backdoor filter · trigger: digital · recorded data`
- [CleaNN](https://doi.org/10.1145/3400302.3415671). Mojan Javaheripi et al., ICCAD 2020, 2020. `CLEANN · trigger: digital · real system`
- [Optimizing Deep Learning Based Intrusion Detection Systems Defense Against White-Box and Backdoor Adversarial Attacks Through a Genetic Algorithm](https://doi.org/10.1109/aipr50011.2020.9425293). Khaled Alrawashdeh et al., IEEE AIPR 2020, 2020. `GA-Trigger-Detection · trigger: digital · recorded data`
- [DeepAttest](https://doi.org/10.1145/3307650.3322251). Huili Chen et al., ISCA 2019, 2019. `DeepAttest · trigger: processing or fault · real system`

## Evaluations, benchmarks, surveys, and standards

- [Backdoor Attacks on Contrastive Continual Learning for IoT Systems](https://arxiv.org/abs/2602.13062). Tim et al., arXiv, 2026. `trigger: digital` `evaluation`
- [Backdoors in Learning-Based Industrial Robotic Arm Manipulation: An Empirical Security Study](https://arxiv.org/abs/2609.26868). Zijian Zhang et al., IROS 2026 Workshop, 2026. `evaluation`
- [Can Federated Learning Backdoor Defenses Protect Parallel Split-Federated Learning?](https://doi.org/10.1109/wimob70978.2026.11777847). Yelyzaveta Klysa et al., IEEE WiMob 2026, 2026. `evaluation`
- [HALO: Revealing the inadequacy of backdoor defenses in encrypted traffic classification](https://doi.org/10.1016/j.comnet.2026.112656). Wang et al., Computer Networks, 2026. `evaluation`
- [Quantization-Triggered Backdoors in Language Models: Cross-Quantizer Transferability and the Validation--Deployment Gap](https://arxiv.org/abs/2608.27512). Jacopo Dardini et al., ARES 2026, 2026. `evaluation`
- [Rethinking the trigger of backdoor attacks: Towards physical backdoor threats](https://doi.org/10.1016/j.patcog.2026.113665). Yiming Li et al., Pattern Recognition, 2026. `evaluation`
- [When Does Trust Help? A Leakage-Free Evaluation of Representation- and Aggregation-Based Defenses Against Backdoors in Federated Intrusion Detection](https://doi.org/10.48550/arxiv.2610.14767). Tusar et al., arXiv, 2026. `evaluation`
- [AttackVLA: Benchmarking Adversarial and Backdoor Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2511.12149). Jiayu Li et al., preprint (arXiv), 2025. `evaluation`
- [Comprehensive Evaluation of Cloaking Backdoor Attacks on Object Detector in Real-World](https://doi.org/10.1145/3708821.3710836). Hua Ma et al., AsiaCCS 2025, 2025. `evaluation`
- [Quantization Blindspots: How Model Compression Breaks Backdoor Defenses](https://doi.org/10.48550/arxiv.2512.06243). Rohan Pandey et al., arXiv, 2025. `evaluation`
- [SoK: The Last Line of Defense: On Backdoor Defense Evaluation](https://doi.org/10.48550/arxiv.2511.13143). Gorka Abad et al., arXiv, 2025. `evaluation`
- [On the Credibility of Backdoor Attacks Against Object Detectors in the Physical World](https://doi.org/10.1109/acsac63791.2024.00079). Bao Gia Doan et al., ACSAC 2024, 2024. `evaluation`
- [Towards robustness evaluation of backdoor defense on quantized deep learning models](https://doi.org/10.1016/j.eswa.2024.124599). Yifan Zhu et al., Expert Systems with Applications, 2024. `evaluation`
- [Synthesizing Physical Backdoor Datasets: An Automated Framework Leveraging Deep Generative Models](https://arxiv.org/abs/2312.03419). Sze Jue Yang et al., preprint (arXiv), 2023. `evaluation`
- [Finding Naturally Occurring Physical Backdoors in Image Datasets](https://doi.org/10.52202/068431-1606). Emily Wenger et al., NeurIPS 2022 (Datasets & Benchmarks), 2022. `evaluation`
- [SoK: Understanding backdoor attacks & defenses in federated learning](https://doi.org/10.1016/j.eswa.2026.132558). Ahmed Ayoub Bellachia et al., Expert Systems with Applications, 2026. `survey`
- [TinyML Security: Attacks, Defenses, and Open Challenges in Resource-Constrained Machine Learning Systems](https://doi.org/10.1145/3793197). Jacob Huckelberry et al., ACM Computing Surveys, 2026. `survey`
- [A Systematic Review on the Practicality of Poisoning Defenses in Federated IoT Systems](https://doi.org/10.1109/access.2025.3637093). Anthony Jacklingo Kwame Quansah et al., IEEE Access, 2025. `survey`
- [Exploring Graph Neural Backdoors in Vehicular Networks: Fundamentals, Methodologies, Applications, and Future Perspectives](https://doi.org/10.1109/ojvt.2025.3550411). Xiao Yang et al., IEEE Open Journal of Vehicular Technology, 2025. `survey`
- [A Survey of Wireless Sensing Security from a Role-Based View: Victim, Weapon, and Shield](https://arxiv.org/abs/2412.03064). Geng et al., arXiv, 2024. `survey`
- [Data and Model Poisoning Backdoor Attacks on Wireless Federated Learning, and the Defense Mechanisms: A Comprehensive Survey](https://doi.org/10.1109/comst.2024.3361451). Yichen Wan et al., IEEE Communications Surveys & Tutorials, 2024. `survey`
- [Is There a Trojan!: Literature Survey and Critical Evaluation of the Latest ML Based Modern Intrusion Detection Systems in IoT Environments](https://doi.org/10.5121/ijci.2023.120306). Vishal Karanam et al., International Journal on Cybernetics & Informatics, 2023. `survey`
- [Edge Learning for 6G-enabled Internet of Things: A Comprehensive Survey of Vulnerabilities, Datasets, and Defenses](https://arxiv.org/abs/2306.10309). Ferrag et al., IEEE COMST. `survey`
- [BackDFL: A Unified Benchmark For Backdoor Attacks and Defenses In Decentralized Federated Learning](https://doi.org/10.48550/arxiv.2608.21137). Mouhamed Amine Bouchiha et al., arXiv, 2026. `benchmark`
- [NIDS Backdoor Benchmark: cleaned NIDS datasets and backdoor-poisoned training sets for XGBoost intrusion detectors](https://doi.org/10.5281/zenodo.23328624). Gia Hien Tran et al., Zenodo, 2026. `benchmark`
- [BackFed: An Efficient & Standardized Benchmark Suite for Backdoor Attacks in Federated Learning](https://doi.org/10.48550/arxiv.2507.04903). Thinh Dao et al., arXiv, 2025. `benchmark`
- [BackdoorBench: A Comprehensive Benchmark of Backdoor Learning](https://doi.org/10.1007/s11263-025-02447-x). Baoyuan Wu et al., IJCV 2025, 2025. `benchmark`
- [SoK: Benchmarking Poisoning Attacks and Defenses in Federated Learning (FLPoison)](https://arxiv.org/abs/2502.03801). Heyi Zhang et al., arXiv, 2025. `benchmark`
- [BackdoorBox: A Python Toolbox for Backdoor Learning](https://doi.org/10.48550/arxiv.2302.01762). Yiming Li et al., arXiv, 2023. `benchmark`
- [The TrojAI Software Framework: An OpenSource tool for Embedding Trojans into Deep Learning Models](https://doi.org/10.48550/arxiv.2003.07233). Kiran Karra et al., arXiv, 2020. `benchmark`
- MITRE ATLAS (data v5.6.0): AML.T0020, AML.T0018(.000/.001), AML.T0043.004, AML.T0010; case study AML.CS0013. MITRE et al., MITRE, 2026. `standard or guideline`
- ETSI TS 104 223 V1.1.1 Securing Artificial Intelligence (SAI); Baseline Cyber Security Requirements for AI Models and Systems. ETSI et al., ETSI, 2025. `standard or guideline`
- NIST AI 100-2 E2025, Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations. NIST et al., NIST, 2025. `standard or guideline`
- OWASP Machine Learning Security Top 10 (2023, draft v0.3). OWASP et al., OWASP, 2023. `standard or guideline`
- ENISA Securing Machine Learning Algorithms. ENISA et al., ENISA, 2021. `standard or guideline`
- ETSI GR SAI 005 V1.1.1 Mitigation Strategy Report. ETSI et al., ETSI, 2021. `standard or guideline`
- ENISA Artificial Intelligence Cybersecurity Challenges (AI threat landscape). ENISA et al., ENISA, 2020. `standard or guideline`
- [Practical and Flexible Backdoor Attack Against Deep Learning Models via Shell Code Injection](https://doi.org/10.1109/TIFS.2026.3662587). Jiakai Wang et al., IEEE TIFS, 2026. `related work`
- [MalModel: hiding malicious payload in mobile deep learning models with black-box backdoor attack](https://doi.org/10.1007/s10515-025-00569-7). Jiayi Hua et al., Automated Software Engineering (journal), 2025. `related work`
- [Models Are Codes: Towards Measuring Malicious Code Poisoning Attacks on Pre-trained Model Hubs](https://doi.org/10.1145/3691620.3695271). Jian Zhao et al., ASE 2024, 2024. `related work`

## Citation

If you find this list useful, please cite the survey. The citation will be added after publication.

## Contributing

Pull requests that add missing studies or correct labels are welcome.
