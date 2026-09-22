#  Scoping Learning to Route On-Chip: A Survey of Machine Learning-Based Routing in Networks-on-Chip and Its Hardware Overheads

**Scoping Review** · UAZ · Started 2026-06-08

Authors: Remberto Sandoval Arechiga

## Abstract
**Background:** Networks-on-Chip (NoC) interconnects constitute the fundamental pillar for communication in many-core processors. **Objectives:** To systematically evaluate and synthesize machine learning-based NoC routing methods (RL, regression, and metaheuristics) by analyzing their multi-objective performance and quantitatively measuring their hardware implementation overheads on FPGA and ASIC platforms. **Methods:** PRISMA 2020-compliant search across 7 sources; dual independent screening; MMAT (adapted for engineering studies); page-level evidence traceability. **Results:** 175 records identified, 0 duplicates removed, 175 screened, 49 studies included. **Conclusions:** see synthesis; reproducibility package accompanies this report.

## 1. Introduction
Networks-on-Chip (NoC) interconnects constitute the fundamental pillar for communication in many-core processors. As sub-nanometric manufacturing technologies advance, traditional assumptions of deterministic and static adaptive routing algorithms (such as XY routing or Odd-Even) are severely compromised by highly bursty traffic patterns, thermal variability, and structural failures. Machine Learning (ML) and Reinforcement Learning (RL) emerge as data-driven alternatives capable of making dynamic route selection decisions.1.2 RationaleDespite the rapid increase in publications on routing with ML/RL, there is a critical fragmentation in current literature: existing surveys neglect hardware synthesis aspects (silicon area, power consumption, and clock cycle latency), omit the distinction between electrical (2D/3D) and photonic media, or lack a formal framing as Partially Observable Markov Decision Processes and multi-agent systems (Dec-POMDP/MARL). This Comprehensive Review is justified by the need to synthesize empirical FPGA/ASIC synthesis evidence and establish a unified multi-objective evaluation framework.

**Rationale.** Despite the increase in ML-NoC publications, prior literature presents three severe structural limitations that justify this review:Predominance of outdated or general EDA-oriented reviews: Existing reviews do not categorize modern deep learning architectures nor do they disaggregate the impact on NoC routing with strict clock-cycle constraints (< 1 ns).Absence of realistic hardware cost synthesis: Most ML reviews for NoC focus solely on algorithmic metrics or cycle-exact simulations, omitting real ASIC synthesis data (gate equivalents, kGE) and FPGA prototyping.Lack of simultaneous consideration of physical media and multiple objectives: Previous reviews analyze planar 2D, 3D (TSV-based), or photonic architectures in isolation without systematically crossing the ML paradigm with the transmission medium and multi-objective goals (latency, power, thermal gradient, degradation/aging, resilience, and security).

## 2. Research Questions
**Framework:** PICO

RQ1: What are the most widely used ML paradigms and mathematical abstractions (Dec-POMDP, MARL, SVR, ACO) for addressing adaptive routing in NoCs?

RQ2: How does the effectiveness of learning policies vary depending on the underlying physical medium (2D electrical, 3D electrical, or silicon photonic)?

RQ3: What are the area (kGE), power (W), and decision latency (ns) overheads reported in ASIC/FPGA hardware synthesis for these intelligent routers?

RQ4: What are the primary methodological gaps, scalability bottlenecks, and evaluation biases present in the current literature?

## 3. Protocol
Status: **Approved** · Versions: v0.1 (Draft), v1.0 (Under Review), v2.0 (Approved)

Thematic and Narrative Synthesis: Disaggregation of the theoretical framework (MDP vs. Dec-POMDP/MARL) and analysis of mitigation mechanisms (logic distillation, linear function approximation).1. Comparative Quantitative Tabulation: Generation of normalized tables of hardware synthesis costs. For area normalization to Gate Equivalents (GE), the standard formula will be applied:2. Meta-Analysis Feasibility: Due to the heterogeneity of simulators, clock frequencies, technology nodes (ranging from 45 nm to 14 nm), and traffic types, a direct quantitative statistical meta-analysis is not feasible. Instead, a cross-study empirical comparative analysis will be conducted across technology ranges and normalized performance metrics.

## 4. Search Strategy
```
TITLE((*NoC OR "Network*-on-Chip" OR Interconnect*))
  AND
TITLE(*routing)
  AND
*learning
```
Executions:
- ACM Digital Library · 2026-09-07 · 19 results · query v3 · [Title: network-on-chip] AND [Title: learning] AND [E-Publication Date: (01/01/2015 TO 12/31/2026)]
- IEEE Xplore · 2026-09-07 · 41 results · query v3 · ((("Document Title":*NoC) OR ("Document Title":Network*-on-Chip) OR ("Document Title":interconnect*)) AND ("Document Title":*routing) AND ("All Metadata":*learning))
- ScienceDirect · 2026-09-07 · 49 results · query v3 · TITLE-ABS-KEY((NoC OR "Network-on-Chip" OR Interconnect) AND routing AND learning); 2015-2026; Computer Science; Enginneering
- SpringerLink · 2026-09-07 · 18 results · query v3 · Title: (*NoC OR "Network*-on-Chip" OR Interconnect*) AND *routing; Keywords: *learning; 2015-2026
- Wiley Online Library · 2026-09-07 · 24 results · query v3 · *NoC OR "Network*-on-Chip" OR Interconnect* AND *routing AND *learning" in Title; OPen Access; 2015-2026; Computer Science
- Prior Knowledge · 2026-09-08 · 24 results · query v3 · 

## 5. Eligibility Criteria
- **[Inclusion]** IC1: Original research studies published in peer-reviewed indexed journals or high-impact conference proceedings (Q1/Q2 or IEEE/ACM core).
- **[Inclusion]** IC2: Articles that explicitly propose or evaluate an NoC routing algorithm guided or supervised by ML, RL, or metaheuristic models.
- **[Inclusion]** IC2: Articles that explicitly propose or evaluate an NoC routing algorithm guided or supervised by ML, RL, or metaheuristic models.
- **[Inclusion]** IC4: Publications written in the English language.
- **[Exclusion]** EC1: Studies on routing in wide area networks (WAN), wireless sensor networks (WSN), or software-defined networks (SDN) that do not apply to on-chip hardware constraints (NoC).
- **[Exclusion]** EC2: Studies using ML for NoC tasks other than routing (e.g., task mapping, chip testing, or traffic classification only).
- **[Exclusion]** EC3: Purely descriptive papers, patents, extended abstracts, presentations, or tutorials lacking empirical validation.
- **[Exclusion]** EC4: Publications that do not provide clear information regarding the underlying router topology or architecture.

## 6. Study Selection (PRISMA flow)
- Records identified: **175**
- Duplicates removed: **0**
- Records screened: **175** (excluded 121)
- Reports sought: **54** (not retrieved 0)
- Assessed for eligibility: **54** (excluded 5)
- **Studies included: 49**

## 7. Quality Assessment (MMAT (adapted for engineering studies))
- R-01 Reinforcement Learning Based Routing for Cognitive Network on Chip — risk: High
- R-14 KARL: A Cost-Effective Routing Algorithm in Fault Tolerant 3D Network-on-Chip via k-Means Assisted Reinforcement Learning — risk: Low
- R-20 LARE: A Linear Approximate Reinforcement Learning Based Adaptive Routing for Network-on-Chips — risk: Low
- R-21 A Reinforcement Learning Framework with Region-Awareness and Shared Path Experience for Efficient Routing in Networks-on-Chip — risk: Low
- R-23 Reinforcement Learning (RL)-Based Holistic Routing and Wavelength Assignment in Optical Network-on-Chip (ONoC): Distributed or Centralized? — risk: Low
- R-25 FRoZN:Fault-Tolerant Routing Technique Using Reinforcement Learning for Zmesh NoC — risk: Low
- R-27 Fault-Tolerant Adaptive Routing in NoCs: Machine Learning Approaches for Resilient on-Chip Networks — risk: High
- R-30 RLRM: Reinforcement Learning-Based Routing for Ring-Augmented Mesh NoC — risk: Low
- R-31 A Scalable Fault-Tolerant and Congestion-Aware q-Learning Routing Framework for Network-on-Chip Systems — risk: Low
- R-34 PND3QN: A Deep Reinforcement Learning-Driven Routing Selection Framework for Network-on-Chip — risk: Moderate
- R-40 A Low-Overhead Fault-Aware Deflection Routing Algorithm for 3D Network-on-Chip — risk: Moderate
- R-41 Q-Learning Based Congestion-Aware Routing Algorithm for on-Chip Network — risk: Moderate
- R-42 HARAQ: Congestion-aware Learning Model for Highly Adaptive Routing Algorithm in on-Chip Networks — risk: Low
- R-44 Hybrid Adaptive Routing Algorithm for 2D Mesh On-Chip Networks — risk: Moderate
- R-45 A Q-routing Based Self-Regulated Routing Scheme for Network-on-Chip — risk: Moderate
- R-46 Fuzzy & Neural-Based Adaptive & Deterministic Routing Algorithm for Network-on-Chip — risk: High
- R-48 An Adaptive Routing Scheme Based on Q-Learning and Real-Time Traffic Monitoring for Network-on-Chip — risk: Moderate
- R-50 Q-Thermal: A q-Learning-Based Thermal-Aware Routing Algorithm for 3-D Network on-Chips — risk: Low
- R-51 Fault-Tolerant Routing Algorithm for Mesh Based NoC Using Reinforcement Learning — risk: Moderate
- R-52 An Adaptive Routing Algorithm Based on Multiple-Path-Finding Dijkstra’s and q-Learning Algorithm in Silicon Photonic Interconnects on Chip — risk: Low
- R-53 Reinforcement Learning Enabled Routing for High-Performance Networks-on-Chip — risk: High
- R-54 Q-Learning-Based Routing Algorithm for 3D Network-on-Chips — risk: Low
- R-55 RELAR: A Reinforcement Learning Framework for Adaptive Routing in Network-on-Chips — risk: Moderate
- R-56 A Centralized Routing Algorithm Based on DQN Algorithm in Silicon Photonic Interconnects on Chip — risk: Low
- R-58 Reinforcement Learning Based Fault-Tolerant Routing Algorithm for Mesh Based NoC and Its FPGA Implementation — risk: Low
- R-59 A Q-Learning-Based Fault-Tolerant and Congestion-Aware Adaptive Routing Algorithm for Networks-on-Chip — risk: Low
- R-60 A Novel Reinforcement Learning Framework for Adaptive Routing in Network-on-Chips — risk: Low
- R-114 Predictions Optimal Routing Algorithm Based on Artificial Intelligence Technique for 3D NoC Systems — risk: Low
- R-152 Photonic-Aware Routing in Hybrid Networks-on-Chip via Decentralized Deep Reinforcement Learning — risk: Low
- R-153 Reinforcement Learning Enabled Multi-Layered NoC for Mixed Criticality Systems — risk: Low
- R-154 MARCO: A High-performance Task Mapping and Routing Co-optimization Framework for Point-to-Point NoC-based Heterogeneous Computing Systems — risk: Low
- R-155 Adaptive Reinforcement Learning Method for Networks-on-Chip — risk: Low
- R-156 Bi-LCQ: A Low-Weight Clustering-Based Q-learning Approach for NoCs — risk: Moderate
- R-157 A Reconfigurable Fault-Tolerant Deflection Routing Algorithm Based on Reinforcement Learning for Network-on-Chip — risk: Low
- R-158 Improved Route Selection Approaches Using Q-learning Framework for 2D NoCs — risk: Moderate
- R-159 RLARA: A TSV-Aware Reinforcement Learning Assisted Fault-Tolerant Routing Algorithm for 3D Network-on-Chip — risk: Low
- R-160 PreNoc: Neural Network Based Predictive Routing for Network-on-Chip Architectures — risk: Low
- R-161 Q-Function-Based Traffic- and Thermal-Aware Adaptive Routing for 3D Network-on-Chip — risk: Moderate
- R-162 TTQR: A Traffic- and Thermal-Aware Q-Routing for 3D Network-on-Chip — risk: Low
- R-163 Enhancing NoC-Based MPSoC Performance: A Predictive Approach With ANN and Guaranteed Convergence Arithmetic Optimization Algorithm — risk: Low
- R-164 DeepNR: An Adaptive Deep Reinforcement Learning Based NoC Routing Algorithm — risk: Low
- R-165 Machine Learning-Assisted Routing Optimization for Scalable Network-on-Chip Architectures — risk: Low
- R-166 A Novel Congestion-Aware Adaptive Routing Algorithm Based on Reinforcement Learning for VCmesh-based Optical Network-on-Chip — risk: Low
- R-167 A Holistic Approach Towards Intelligent Hotspot Prevention in Network-on-Chip-Based Multicores — risk: Low
- R-168 Intelligent Congestion Control for NoC Architecture in Gem5 Simulator — risk: Moderate
- R-169 A Deep Learning Based Latency Aware Predictive Routing Model for Network-on-Chip Architectures — risk: Low
- R-170 A Fault-Tolerant and Congestion-Aware Routing Algorithm for Networks-on-Chip — risk: High
- R-171 DRLAR: A Deep Reinforcement Learning-Based Adaptive Routing Framework for Network-on-Chips — risk: Low
- R-172 Reinforcement Learning-Driven Fault-Tolerant Routing for Mesh-Based Network-on-Chip Architectures — risk: Low
- R-173 A Table-Free Approximate \mkbibemphQ -Learning-Based Thermal-Aware Adaptive Routing for Optical NoCs — risk: Low
- R-174 Layer-Coupled Parity Turn and Adaptive Expected State–Action–Reward–State–Action-based Routing in Three-Dimensional Networks-on-Chip — risk: Low
- R-175 An Adaptive Routing Method Based on Fuzzy Logic System in Optical Network-on-Chip (ONoC) — risk: High

## 8. Data Extraction & Evidence Matrix
| Study | Year | Platform | Technique | Comparator | Primary Outcome | Benchmark |
|---|---|---|---|---|---|---|
| R-01 | 2016 | 2D mesh NoC | Q-learning | XY routing, DyAD | Average packet latency / throughput | Synthetic CBR traffic generator, 8×8 mesh, NIRGAM simulator |
| R-14 | 2022 | 3D NoC | Hybrid | TAFT, Advertiser Elevator (state-of-the-art fault-tolerant 3D NoC routing) | fault tolerance / packet delivery rate + average latency | synthetic traffic under 5%-20% fault injection rates (gem5 garnet2.0 simulator) |
| R-20 | 2023 | 2D mesh NoC | DQN / RL | DOR, O1TURN, Footprint, RL (full Q-table) | average packet latency, area overhead | synthetic (uniform-random, shuffle, transpose, mix) + PARSEC2.1 real applications (11 apps) |
| R-21 | 2023 | 2D mesh NoC | Q-learning | QR (Q-routing), BiLCQ, CrQ, DyAD, XY | Average packet latency / NoC energy consumption | Synthetic (bit-reversal, butterfly, transpose, random uniform) + PARSEC benchmark suite, 8×8 mesh (Noxim) |
| R-23 | 2024 | 2D mesh NoC | DQN / RL | Step-by-step (separate) routing + wavelength assignment baseline | Multi-objective: OSNR, load balancing, waiting delay, wavelength utilization | Synthetic communication-pair traffic in simulated ONoC (no standard benchmark named) |
| R-25 | 2025 | 2D mesh NoC | Q-learning | prior ZMesh fault-tolerant routing technique (Veda Bhanu et al. 2020) | fault tolerance / packet delivery rate | 100 random source-destination pairs per topology under varying fault percentages (link and router faults), 5x5/10x10/15x15 ZMesh |
| R-27 | 2025 | 2D mesh NoC | Hybrid | None / self-comparison only (narrative review of prior works) | fault tolerance / packet delivery rate | not applicable (literature survey; cites third-party results, e.g., 8x8 mesh benchmarks from reviewed works) |
| R-30 | 2026 | 2D mesh NoC | Q-learning | conventional mesh, static hybrid ring-mesh routing (RSDR) | average packet latency / load balancing | realistic benchmark traffic patterns (not further specified in excerpt) |
| R-31 | 2026 | 2D mesh NoC | Q-learning | classical deterministic (XY), adaptive/congestion-aware (DBAR, RCA, DyXY-type), and other RL-based schemes (HARAQ, QCA, RELAR) referenced qualitatively | fault tolerance / packet delivery rate + hop count (congestion-aware) | offline training on 5x5 mesh, inference-only evaluation on 5x5, 8x8, 12x12, 16x16 meshes under 0-20% fault density (uniform and non-uniform fault distributions) |
| R-34 | 2026 | 2D mesh NoC | DQN / RL | Q-learning, SARSA, DQN | latency-minimizing routing-algorithm selection (meta-routing) | synthetic uniform random traffic (injection rate 0.05-0.40), 8×8/4×4/2×2 mesh (Gem5 HeteroGarnet) |
| R-40 | 2011 | 3D NoC | Q-learning | Reinforcement-learning deflection switch with global routing table (GR) | Fault tolerance / average packet latency, area-power overhead | Synthetic (uniform random, transpose, local) + Splash-2 traces (barnes, cholesky, fft, fmm, lu, radix, raytrace, water) on 4×4×4 3D mesh |
| R-41 | 2011 | 2D mesh NoC | Q-learning | DyXY | average packet latency / throughput | synthetic uniform random and hotspot (H=10%) |
| R-42 | 2012 | 2D mesh NoC | Q-learning | DBAR, C-Routing (Q-learning clustered) | average packet latency / congestion avoidance | synthetic uniform random, hotspot (H=10%) + SPLASH-2 traces (GEMS) |
| R-44 | 2017 | 2D mesh NoC | Hybrid | Odd-even turn model, west-first, north-last routing | Average packet latency | Synthetic traffic (uniform, transpose, tornado), 8×8 mesh (BookSim) |
| R-45 | 2017 | 2D mesh NoC | Q-learning | DyXY | average packet transfer latency | uniform traffic, transpose traffic (Booksim2.0, 16×16 mesh) |
| R-46 | 2018 | 2D mesh NoC | Hybrid | Dynamic XY (DyXY) routing algorithm | Throughput, latency, power consumption (conceptual comparison) | None / self-comparison only (no simulation or dataset — conceptual/qualitative paper) |
| R-48 | 2019 | 2D mesh NoC | Q-learning | C-XY, DyXY | average packet transmission latency | synthetic benchmark + industrial MWD application traffic |
| R-50 | 2020 | 3D NoC | Q-learning | PTB3R (proactive) and TAAR (reactive) thermal-aware routing algorithms | Thermal balancing (temperature distribution) and network performance (latency/throughput) | Synthetic traffic pattern(s) via traffic-thermal co-simulation (PATNoxim) |
| R-51 | 2020 | 2D mesh NoC | Q-learning | Algorithm by Khichar et al. 2017 (dynamic XY-YX fault-tolerant routing) | Fault tolerance / packet delivery rate (optimal path under link and router faults) | Self-generated (synthetic) random source-destination test sets, no application traffic |
| R-52 | 2020 | 2D mesh NoC | Hybrid | Dijkstra, Random, Q-learning (standalone) | load balance / traffic congestion / insertion loss (path reservation latency) | 1000 random source-destination pairs on M×M mesh (4x4, 6x6, 8x8, 10x10), Cygnus router model |
| R-53 | 2021 | 2D mesh NoC | DQN / RL | XY-routing (DoR), random-oblivious routing, adaptive west-first routing (fixed baselines) | Average NoC latency minimization via dynamic routing-algorithm selection | Uniform-random synthetic traffic (garnet2.0/gem5), injection rates 0.05–0.40 |
| R-54 | 2021 | 3D NoC | Q-learning | XY, HARAQ (2D), deterministic XYZ (3D) | average latency / throughput | synthetic uniform and hotspot traffic |
| R-55 | 2021 | 2D mesh NoC | DQN / RL | DOR, Footprint | average packet latency | synthetic (uniform, bitcomp, transpose, shuffle) |
| R-56 | 2021 | 2D mesh NoC | DQN / RL | distributed Dijkstra-Q algorithm (authors' prior work) | load balance / waiting delay (congestion) / insertion loss | synthetic uniform-random, hot-spot, and transpose traffic (Poisson process), 4x4 mesh |
| R-58 | 2022 | 2D mesh NoC | Q-learning | Prior RL/knowledge-base fault-tolerant routing algorithms ([7],[8],[9] in paper: Q-learning-based, DSPIN, dynamic XY-YX) | Fault tolerance / packet delivery rate and average network latency | Synthetic fault injection (link/router faults) on varying mesh sizes, System-C cycle-accurate simulator; FPGA case studies |
| R-59 | 2022 | 2D mesh NoC | Q-learning | CG, FG, FTDR routing algorithms | Fault-tolerant routing + congestion-aware adaptive routing (latency/throughput under faults) | Synthetic uniform and transpose traffic; PARSEC v2.1 traces via Netrace/M5 |
| R-60 | 2021 | 2D mesh NoC | DQN / RL | Footprint, O1TURN/DOR (implied), DBAR | average packet latency | synthetic (uniform, hotspot, bursty) + GPCNeT HPC interconnect benchmark |
| R-114 | 2020 | 3D NoC | CNN | 3D Odd-Even routing, DLAR routing (also DLADR in sensitivity analysis) | Throughput and energy consumption optimization via routing algorithm switching | Synthetic traffic (varied injection rate) for training; PARSEC benchmark workloads (Blackscholes, Canneal, Dedup, Vips, Streamcluster, Ferret, Fluidanimate, Bodytrack, X264, Swaptions) for validation via Gem5 |
| R-152 | 2026 | 2D mesh NoC | DQN / RL | XY, West-First (deterministic), ARCA (adaptive), DRLAR, DeepNR (DRL) | Mean packet latency, throughput, energy per delivered bit | Synthetic (uniform, transpose, bit-complement, hotspot, bursty) + full PARSEC 3.0 and SPLASH-2 suites + 2 AI-inspired workloads (MLPerf Tiny, GraphBIG PageRank) |
| R-153 | 2023 | Many-core chip | Hybrid | Static XY, Static Layer XY, adaptive Near-Node congestion-aware routing (NN with/without CA) | throughput / latency for mixed-criticality traffic | uniform random traffic injection (SystemVerilog testbench) |
| R-154 | 2021 | 2D mesh NoC | DQN / RL | state-of-the-art mapping+routing co-optimization for homogeneous systems; combinations of SOTA independent mapping (communication-aware/computation-aware) and routing (contention-aware SOTA) | schedule length (application makespan) | real applications (e.g., H.264) on point-to-point ArSMART NoC-based heterogeneous computing systems, 8x8 mesh |
| R-155 | 2012 | 2D mesh NoC | Q-learning | Q-routing, DRQ-routing, Dynamic XY-routing | Average packet latency / congestion alleviation | Synthetic traffic (uniform random, transpose, hotspot) on 4×4 mesh |
| R-156 | 2014 | 2D mesh NoC | Q-learning | Traditional Q-routing, C-routing, DBAR, Dynamic XY | Average packet latency / routing-table area overhead | Synthetic traffic (uniform) on 8×8 mesh |
| R-157 | 2010 | 2D mesh NoC | Q-learning | FoN (Fault-on-Neighbor) switch, cost-based deflection switch, turn-model resilient routing | Fault tolerance / packet delivery (throughput, hop count) under link faults | Synthetic (uniform random, transpose, bit-complement, bit-reverse, shuffle, tornado) + Splash-2-mapped applications (matrix mult., FFT, wavefront) on 8×8 mesh |
| R-158 | 2015 | 2D mesh NoC | Q-learning | Q-routing (conventional) and its variants | Average packet latency / adaptation speed to congestion | Synthetic traffic, in-house C-based OCN simulator, 4×4 and 8×8 mesh |
| R-159 | 2023 | 3D NoC | Hybrid | Ideal routing, LEAD, Advertiser Elevator, TAFT, Elevator First | Fault tolerance / average latency and successful delivery rate | Synthetic uniform random traffic, Garnet2.0 simulator, 3×3×3 and 4×4×4 3D mesh |
| R-160 | 2017 | 2D mesh NoC | CNN | DOR (XY), xy_yx, Adaptive (Adap) | Average packet latency / throughput | Synthetic (Transpose, Bit Reverse, Tornado) + H.264 encoder traces, 8×8 mesh (BookSim) |
| R-161 | 2020 | 3D NoC | Q-learning | PTB3R, PTDBA (proactive RTM); TLAR, TAAR, TTABR (reactive RTM); prior Q-learning-based routing | Throughput / thermal balance (inter-layer traffic and heat distribution) | Synthetic traffic, simulation, 8×8×4 3D mesh |
| R-162 | 2022 | 3D NoC | Q-learning | TAAR routing algorithm | Traffic load balancing + thermal balancing (latency, throughput, temperature distribution) | Synthetic traffic: random, shuffle, bit-reversal |
| R-163 | 2023 | 2D mesh NoC | Hybrid | XY, Odd-Even, West-First, North-Last routing algorithms; also compared to PSOGW-ANN, SMA-ANN, AOA-ANN, Random Forest, plain ANN | Prediction of routing algorithm choice during Design Space Exploration (regression accuracy) | NOXIM-simulated NoC-based MPSoC traffic dataset (1250 records) |
| R-164 | 2022 | 2D mesh NoC | DQN / RL | Existing Q-routing/adaptive routing approaches (implicit; conventional routing baseline) | Average packet latency reduction and throughput | Synthetic traffic and real-time (real application) traffic via Gem5 |
| R-165 | 2026 | 2D mesh NoC | DQN / RL | Deterministic XY routing | Latency, throughput, energy efficiency (EDP), reliability (PDR), scalability | Synthetic traffic: Random, Hotspot, Bit-Complement traffic patterns |
| R-166 | 2026 | 2D mesh NoC | Q-learning | LORP (Length-Optimized Routing Protocol), also XY and Standard-Q (mesh RL) baselines | Average end-to-end delay and maximum throughput (with optical insertion loss trade-off) | Synthetic traffic: uniform, transpose, hotspot-point, hotspot-area |
| R-167 | 2016 | 2D mesh NoC | CNN | Prior-art congestion-aware/load-balancing routing algorithms (e.g., BARP, DyXY, DyAD, GCA, DBAR, DAR) | Network throughput improvement via proactive hotspot prevention (also latency, hardware overhead) | Synthetic adversarial traffic (hotspot, transpose patterns) + real application traces from TRIPS CMP (SPEC CPU2000-based benchmarks, e.g., vpr, ammp) |
| R-168 | 2022 | 2D mesh NoC | Q-learning | XY, Odd-Even | average packet latency, power/energy | synthetic uniform, transpose, bit-reverse (Gem5 Garnet2.0, 8×8 mesh) |
| R-169 | 2023 | 2D mesh NoC | Hybrid | SVR, ANN, DOR, XY-YX, PreNoC, Adaptive routing | latency-aware routing accuracy / average packet latency, throughput | synthetic traffic (uniform/transpose/shuffle/tornado/bit-reversal/bit-complement) + H.264 encoder application benchmark |
| R-170 | 2010 | 2D mesh NoC | Hybrid | Dimension-order routing baseline | Latency −9.1%, throughput +5.1% vs baseline | Synthetic + trace-driven benchmarks |
| R-171 | 2024 | 2D mesh NoC | DQN / RL | Odd-even, DyXY, RCA, GCA, DBAR (heuristic baselines); implied DOR | average packet latency, throughput | Synthetic traffic (Uniform, Shuffle, Transpose, etc.) and PARSEC 2.1 |
| R-172 | 2026 | 2D mesh NoC | DQN / RL | Q-learning, static routing | fault tolerance / packet delivery ratio (PDR), latency, throughput | synthetic random/hotspot traffic + standard NoC benchmarks (MPEG, MWD, 263ENC, 263DEC, MP3ENC, VOPD) |
| R-173 | 2021 | 2D mesh NoC | Q-learning | Negative-First, Odd-Even, West-First routing, traditional table-based Q-routing | thermal-aware routing / average thermal-induced optical power loss, network throughput | synthetic traffic (uniform, transpose, bit-reverse, hotspot) + real applications, 5 temperature distributions (SystemC + Hotspot + McPAT, 8×8 and 16×16 optical mesh NoC) |
| R-174 | 2026 | 3D NoC | DQN / RL | LCPT (rule-based), LCPT-Q (table-based Q-learning) | average packet latency, tail (max) latency, energy-delay product (EDP) per flit | synthetic uniform and transpose traffic (Access Noxim simulator, 4×4×4 and 6×6×6 3D mesh) |
| R-175 | 2022 | 2D mesh NoC | Hybrid | Dimension-order routing baseline | Latency −18.1%, throughput +5.1% vs baseline | Synthetic + trace-driven benchmarks |

## 9. Evidence Synthesis


### Themes


## 10. Research Gaps


## 11. Limitations
Simulation-only primary evidence; heterogeneous traffic generators; single reviewer resolved conflicts at full text where needed.

## 12. References (included studies)
- [R-01] Gupta, Yogendra, Bhargava, Lava (2016). Reinforcement Learning Based Routing for Cognitive Network on Chip. *Proceedings of the Second International Conference on Information and Communication Technology for Competitive Strategies*. doi:10.1145/2905055.2905093
- [R-14] Chen, Lujian, Jiao, Jiajia, Shen, Ruirui (2022). KARL: A Cost-Effective Routing Algorithm in Fault Tolerant 3D Network-on-Chip via k-Means Assisted Reinforcement Learning. *Proceedings of the 7th International Conference on Big Data and Computing*. doi:10.1145/3545801.3545808
- [R-20] Wang, Shaocong, Zhang, Xiaoyun, Dong, Dezun, Li, Cunlu, Wang, Zicong, Zhang, Zongmao (2023). LARE: A Linear Approximate Reinforcement Learning Based Adaptive Routing for Network-on-Chips. *2023 IEEE International Symposium on Circuits and Systems (ISCAS)*. doi:10.1109/ISCAS46773.2023.10181382
- [R-21] Khan, Kamil, Pasricha, Sudeep (2023). A Reinforcement Learning Framework with Region-Awareness and Shared Path Experience for Efficient Routing in Networks-on-Chip. *IEEE Design & Test*. doi:10.1109/MDAT.2023.3306719
- [R-23] Li, Hui, Zhao, Jiahe, Liu, Feiyang (2024). Reinforcement Learning (RL)-Based Holistic Routing and Wavelength Assignment in Optical Network-on-Chip (ONoC): Distributed or Centralized?. *IEEE Journal on Emerging and Selected Topics in Circuits and Systems*. doi:10.1109/JETCAS.2024.3435721
- [R-25] Choudhary, Jitesh, Barbhuiya, Imran Hussain, M, Dharrun Singh., J, Soumya (2025). FRoZN:Fault-Tolerant Routing Technique Using Reinforcement Learning for Zmesh NoC. *2025 38th International Conference on VLSI Design and 2024 23rd International Conference on Embedded Systems (VLSID)*. doi:10.1109/VLSID64188.2025.00024
- [R-27] Adnan, Muhammad, Chaudary, Muhammad Akmal, Ali, Muhammad Moazzam, Aatif, Hafiz Ayaan, Raza, Muhammad Ibrahim, Ramzan, Hafiz Arslan (2025). Fault-Tolerant Adaptive Routing in NoCs: Machine Learning Approaches for Resilient on-Chip Networks. *2025 International Conference on Artificial Intelligence, Computer, Data Sciences and Applications (ACDSA)*. doi:10.1109/ACDSA65407.2025.11165816
- [R-30] Fang, Juan, Guo, Jingming, He, Yubin, Ming, Qi (2026). RLRM: Reinforcement Learning-Based Routing for Ring-Augmented Mesh NoC. *IEEE Transactions on Very Large Scale Integration (VLSI) Systems*. doi:10.1109/TVLSI.2026.3664149
- [R-31] Choudhary, Jitesh, Das, Rituraj, Chandermani, Daryani, Ritu, Barbhuiya, Imran Hussain, J, Soumya (2026). A Scalable Fault-Tolerant and Congestion-Aware q-Learning Routing Framework for Network-on-Chip Systems. *IEEE access : practical innovations, open solutions*. doi:10.1109/ACCESS.2026.3675015
- [R-34] Wang, Jingwen, Yu, Fang, Sun, Xuecheng, family=Sousa, given=José T., prefix=de, useprefix=true, Li, Jiao (2026). PND3QN: A Deep Reinforcement Learning-Driven Routing Selection Framework for Network-on-Chip. *2026 IEEE Wireless Communications and Networking Conference Workshops (WCNCW)*. doi:10.1109/WCNCW67598.2026.11555293
- [R-40] Feng, Chaochao, Zhang, Minxuan, Li, Jinwen, Jiang, Jiang, Lu, Zhonghai, Jantsch, Axel (2011). A Low-Overhead Fault-Aware Deflection Routing Algorithm for 3D Network-on-Chip. *2011 IEEE Computer Society Annual Symposium on VLSI*. doi:10.1109/ISVLSI.2011.42
- [R-41] Farahnakian, Fahimeh, Ebrahimi, Masoumeh, Daneshtalab, Masoud, Liljeberg, Pasi, Plosila, Juha (2011). Q-Learning Based Congestion-Aware Routing Algorithm for on-Chip Network. *2011 IEEE 2nd International Conference on Networked Embedded Systems for Enterprise Applications*. doi:10.1109/NESEA.2011.6144949
- [R-42] Ebrahimi, Masoumeh, Daneshtalab, Masoud, Farahnakian, Fahimeh, Plosila, Juha, Liljeberg, Pasi, Palesi, Maurizio, Tenhunen, Hannu (2012). HARAQ: Congestion-aware Learning Model for Highly Adaptive Routing Algorithm in on-Chip Networks. *2012 IEEE/ACM Sixth International Symposium on Networks-on-Chip*. doi:10.1109/NOCS.2012.10
- [R-44] Krishnan, S. Gogula, Inbarasan, T., Chitra, P. (2017). Hybrid Adaptive Routing Algorithm for 2D Mesh On-Chip Networks. *2017 Third International Conference on Sensing, Signal Processing and Security (ICSSS)*. doi:10.1109/SSPS.2017.8071607
- [R-45] Xiang, Yande, Meng, Jianyi, Ma, De (2017). A Q-routing Based Self-Regulated Routing Scheme for Network-on-Chip. *2017 IEEE 9th International Conference on Communication Software and Networks (ICCSN)*. doi:10.1109/ICCSN.2017.8230101
- [R-46] Singh, Ashok Kumar, Shahi, Ashima (2018). Fuzzy & Neural-Based Adaptive & Deterministic Routing Algorithm for Network-on-Chip. *2018 2nd International Conference on Inventive Systems and Control (ICISC)*. doi:10.1109/ICISC.2018.8398865
- [R-48] Fan, Renshi, Du, Gaoming, Xu, Pengfei, Li, Zhenmin, Song, Yukun, Zhang, Duoli (2019). An Adaptive Routing Scheme Based on Q-Learning and Real-Time Traffic Monitoring for Network-on-Chip. *2019 IEEE 13th International Conference on Anti-Counterfeiting, Security, and Identification (ASID)*. doi:10.1109/ICASID.2019.8924997
- [R-50] Shahabinejad, Narges, Beitollahi, Hakem (2020). Q-Thermal: A q-Learning-Based Thermal-Aware Routing Algorithm for 3-D Network on-Chips. *IEEE Transactions on Components, Packaging and Manufacturing Technology*. doi:10.1109/TCPMT.2020.3018176
- [R-51] Samala, Jagadheesh, Takawale, Harshvardhan, Chokhani, Yash, Bhanu, P. Veda, J., Soumya (2020). Fault-Tolerant Routing Algorithm for Mesh Based NoC Using Reinforcement Learning. *2020 24th International Symposium on VLSI Design and Test (VDAT)*. doi:10.1109/VDAT50263.2020.9190340
- [R-52] Chen, Yanyi, Li, Hui, Liu, Feiyang (2020). An Adaptive Routing Algorithm Based on Multiple-Path-Finding Dijkstra’s and q-Learning Algorithm in Silicon Photonic Interconnects on Chip. *2020 IEEE 20th International Conference on Communication Technology (ICCT)*. doi:10.1109/ICCT50939.2020.9295898
- [R-53] Reza, Md Farhadur, Le, Tung Thanh (2021). Reinforcement Learning Enabled Routing for High-Performance Networks-on-Chip. *2021 IEEE International Symposium on Circuits and Systems (ISCAS)*. doi:10.1109/ISCAS51556.2021.9401790
- [R-54] BÖLÜCÜ, Nurettin, TOSUN, Suleyman (2021). Q-Learning-Based Routing Algorithm for 3D Network-on-Chips. *2021 24th International Symposium on Design and Diagnostics of Electronic Circuits & Systems (DDECS)*. doi:10.1109/DDECS52668.2021.9417050
- [R-55] Wang, Changhong, Dong, Dezun, Wang, Zicong, Zhang, Xiaoyun, Zhao, Zhenyu (2021). RELAR: A Reinforcement Learning Framework for Adaptive Routing in Network-on-Chips. *2021 IEEE International Conference on Cluster Computing (CLUSTER)*. doi:10.1109/Cluster48925.2021.00069
- [R-56] Chen, Yanyi, Li, Hui (2021). A Centralized Routing Algorithm Based on DQN Algorithm in Silicon Photonic Interconnects on Chip. *2021 IEEE 21st International Conference on Communication Technology (ICCT)*. doi:10.1109/ICCT52962.2021.9657992
- [R-58] Jagadheesh, Samala, Bhanu, P. Veda, Soumya, J., Cenkeramaddi, Linga Reddy (2022). Reinforcement Learning Based Fault-Tolerant Routing Algorithm for Mesh Based NoC and Its FPGA Implementation. *IEEE access : practical innovations, open solutions*. doi:10.1109/ACCESS.2022.3168992
- [R-59] Liu, Yi, Guo, Rujia, Xu, Changqing, Weng, Xiaodong, Yang, Yintang (2022). A Q-Learning-Based Fault-Tolerant and Congestion-Aware Adaptive Routing Algorithm for Networks-on-Chip. *IEEE Embedded Systems Letters*. doi:10.1109/LES.2022.3176233
- [R-60] Wang, Changhong, Wang, Zicong, Dong, Dezun, Zhang, Xiaoyun, Zhao, Zhenyu (2021). A Novel Reinforcement Learning Framework for Adaptive Routing in Network-on-Chips. *2021 IEEE 23rd Int Conf on High Performance Computing & Communications; 7th Int Conf on Data Science & Systems; 19th Int Conf on Smart City; 7th Int Conf on Dependability in Sensor, Cloud & Big Data Systems & Application (HPCC/DSS/SmartCity/DependSys)*. doi:10.1109/HPCC-DSS-SmartCity-DependSys53884.2021.00069
- [R-114] Furat Al-ObaidyFarah A. Mohammadi (2020). Predictions Optimal Routing Algorithm Based on Artificial Intelligence Technique for 3D NoC Systems. *Microsystem Technologies*. doi:10.1007/s00542-020-05084-1
- [R-152] Kakoulli, Elena (2026). Photonic-Aware Routing in Hybrid Networks-on-Chip via Decentralized Deep Reinforcement Learning. *AI*. doi:10.3390/ai7020065
- [R-153] Anantharajaiah, Nidhi, Lesniak, Fabian, Harbaum, Tanja, Becker, Juergen (2023). Reinforcement Learning Enabled Multi-Layered NoC for Mixed Criticality Systems. *2023 IEEE 16th International Symposium on Embedded Multicore/Many-core Systems-on-Chip (MCSoC)*. doi:10.1109/MCSoC60832.2023.00014
- [R-154] Chen, Hui, Zhang, Zihao, Chen, Peng, Luo, Xiangzhong, Li, Shiqing, Liu, Weichen (2021). MARCO: A High-performance Task Mapping and Routing Co-optimization Framework for Point-to-Point NoC-based Heterogeneous Computing Systems. *ACM Trans. Embed. Comput. Syst.*. doi:10.1145/3476985
- [R-155] Farahnakian, Fahimeh, Ebrahimi, Masoumeh, Daneshtalab, Masoud, Plosila, Juha, Liljeberg, Pasi (2012). Adaptive Reinforcement Learning Method for Networks-on-Chip. *2012 International Conference on Embedded Computer Systems (SAMOS)*. doi:10.1109/SAMOS.2012.6404180
- [R-156] Farahnakian, F., Ebrahimi, M., Daneshtalab, M., Liljeberg, P., Plosila, J. (2014). Bi-LCQ: A Low-Weight Clustering-Based Q-learning Approach for NoCs. *Microprocessors and Microsystems*. doi:10.1016/j.micpro.2013.11.008
- [R-157] Feng, Chaochao, Lu, Zhonghai, Jantsch, Axel, Li, Jinwen, Zhang, Minxuan (2010). A Reconfigurable Fault-Tolerant Deflection Routing Algorithm Based on Reinforcement Learning for Network-on-Chip. *Proceedings of the Third International Workshop on Network on Chip Architectures*. doi:10.1145/1921249.1921254
- [R-158] Gupta, Niyati, Kumar, Manoj, Sharma, Ashish, Gaur, Manoj Singh, Laxmi, Vijay, Daneshtalab, Masoud, Ebrahimi, Masoumeh (2015). Improved Route Selection Approaches Using Q-learning Framework for 2D NoCs. *Proceedings of the 3rd International Workshop on Many-core Embedded Systems*. doi:10.1145/2768177.2768180
- [R-159] Jiao, Jiajia, Shen, Ruirui, Chen, Lujian, Liu, Jin, Han, Dezhi (2023). RLARA: A TSV-Aware Reinforcement Learning Assisted Fault-Tolerant Routing Algorithm for 3D Network-on-Chip. *Electronics*. doi:10.3390/electronics12234867
- [R-160] Kinsy, Michel A., Khadka, Shreeya, Isakov, Mihailo (2017). PreNoc: Neural Network Based Predictive Routing for Network-on-Chip Architectures. *Proceedings of the Great Lakes Symposium on VLSI 2017*. doi:10.1145/3060403.3060406
- [R-161] Lee, Seung Chan, Han, Tae Hee (2020). Q-Function-Based Traffic- and Thermal-Aware Adaptive Routing for 3D Network-on-Chip. *Electronics*. doi:10.3390/electronics9030392
- [R-162] Liu, Hanyan, Chen, Xiaowen, Zhao, Yunping, Li, Chen, Lu, Jianzhuang (2022). TTQR: A Traffic- and Thermal-Aware Q-Routing for 3D Network-on-Chip. *Sensors*. doi:10.3390/s22228721
- [R-163] Muhsen, Yousif Raad, Husin, Nor Azura, Zolkepli, Maslina Binti, Manshor, Noridayu, Al-Hchaimi, Ahmed Abbas Jasim, Ridha, Hussein Mohammed (2023). Enhancing NoC-Based MPSoC Performance: A Predictive Approach With ANN and Guaranteed Convergence Arithmetic Optimization Algorithm. *IEEE Access*. doi:10.1109/ACCESS.2023.3305669
- [R-164] R.S., Reshma Raj, R., Rohit, Shahreyar, Mushrif Shaikh, Raut, Akash, P.N., Pournami, Kalady, Saidalavi, P.B., Jayaraj (2022). DeepNR: An Adaptive Deep Reinforcement Learning Based NoC Routing Algorithm. *Microprocessors and Microsystems*. doi:10.1016/j.micpro.2022.104485
- [R-165] Rai, H T, Mu, G W, Lu, R Q (2026). Machine Learning-Assisted Routing Optimization for Scalable Network-on-Chip Architectures. *National Journal of Advanced VLSI Design and Systems*. doi:pending/54cd9961
- [R-166] Song, Tingting, Jiang, Jinli, Ye, Yichen, Su, Ye, Huang, Cong, Zhu, Yi (2026). A Novel Congestion-Aware Adaptive Routing Algorithm Based on Reinforcement Learning for VCmesh-based Optical Network-on-Chip. *Optical Fiber Technology*. doi:10.1016/j.yofte.2025.104523
- [R-167] Soteriou, Vassos, Theocharides, Theocharis, Kakoulli, Elena (2016). A Holistic Approach Towards Intelligent Hotspot Prevention in Network-on-Chip-Based Multicores. *IEEE Transactions on Computers*. doi:10.1109/TC.2015.2435748
- [R-168] Srivastava, Smriti, Shaikh, Mushtaq Ahmed, G, Shivaneetha, Moharir, Minal (2022). Intelligent Congestion Control for NoC Architecture in Gem5 Simulator. *2022 IEEE 15th International Symposium on Embedded Multicore/Many-core Systems-on-Chip (MCSoC)*. doi:10.1109/MCSoC57363.2022.00062
- [R-169] Sudhakar, M. Venkata, Reddy, P. Rahul, Penchalaiah, Usthulamuri, Reddy, P. Raghava (2023). A Deep Learning Based Latency Aware Predictive Routing Model for Network-on-Chip Architectures. *International Journal of Communication Systems*. doi:10.1002/dac.5602
- [R-170] Valinataj, Mojtaba, Mohammadi, Siamak, Plosila, Juha, Liljeberg, Pasi (2010). A Fault-Tolerant and Congestion-Aware Routing Algorithm for Networks-on-Chip. *13th IEEE Symposium on Design and Diagnostics of Electronic Circuits and Systems*. doi:10.1109/DDECS.2010.5491798
- [R-171] Wang, Shaocong, Zhang, Xiaoyun, Wang, Changhong, Wu, Ke, Li, Cunlu, Dong, Dezun (2024). DRLAR: A Deep Reinforcement Learning-Based Adaptive Routing Framework for Network-on-Chips. *Computer Networks*. doi:10.1016/j.comnet.2024.110419
- [R-172] Yadav, Challa Muralikrishna, Reddy, B. Naresh Kumar (2026). Reinforcement Learning-Driven Fault-Tolerant Routing for Mesh-Based Network-on-Chip Architectures. *Analog Integrated Circuits and Signal Processing*. doi:10.1007/s10470-026-02584-4
- [R-173] Zhang, Wenfei, Ye, Yaoyao (2021). A Table-Free Approximate \mkbibemphQ -Learning-Based Thermal-Aware Adaptive Routing for Optical NoCs. *IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems*. doi:10.1109/TCAD.2020.2987775
- [R-174] Zhang, Yuan, Jing, Zewei, Yang, Qinghai, Gu, Huaxi, Kwak, Kyung Sup (2026). Layer-Coupled Parity Turn and Adaptive Expected State–Action–Reward–State–Action-based Routing in Three-Dimensional Networks-on-Chip. *Microelectronics Journal*. doi:10.1016/j.mejo.2026.107383
- [R-175] Zhao, Jiahe, Li, Hui, Liu, Feiyang (2022). An Adaptive Routing Method Based on Fuzzy Logic System in Optical Network-on-Chip (ONoC). *2022 20th International Conference on Optical Communications and Networks (ICOCN)*. doi:10.1109/ICOCN55511.2022.9901217

---
*Generated 2026-09-10T14:54:27.757Z by SR Research Workspace · PRISMA 2020 · audit trail of 1220 events attached in reproducibility package.*