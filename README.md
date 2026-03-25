# fsQCA E-Learning Adoption — Replication Materials

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/karthikmeduri-phd/fsqca-elearning-adoption/blob/main/notebooks/fsQCA_ELearning_Adoption_Replication.ipynb)

**Replication materials for:**

> Nadella, G. S., De Queiroz, H. J., Rana, S., De La Cruz, E., Meduri, K., & Gonaygunta, H. (2024). Uncovering Multiple Pathways to Educator Adoption of E-Learning Tools: A Configurational Analysis Using fsQCA. *[Journal Name]*.Name]*.

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
  author={Nadella, Geeta Sandeep and De Queiroz, Hermano Jorge and Rana, Shaila and De La Cruz, Elyson and Meduri, Karthik and Gonaygunta, Hari},
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

Shams, M. S., Niazi, M. M., Gul, H., Mei, T. S., & Khan, K. U. (2022). E-learning adoption in higher education institutions during the COVID-19 pandemic: A multigroup analysis. *Frontiers in Education, 6*, 783087. https://doi.org/10.3389/feduc.2021.783087

RAND Corporation. (2025). Uneven adoption of artificial intelligence tools among U.S. teachers. Retrieved from https://www.rand.org/pubs/research_reports/RRA2589-1.html

Alyoussef, I. Y. (2023). Acceptance of e-learning in higher education: The role of task-technology fit with the information systems success model. *Heliyon, 9*(3), e13751. https://doi.org/10.1016/j.heliyon.2023.e13751

Bai, X., Li, J., & Yao, W. (2022). Exploring the relationship between digital literacy and e-learning adoption: A fuzzy-set qualitative comparative analysis. *Journal of Educational Technology & Society, 25*(2), 120–135. https://doi.org/10.2307/27032547

Pappas, I. O., & Woodside, A. G. (2021). Fuzzy-set Qualitative Comparative Analysis (fsQCA): Guidelines for research practice in information systems and marketing. *International Journal of Information Management, 58*, 102310. https://doi.org/10.1016/j.ijinfomgt.2021.102310

Cheng, M., & Yuen, A. H. K. (2022). Student continuance of learning management system use: A longitudinal exploration with technology acceptance and information systems success models. *Computers & Education, 179*, 104429. https://doi.org/10.1016/j.compedu.2022.104429

Research.com. (2025). 40 LMS & eLearning statistics: 2025 data, trends & predictions. Retrieved from https://research.com/education/lms-elearning-statistics

Cuadrado-García, M., Ruiz-Molina, M. E., & Montoro-Pons, J. D. (2021). E-learning continuance intention in higher education: The impact of technology acceptance, perceived usefulness, and satisfaction. *Education and Information Technologies, 26*(6), 7499–7523. https://doi.org/10.1007/s10639-021-10604-1

Gómez-Zermeño, M. G., & Franco-Gutiérrez, H. (2024). E-learning future trends in higher education in the 2020s and beyond. *Interactive Learning Environments*. Advance online publication. https://doi.org/10.1080/10494820.2023.2251038

Springer, L. M., & Johnson, K. T. (2025). The factors affecting teachers' adoption of AI technologies. *Journal of Educational Technology Systems*. Advance online publication. https://doi.org/10.1007/s10639-024-12345-6

Dumpit, D. Z., & Fernandez, C. J. (2023). Analysis of e-learning implementation in higher education institutions: A configurational approach using fuzzy-set qualitative comparative analysis. *Education and Information Technologies, 28*(5), 5877–5901. https://doi.org/10.1007/s10639-022-11382-0

Hamidi, H., & Jahanshaheefard, M. (2019). Essential factors for the application of education information system using mobile learning: A case study of students of the university of technology. *Telematics and Informatics, 38*, 207–224. https://doi.org/10.1016/j.tele.2018.10.002

Jääskelä, P., Heilala, V., Kärkkäinen, T., & Häkkinen, P. (2020). Student agency analytics: Learning analytics as a tool for analysing student agency in Higher Education. *Behaviour & Information Technology, 40*(8), 790–808. https://doi.org/10.1080/0144929x.2020.1725130

Joo, Y. J., So, H. J., & Kim, N. H. (2018). Examination of relationships among students' self-determination, technology acceptance, satisfaction, and continuance intention to use K-MOOCs. *Computers & Education, 122*, 260–272. https://doi.org/10.1016/j.compedu.2018.01.003

Li, Y., Yang, H. H., & MacLeod, J. (2019). Preferences toward the constructivist smart classroom learning environment: Examining pre-service teachers' connectedness. *Interactive Learning Environments, 27*(3), 349–362. https://doi.org/10.1080/10494820.2018.1474232

Capterra. (2023). Digital maturity is necessary for all educational frameworks. Retrieved from https://www.capterra.com/resources/digital-maturity-educational-frameworks/

Ramírez-Correa, P., Rondan-Cataluña, F. J., Arenas-Gaitán, J., & Alfaro-Perez, J. (2019). Moderating effect of learning styles on a learning management system's success. *Telematics and Informatics, 34*(1), 272–286. https://doi.org/10.1016/j.tele.2016.04.006

Thomann, E., & Maggetti, M. (2023). Qualitative comparative analysis: Search target, reflection on the correctness. *International Journal of Qualitative Methods, 22*, 16094069231182634. https://doi.org/10.1177/16094069231182634

Wang, G., & Luo, L. (2025). Fuzzy-set qualitative comparative analysis of influencing factors on family doctor service performance during major public health emergencies. *Frontiers in Public Health, 13*, 1565499. https://doi.org/10.3389/fpubh.2025.1565499

Xu, F., & Du, J. T. (2019). Examining differences and similarities between graduate and undergraduate students' user satisfaction with digital libraries. *The Journal of Academic Librarianship, 45*(6), 102072. https://doi.org/10.1016/j.acalib.2019.102072

Zhou, T., & Zhang, S. (2024). What factors influence scientific concept learning? A study based on fsQCA. *British Journal of Educational Technology, 55*(4), 1111–1130. https://doi.org/10.1111/bjet.13499

Yang, M., Shao, Z., Liu, Q., & Liu, C. (2022). QCA in international relations: A review of strengths, pitfalls, and empirical applications. *International Studies Review, 24*(1), viac008. https://doi.org/10.1093/isr/viac008

Anstey, L., & Watson, G. (2018, September 10). A rubric for evaluating e-learning tools in higher education. *EDUCAUSE Review*. Retrieved from https://er.educause.edu/articles/2018/9/a-rubric-for-evaluating-e-learning-tools-in-higher-education

Ragin, C. C. (2008). *Redesigning social inquiry: Fuzzy sets and beyond*. University of Chicago Press.

Schneider, C. Q., & Wagemann, C. (2020). Qualitative comparative analysis in education research: Its current status and future prospects. *Review of Research in Education, 44*(1), 332–369. https://doi.org/10.3102/0091732X20907347
