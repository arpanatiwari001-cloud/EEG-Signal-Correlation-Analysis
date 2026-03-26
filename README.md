# EEG Signal Analysis: Neural Synchronization & Connectivity

This project explores how we can use mathematical tools—specifically **Correlation** and **Covariance**—to understand brain signals (EEG). It helps determine if different brain regions are "talking" to each other, if one is following the other, or if they are working independently.

## 🧠 Project Overview (The "Why")
When doctors monitor brain waves, they need to identify patterns that indicate health or disease. This module simulates and analyzes three critical neurological states:

1. **Normal Brain Activity:** Random, independent electrical noise across different regions.
2. **Spike Propagation:** A neural discharge (like a "spark") that starts in one area and travels to another with a slight delay.
3. **Seizure Synchronization:** A state where multiple brain regions begin firing in a rhythmic, simultaneous pattern.

---

## 📊 The Mathematical Core
We use **Cross-Correlation ($R_{xy}$)** to measure the relationship between two channels. 



**What does this mean?**
Imagine sliding two signal graphs over each other. If they "match up" perfectly at a certain point, a "Peak" appears on the correlation graph.
* **Peak at Zero:** The signals are happening at the exact same time (Synchronization).
* **Peak to the Side:** One signal is an "echo" of the other, arriving with a **Lag** (Propagation).
* **No Peak:** The signals are unrelated (Random).

---

## 🔍 Technical Terms & Interpretation
If you run this code, you will see three distinct types of output. Here is how to interpret them:

| Technical Case | Graph Characteristics | Clinical Interpretation |
| :--- | :--- | :--- |
| **Random EEG** | A flat, messy line staying near the zero-axis. | **Independent:** Normal resting state; regions are not influencing each other. |
| **Spike Propagation** | A sharp peak shifted to the left or right of the center. | **Traveling Signal:** A discharge is moving from one lobe to another with a measurable delay (Lag). |
| **Seizure Sync** | A very high, repetitive peak centered exactly at zero. | **Hypersynchrony:** A hallmark of seizure activity where the brain fires in unison. |

---

## 🛠️ How the Pipeline Works
The code follows a standard **Biomedical Signal Processing** workflow:

1. **Preprocessing:** Cleaning the signals to remove baseline drift and muscle interference.
2. **Autocorrelation:** Comparing a signal to its own past to find repeating rhythms (like heartbeats or rhythmic seizures).
3. **Cross-Correlation:** Calculating the similarity between Channel A and Channel B across all possible time displacements.
4. **Lag Estimation:** Converting the "sample shift" into real-world time (milliseconds) to see how fast signals travel in the brain.

---

## 🚀 Quick Start & Tech Stack

### 1. Prerequisites
You will need a Python environment with these three core "toolbox" libraries:
* **NumPy:** For high-speed mathematical operations on signal arrays.
* **SciPy:** Used for `correlate` and `gausspulse` functions to analyze and simulate waveforms.
* **Matplotlib:** For generating the 3-tier visual comparison of the brain states.

```bash
pip install numpy matplotlib scipy
