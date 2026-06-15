# GENOME-OS: Metabolic Virtual Machine (MVM)

**GENOME-OS** is a research-oriented, in-silico simulation that treats a synthetic DNA sequence as **executable code**. Instead of viewing DNA as a static string, this system interprets it via a **Metabolic Virtual Machine (MVM)** where specific codons act as functional opcodes to maintain the "health" and "energy" of a digital cell.

The simulation is governed by a **Recursive Self-Improving (RSI) Q-Learning Agent** that learns to "program" the genome to maximize cellular survival under environmental stress.

![Genome Simulation](https://img.shields.io/badge/Simulation-In--Silico-blue)
![AI-Logic](https://img.shields.io/badge/Logic-RSI--Q--Learning-orange)
![Tech](https://img.shields.io/badge/Tech-HTML5--Canvas-green)

---

## 🧬 How It Works

### 1. The Metabolic Virtual Machine (MVM)
The genome is composed of 120 base pairs. The MVM scans this sequence for **Functional Codons** (triplets) that influence the cell's phenotype:

| Codon | Action | Biological Equivalent |
| :--- | :--- | :--- |
| `GCG` | **METABOLIC_BOOST** | Increases ATP (Energy) production. |
| `ATT` | **STRUCTURAL_FIX** | Repairs Structural Integrity (Health). |
| `CAT` | **STRESS_SHIELD** | Slows down metabolic decay. |
| `GGG` | **REPLICATE** | Signals a successful generation cycle. |

### 2. Phenotype-Driven Reward
Unlike traditional models that optimize for sequence patterns, GENOME-OS optimizes for **Survival Time**. 
*   **ATP (Energy)** decays over time.
*   **Health** decays as the cell ages.
*   If either reaches 0, the cell "expires," and the agent receives a final reward based on the total lifecycle duration.

### 3. RSI Q-Learning Agent
The agent utilizes a Q-Table to determine which mutations will result in a more stable metabolic state.
*   **State:** A combination of the current metabolic health and local k-mer sequences.
*   **Action:** Point mutations (A, T, G, C) on the genome.
*   **RSI Logic:** The agent monitors its own learning progress. If the "Survival Time" plateaus across generations, the agent triggers an **Entropy Spike**, increasing its `epsilon` (exploration rate) to force the discovery of new genomic strategies.

---

## 🚀 Features

-   **Real-time 3D Visualization:** A procedural DNA double helix that reflects current genomic mutations in real-time.
-   **Heads-Up Display (HUD):** Live tracking of ATP levels, Structural Integrity, and Fitness (Q-value).
-   **Warp Speed Learning:** The agent executes multiple mutation/evaluation cycles per animation frame to accelerate evolution.
-   **Automated Generations:** The system automatically resets and iterates, tracking the "Best Survival Time" achieved across the evolutionary timeline.

---

## 🛠️ Installation & Usage

Since GENOME-OS is built using a standalone HTML5/JavaScript architecture, no installation is required.

1.  Save the code as `index.html`.
2.  Open the file in any modern web browser (Chrome, Firefox, or Edge recommended).
3.  Click **"RUN SIMULATION"** to begin the evolutionary process.

### Controls
-   **Run/Halt Simulation:** Toggle the execution of the Metabolic VM.
-   **Visuals:** Drag to orbit the DNA helix; the colors represent the four Nitrogenous Bases (A, T, G, C).

---

## 🔬 Research Basis

This simulation is inspired by recent breakthroughs in:
-   **Synthetic Genomics:** The concept of "Minimal Genomes" (e.g., JCVI-syn3.0) where every gene is essential for life.
-   **Reinforcement Learning in Proteomics:** Using AI to predict how sequence changes affect protein folding and cellular function.
-   **In-Silico Evolution:** Simulating metabolic pathways to predict evolutionary outcomes before wet-lab testing.

---

## 📜 License
This project is open-source and intended for educational and research purposes. Feel free to fork and innovate.

> **Note:** This is a conceptual simulation. While based on biological principles, it is a simplified model of metabolic complexity designed to demonstrate AI-driven genomic optimization.
