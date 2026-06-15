# GENOME-OS v4.5: Epigenetic Neural Engine

GENOME-OS v4.5 is a self-contained, real-time molecular biology simulation that models chromatin folding, gene regulatory networks (the Central Dogma), and environmental selection pressures. The system is run in tandem with an active machine learning model—a Reinforcement Learning (RSI) agent that attempts to maintain cellular homeostasis through targeted point mutations and epigenetic edits.

---

## Core System Architecture

The simulator is structured into four primary intersecting systems:

### 1. 3D Epigenetic Chromatin Physics
Rather than rendering a static double-helix model, the visualization engine derives its spatial coordinates from the simulated epigenetic state of each locus ($N=180$).
* **Euchromatin (Active Zones):** Unmethylated loci relax. The engine dynamically scales up the horizontal rotational radius and stretches vertical base spacing, modeling open, transcriptionally accessible DNA.
* **Heterochromatin (Silenced Zones):** Highly methylated loci physically condense. The horizontal radius collapses inward by up to 50%, and the vertical interval compresses. Highly methylated zones appear physically packed, darker, and wrapped in histone-like structural rings.

### 2. Central Dogma Transcription & Translation
The simulator parses the nucleotide sequence in real-time using biological boundaries:
* **Transcription Initiation:** The engine scans the genome in triplets for Start Codons (`0-1-2` / `ATG`) and proceeds down the locus chain until encountering a Stop Codon (`1-0-0` / `TAA`) or reaching a structural size limit.
* **Transcription Inhibition:** If any nucleotide within the promoter region has a methylation value above `0.5`, transcription of that gene is blocked.
* **mRNA Particle Emission:** Actively transcribed regions trigger physical transcription events, spawning visual mRNA particles that drift away from the DNA matrix toward the background.
* **Enzymatic Synthesis & Translation Tables:**
  * `2-2-2` (`GGG`) $\rightarrow$ **Metabolic Enzymes (ATP Synthase):** Mitigates base energy depletion.
  * `3-3-3` (`CCC`) $\rightarrow$ **DNA Repair Polymerase:** Reverses cellular damage and restores health.
  * `1-1-1` (`TTT`) $\rightarrow$ **Hsp70 Heat Shock Proteases:** Mitigates stressors and stabilizes chromatin during adverse states.

### 3. Machine Learning RSI Agent (Q-Learning)
An autonomous agent utilizes tabular Q-learning to navigate cellular survival.
* **State Space:** Discretized using a compound key of current ATP levels, structural health, and active environmental parameters.
* **Action Space:** 
  1. *Point Mutation:* Randomly mutates a focused nucleotide base.
  2. *Methylation:* Epigenetically silences a targeted locus.
  3. *Demethylation:* Restores transcriptional access to a locus.
  4. *Homeostatic Repair:* Directly allocates energy toward tissue structural repair.
* **Neural Action-Value Matrix:** The real-time values of the active state-action transitions are plotted on a rolling $4\times4$ heatmap grid in the control panel.

### 4. Environmental Selection Chambers
To evaluate genetic robustness, users can shift the active ecosystem chamber:
* **Standard:** Default homeostatic loss parameters.
* **Hypoxia:** Drastically accelerates ATP depletion, demanding metabolic enzyme upregulation.
* **Radiative Mutagen:** Simulates ionizing radiation, causing elevated stochastic point mutation rates across the genome and increasing DNA structural decay.
* **Oxidative Stress:** Rapidly depletes systemic health, requiring continuous chaperone (Hsp70) expression to survive.

---

## Operating Instructions

### Manual Interactions
* **Point Mutation:** Hover over any nucleotide base on the rotating 3D helix and **Click** to manually cycle through base values ($A \rightarrow T \rightarrow G \rightarrow C$).
* **Epigenetic Silencing:** Hover over any base and hold **Shift + Click** to manually toggle structural methylation (enabling/disabling transcription and folding the localized chromatin segment).
* **Grid Overrides:** Use the status snapshot dots in the right-hand panel to execute sequence overrides on the fly.

### UI Controls
* **INIT SIM / SUSPEND SYSTEM:** Toggles the running clock of the simulation.
* **INJECT HEG (Stress Trigger):** Instantly forces a wave of free radical stress into the system to test genetic adaptive responses.
* **ENGAGE RSI DECAY / DISENGAGE RSI:** Enables or disables the Q-learning agent's operations.
* **Chamber Selectors:** Dynamically switch active selection chambers (Standard, Hypoxia, Mutagen, Oxidative) to monitor phenotypic adaptability.

---

## Development & Deployment

This simulator is built as a highly optimized, dependency-free, zero-asset codebase running purely on native HTML5 Canvas, modern CSS variables, and vanilla JavaScript. 

### To Launch:
1. Save the code as an `.html` file (e.g., `genome_os.html`).
2. Open the file directly in any modern, GPU-accelerated web browser. No local servers, builds, or external node packages are required.
