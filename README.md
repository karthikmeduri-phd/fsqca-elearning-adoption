# fsQCA E-Learning Adoption — Replication Materials

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/karthikmeduri-phd/fsqca-elearning-adoption/blob/main/notebooks/fsQCA_ELearning_Adoption_Replication.ipynb)

**Replication materials for:**

> Meduri, K. (2024). Uncovering Multiple Pathways to Educator Adoption of E-Learning Tools: A Configurational Analysis Using fsQCA. *[Journal Name]*.

---

## Overview

This repository contains all data and code necessary to fully reproduce the findings reported in the paper. The study applies Fuzzy-Set Qualitative Comparative Analysis (fsQCA) to investigate how combinations of IS-Impact dimensions (system quality, information quality, service quality, individual impact, and organizational impact) lead to educator adoption of e-learning tools.

**Key findings:** The analysis identifies multiple equifinal configurations (pathways) to high e-learning adoption, demonstrating that no single factor is necessary or sufficient — different combinations of conditions lead to the same outcome.

---

## Repository Structure

```
fsqca-elearning-adoption/
├── data/
│   └── IS-Impact-Clean-DataSet-08292023.xlsx   # Cleaned survey dataset (N=216)
├── notebooks/
│   └── fsQCA_ELearning_Adoption_Replication.ipynb  # Full analysis notebook
├── outputs/                                    # Generated figures and tables
├── docs/
│   └── codebook.md                             # Variable descriptions and calibration
├── requirements.txt                            # Python dependencies
├── LICENSE                                     # MIT License
├── CITATION.cff                                # Citation metadata
└── README.md                                   # This file
```

---

## Data

- **File**: `data/IS-Impact-Clean-DataSet-08292023.xlsx`
- **Sample**: N = 216 educators (cleaned from N = 230)
- **Instrument**: Survey based on the IS-Impact model (DeLone & McLean, 2003)
- **Variables**: 5 causal conditions + 1 outcome (see `docs/codebook.md`)
- **Collection period**: August 2023

See [`docs/codebook.md`](docs/codebook.md) for full variable descriptions, survey items, and calibration details.

---

## Reproducing the Analysis

### Option A: Google Colab (Recommended — No Installation Required)

1. Click the **Open in Colab** badge above
2. In Colab, go to **Runtime → Run all**
3. When prompted, upload `data/IS-Impact-Clean-DataSet-08292023.xlsx` from this repository
4. All outputs will be generated in the notebook

### Option B: Local Python Environment

#### Prerequisites
- Python 3.10+
- pip

#### Setup

```bash
# Clone the repository
git clone https://github.com/karthikmeduri-phd/fsqca-elearning-adoption.git
cd fsqca-elearning-adoption

# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook notebooks/fsQCA_ELearning_Adoption_Replication.ipynb
```

#### Running the Analysis

1. Open `notebooks/fsQCA_ELearning_Adoption_Replication.ipynb`
2. Run all cells in order (Cell → Run All)
3. Outputs will be saved to `outputs/`

---

## Dependencies

All dependencies are pinned in `requirements.txt`. Key packages:

| Package | Version | Purpose |
|---------|---------|----------|
| `pandas` | 2.1.4 | Data manipulation |
| `numpy` | 1.26.2 | Numerical computing |
| `pyfsca` | 0.1.3 | fsQCA calibration and analysis |
| `matplotlib` | 3.8.2 | Visualization |
| `seaborn` | 0.13.0 | Statistical plots |
| `openpyxl` | 3.1.2 | Excel file reading |
| `jupyter` | 1.0.0 | Notebook environment |

---

## Analysis Steps

The notebook performs the following steps in order:

1. **Data Loading** — Load and inspect the IS-Impact dataset
2. **Descriptive Statistics** — Summary statistics and distributions
3. **Fuzzy-Set Calibration** — Convert Likert scores to fuzzy-set membership [0,1]
4. **Necessity Analysis** — Test each condition for necessity
5. **Sufficiency Analysis** — Truth table construction and Boolean minimization
6. **Solution Interpretation** — Parse and interpret fsQCA solutions
7. **Visualization** — XY plots, coverage/consistency charts
8. **Robustness Checks** — Frequency/consistency threshold sensitivity

---

## Expected Outputs

After running the notebook, the following files will appear in `outputs/`:

- `truth_table.csv` — Raw truth table with consistency scores
- `necessity_results.csv` — Necessity analysis results
- `solution_summary.txt` — Parsimoni ous, intermediate, and complex solutions
- `xy_plot_*.png` — XY scatter plots for each sufficient configuration
- `coverage_consistency_chart.png` — Solution coverage and consistency visualization

---

## Citation

If you use these materials in your research, please cite:

```bibtex
@article{meduri2024fsqca,
  title={Uncovering Multiple Pathways to Educator Adoption of E-Learning Tools: A Configurational Analysis Using fsQCA},
  author={Meduri, Karthik},
  journal={[Journal Name]},
  year={2024},
  doi={[DOI]}
}
```

See [`CITATION.cff`](CITATION.cff) for citation metadata in CFF format.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

The dataset (`data/IS-Impact-Clean-DataSet-08292023.xlsx`) is shared for academic replication purposes only.

---

## Contact

- **Author**: Karthik Meduri
- **GitHub**: [@karthikmeduri-phd](https://github.com/karthikmeduri-phd)

---

## References

DeLone, W. H., & McLean, E. R. (2003). The DeLone and McLean model of information systems success: A ten-year update. *Journal of Management Information Systems, 19*(4), 9–30.

Fiss, P. C. (2011). Building better causal theories: A fuzzy set approach to typologies in organization research. *Academy of Management Journal, 54*(2), 393–420.

Ragin, C. C. (2008). *Redesigning social inquiry: Fuzzy sets and beyond*. University of Chicago Press.

Ragin, C. C. (2009). Qualitative comparative analysis using fuzzy sets (fsQCA). In B. Rihoux & C. C. Ragin (Eds.), *Configurational comparative methods* (pp. 87–121). Sage.
