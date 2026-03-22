# 🦊 Ninetails Engine (Little Fox)
**Adaptive Behavioral Governance for AI Agents**

[![Paper](https://img.shields.io/badge/Paper-SSRN-blue.svg)](https://ssrn.com/abstract=6453579) 
[![Status](https://img.shields.io/badge/Status-Active_Development-success.svg)](#) 
[![Release](https://img.shields.io/badge/Release-Coming_Soon-orange.svg)](#)

> A quantitative risk scoring framework derived from quantitative trading risk management (decision tree pruning), designed to solve the safety-utility dilemma in LLM-powered autonomous agents.

## 📌 Overview

Current AI agent frameworks typically handle risk through "Capability Restriction" (an embargo paradigm)—treating safety as a binary classification problem where tools are either fully available or completely disabled. 

**Ninetails Engine (Little Fox)** reframes agent governance through a **"Tariff" paradigm**. Instead of blanket prohibitions, every action is subject to a continuous, quantitative risk assessment that determines the appropriate level of human oversight. By separating the stochastic LLM inference from a deterministic rule engine, this framework eliminates judgment drift and prompt-injection vulnerabilities in the governance pathway.

## ✨ Core Innovations

* **Tariffs, Not Embargo:** Replaces static permissioning with monotonic tiered execution policies (from autonomous execution to multi-step critical delays).
* **Deterministic Adjudication:** The decision engine operates independently from the governed LLM, ensuring safety mechanisms do not degrade during complex reasoning chains.
* **6-Dimensional Risk Scoring:** Evaluates every action across Operation Risk, External Exposure, Financial Impact, Irreversibility, Context Deviation, and Historical Frequency.
* **Shadow-Mode Calibration:** Adapts the "backtest-before-live" principle from quantitative finance, allowing data-driven threshold correction prior to live enforcement.

## 🏗️ Architecture

The framework is built on a 5-layer architecture, mapping directly to quantitative trading counterparts:
1.  **L1 - Infrastructure:** Inter-process communication and multi-model routing.
2.  **L2 - Request Standardization:** Intent normalization.
3.  **L3 - Context Awareness:** Environmental state classification (Routine vs. Sensitive).
4.  **L4 - Decision Engine:** The core 3-layer scoring pipeline (Signal filtering, Synthesis, Adjudication).
5.  **L5 - Adaptive Learning:** Feedback-driven parameter evolution and global circuit breakers.

```mermaid
flowchart TD
    classDef layerBox fill:#f9f9fb,stroke:#d3d3d9,stroke-width:2px,stroke-dasharray: 5 5,rx:10,ry:10;
    classDef nodeBox fill:#ffffff,stroke:#4a5568,stroke-width:2px,rx:5,ry:5,color:#1a202c,font-weight:bold;
    classDef highlightBox fill:#ebf8ff,stroke:#3182ce,stroke-width:2px,rx:5,ry:5,color:#2b6cb0,font-weight:bold;
    classDef alertBox fill:#fff5f5,stroke:#e53e3e,stroke-width:2px,rx:5,ry:5,color:#c53030,font-weight:bold;

    %% Data Flow Input
    Input(["LLM / Agent\nAction Request"]):::highlightBox
    
    subgraph L1 ["Layer 1: Infrastructure (Network & Routing)"]
        direction LR
        IPC["Inter-Process Communication"]:::nodeBox
        MR["Multi-Model Router"]:::nodeBox
        IPC <--> MR
    end

    subgraph L2 ["Layer 2: Request Standardization (Normalization)"]
        direction LR
        Parsing["Intent Parsing"]:::nodeBox
        Protocol["Standard Protocol\nConversion"]:::nodeBox
        Parsing --> Protocol
    end

    subgraph L3 ["Layer 3: Context Awareness (State Classification)"]
        direction LR
        State["Env State Checker"]:::nodeBox
        Tagging["Context Tagging\n(Routine / Sensitive)"]:::nodeBox
        State --> Tagging
    end

    subgraph L4 ["Layer 4: Decision Engine (Quantitative Adjudication)"]
        direction TB
        subgraph P1 ["Phase 1: Signal Filtering"]
            Filter["Sanity Checks &\nRule Constraints"]:::nodeBox
        end
        subgraph P2 ["Phase 2: Risk Scoring Synthesis"]
            direction LR
            R1["Operational Risk"]
            R2["External Exp."]
            R3["Financial Impact"]
            R4["Irreversibility"]
            R5["Context Deviation"]
            R6["Historical Freq."]
        end
        subgraph P3 ["Phase 3: Tariff Adjudication"]
            Tariff["Monotonic Tiered Policy"]:::highlightBox
        end
        P1 --> P2 --> P3
    end

    subgraph L5 ["Layer 5: Adaptive Learning (Evolution & Safety)"]
        direction LR
        Shadow["Shadow-Mode Calibration\n(Backtesting)"]:::nodeBox
        Breaker["Global Circuit Breaker\n(Anomaly Halt)"]:::alertBox
        Param["Parameter Evolution"]:::nodeBox
        Shadow --> Param
        Breaker -.->|Halt| L4
    end

    %% Main Flow
    Input ==> L1
    L1 ==> L2
    L2 ==> L3
    L3 ==> L4
    L4 ==>|Execution Feedback| L5
    L5 -.->|Dynamic Weights| L4
    
    %% Output policies
    Out1(["Tier 0: Auto Execute"]):::nodeBox
    Out2(["Tier 1: Time Delay"]):::nodeBox
    Out3(["Tier 2: Human Adjudication"]):::alertBox

    P3 ==> Out1
    P3 ==> Out2
    P3 ==> Out3
```

## 🚀 Status & Roadmap

**Current Status: Pre-Release / Paper Published**

The theoretical foundation and empirical analysis of this framework have been published as a pre-print on SSRN:
🔗 *[https://ssrn.com/abstract=6453579](https://ssrn.com/abstract=6453579)*

*Companion Paper: [Frontiers of Neuro-symbolic Fusion in Quantitative Finance](https://ssrn.com/abstract=6118946)*

**Next Steps:**
We are currently cleaning up the configuration files and performing a final security review. A **minimal reproducible open-source profile**, including the core 3-layer decision engine and the fixed-weight 6-dimensional scoring model, will be released in this repository shortly. 

Please `Watch` and `Star` this repository to be notified of the code release.

## 📝 Citation

If you find this framework useful for your research, please cite our paper:

```bibtex
@article{sun2026adaptive,
  title={Adaptive Behavioral Governance for AI Agents: A Quantitative Risk Scoring Framework Derived from Trading Decision Tree Pruning},
  author={Sun, Hua},
  journal={SSRN Electronic Journal},
  year={2026},
  month={March}
}
```

## 📬 Contact

**Howard Sun**
Independent Researcher
📧 howardsun199@gmail.com
