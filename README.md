# LHC-ATLAS-jet-calibration-forward-folding

Analysis pipeline for calibrating hadronic jets, developed for my Honours Thesis (Carleton University, 2025) as part of the ATLAS experiment at CERN.  
The project applies the forward folding technique to Monte Carlo–simulated Z+jet events in the ATLAS detector to extract detector effects.

---

## Project Overview
This work focuses on calibrating measurements in the ATLAS detector by extracting two key parameters:

- **Jet Energy Scale (JES):** average calibration factor (how closely measured jets match their true energy)  
- **Jet Energy Resolution (JER):** spread of the detector response (measurement precision)  

The method compares truth-level Monte Carlo jets with reconstructed jets by simulating detector effects and fitting parameters via χ² minimization.

---

## Methodology
1. Build truth-level jet distributions from Monte Carlo simulation  
2. Apply detector effects via Gaussian smearing (convolution)  
3. Perform χ² scans over scale (μ) and resolution (σ) parameters  
4. Fit quadratic functions around χ² minima to extract JES and JER  
5. Estimate uncertainties using error propagation and random seed averaging  

---

## Key Contributions
- Unified approach to determine JES and JER simultaneously  
- Optimized runtime by replacing slow ROOT histogramming with NumPy vectorization  
- Reduced statistical fluctuations with multiple random seeds  
- Produced calibration results consistent with established methods  

---

## Findings
Forward folding produced calibration factors and resolutions consistent with ATLAS models, validating the approach.  
Remaining challenges include limited statistics at high energies and refinement of uncertainty treatment.

---

## Skills Demonstrated
- **Languages/Tools:** Python, NumPy, Matplotlib, Jupyter, ROOT  
- **Techniques:**  
  - Statistical modeling and parameter estimation  
  - Numerical optimization (χ² minimization)  
  - Performance tuning with vectorization  
  - Uncertainty analysis and error propagation  
  - Reproducible scientific workflows  

---

## Repository Structure
- `notebooks/` — Jupyter notebook with main analysis  
- `results/` — Selected plots (χ² scans, JES/JER fits)  
- `requirements.txt` — Python dependencies  
- `LICENSE` — MIT open-source license  

---

## How to Run
```bash
# Clone the repository
git clone https://github.com/yourusername/LHC-ATLAS-jet-calibration-forward-folding.git
cd LHC-ATLAS-jet-calibration-forward-folding

# Install dependencies
pip install -r requirements.txt

# Open the analysis notebook
jupyter notebook notebooks/forward_folding_analysis.ipynb
