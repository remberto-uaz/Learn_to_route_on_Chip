## background

Networks-on-Chip (NoC) interconnects constitute the fundamental pillar for communication in many-core processors. As sub-nanometric manufacturing technologies advance, traditional assumptions of deterministic and static adaptive routing algorithms (such as XY routing or Odd-Even) are severely compromised by highly bursty traffic patterns, thermal variability, and structural failures. Machine Learning (ML) and Reinforcement Learning (RL) emerge as data-driven alternatives capable of making dynamic route selection decisions.1.2 RationaleDespite the rapid increase in publications on routing with ML/RL, there is a critical fragmentation in current literature: existing surveys neglect hardware synthesis aspects (silicon area, power consumption, and clock cycle latency), omit the distinction between electrical (2D/3D) and photonic media, or lack a formal framing as Partially Observable Markov Decision Processes and multi-agent systems (Dec-POMDP/MARL). This Comprehensive Review is justified by the need to synthesize empirical FPGA/ASIC synthesis evidence and establish a unified multi-objective evaluation framework.

## rationale

Despite the increase in ML-NoC publications, prior literature presents three severe structural limitations that justify this review:Predominance of outdated or general EDA-oriented reviews: Existing reviews do not categorize modern deep learning architectures nor do they disaggregate the impact on NoC routing with strict clock-cycle constraints (< 1 ns).Absence of realistic hardware cost synthesis: Most ML reviews for NoC focus solely on algorithmic metrics or cycle-exact simulations, omitting real ASIC synthesis data (gate equivalents, kGE) and FPGA prototyping.Lack of simultaneous consideration of physical media and multiple objectives: Previous reviews analyze planar 2D, 3D (TSV-based), or photonic architectures in isolation without systematically crossing the ML paradigm with the transmission medium and multi-objective goals (latency, power, thermal gradient, degradation/aging, resilience, and security).

## questions

RQ1: What are the most widely used ML paradigms and mathematical abstractions (Dec-POMDP, MARL, SVR, ACO) for addressing adaptive routing in NoCs?

RQ2: How does the effectiveness of learning policies vary depending on the underlying physical medium (2D electrical, 3D electrical, or silicon photonic)?

RQ3: What are the area (kGE), power (W), and decision latency (ns) overheads reported in ASIC/FPGA hardware synthesis for these intelligent routers?

RQ4: What are the primary methodological gaps, scalability bottlenecks, and evaluation biases present in the current literature?

## objectives

To systematically evaluate and synthesize NoC routing methods based on machine learning (RL, regression, and metaheuristics), analyzing their multi-objective performance and quantitatively measuring their hardware implementation overheads in FPGA and ASIC.

## eligibility

Inclusion Criteria (IC)

IC1: Original research studies published in peer-reviewed indexed journals or high-impact conference proceedings (Q1/Q2 or IEEE/ACM core).
IC2: Articles that explicitly propose or evaluate an NoC routing algorithm guided or supervised by ML, RL, or metaheuristic models.
IC3: Articles that include quantitative network performance metrics (latency, throughput, packet loss) or hardware synthesis data (FPGA or ASIC).
IC4: Publications written in the English language.

Exclusion Criteria (EC)
EC1: Studies on routing in wide area networks (WAN), wireless sensor networks (WSN), or software-defined networks (SDN) that do not apply to on-chip hardware constraints (NoC).
EC2: Studies using ML for NoC tasks other than routing (e.g., task mapping, chip testing, or traffic classification only).
EC3: Purely descriptive papers, patents, extended abstracts, presentations, or tutorials lacking empirical validation.
EC4: Publications that do not provide clear information regarding the underlying router topology or architecture.

## sources

The following search strings have been adapted according to the specific logical operators and syntax of each search engine:IEEE Xplore ACM Digital LibraryWiley Online LibraryMDPI (Search Engine)ScienceDirect (Elsevier)SpringerLink

## search

The following search strings have been adapted according to the specific logical operators and syntax of each search engine:
IEEE
(("Document Title":*NoC) OR ("Document Title":Network*-on-Chip) OR ("Document Title":interconnect*)) AND ("Document Title":*routing) AND ("All Metadata":*learning)

ACM
19 Results for: [Title: network-on-chip] AND [Title: learning] AND [E-Publication Date: (01/01/2015 TO 12/31/2026)]

ScienceDirect
TITLE-ABS-KEY((NoC OR "Network-on-Chip" OR Interconnect) AND routing AND learning)
Engineering and computer science, 2015-2026

Wiley
*NoC OR "Network*-on-Chip" AND *routing AND *learning
OPEN ACCESS( ELECTRICAL  EnGIENEER) (COMPUTER SCIENCE) 2015 2026

mdpi
Keywords = noc routing learning

Springer

Title (*NoC OR "Network*-on-Chip" OR Interconnect*) AND *routing Keywords (*learning)
2015-2026

## selection

Reviewer 1 (First Reviewer – Selection and Extraction): Dr. Bernardo Ibarra Infante.
Reviewer 2 (Second Reviewer – Independent Selection and Extraction): Dr. Remberto Sandoval Aréchiga.Reviewer 3 (Third Reviewer – Arbitrator and Tie-breaker): Dr. Víktor Iván Rodríguez Abdalá.

## extraction

ML Model Taxonomy and Formalization (Aligned with RQ1)
ML Paradigm	Mathematical Abstraction / Formalization	State Variables / Observed Inputs	Advantages in NoC	Disadvantages / Overheads	 Underlaying technology: wired, optical, wireless, 2D, 3D, interposer, 3D, 2.5D References

## quality

Quality Assessment Criteria (QA) Each candidate study will be evaluated using a weighted quality questionnaire (0 to 2 points per item):QA1: Is the learning model (state space, actions, reward, or regression function) formally defined mathematically?QA2: Does the study use standardized traffic benchmarks or patterns (SPLASH-2, PARSEC, Synthetic Bursty/Hotspot) instead of uniform traffic alone?QA3: Are simulation tools specified (e.g., BookSim, Noxim, Gem5, Ratatoskr) along with router parameters (e.g., buffer depth, VCs, pipeline depth)?QA4: Are explicit hardware synthesis results provided (e.g., Synopsys DC, Cadence Genus, Vivado) reporting area (kGE), power, or latency?6.2 Bias Assessment CriteriaEvaluation Bias: Over-reliance on evaluation under synthetic uniform traffic, which conceals saturation caused by burstiness.Distribution Shift / Overfitting Bias: Regression/SVR models or DRL agents evaluated solely under the same injection distribution used during training.Overhead Omission Bias: Evaluating gains in network latency without accounting for the additional clock cycles inserted by the model's decision logic into the router pipeline.

## synthesis

Thematic and Narrative Synthesis: Disaggregation of the theoretical framework (MDP vs. Dec-POMDP/MARL) and analysis of mitigation mechanisms (logic distillation, linear function approximation).1. Comparative Quantitative Tabulation: Generation of normalized tables of hardware synthesis costs. For area normalization to Gate Equivalents (GE), the standard formula will be applied:2. Meta-Analysis Feasibility: Due to the heterogeneity of simulators, clock frequencies, technology nodes (ranging from 45 nm to 14 nm), and traffic types, a direct quantitative statistical meta-analysis is not feasible. Instead, a cross-study empirical comparative analysis will be conducted across technology ranges and normalized performance metrics.

## timeline

2015-2016 (Except for prior knowledge and IEEE)