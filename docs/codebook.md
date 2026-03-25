# Codebook: IS-Impact E-Learning Dataset

## Study Information

- **Paper**: Uncovering Multiple Pathways to Educator Adoption of E-Learning Tools: A Configurational Analysis Using fsQCA
- **Sample Size**: N = 216 educators
- **Data Collection**: Survey instrument based on IS-Impact model
- **Analysis Method**: Fuzzy-Set Qualitative Comparative Analysis (fsQCA)

---

## Variables

### Outcome Variable

| Variable | Label | Description | Scale | Calibration |
|----------|-------|-------------|-------|-------------|
| `ADOPTION` | E-Learning Tool Adoption | Behavioral adoption of e-learning tools by educators | Composite (mean of adoption items) | Calibrated to fuzzy set [0,1]; anchored at 5 (fully in), 3 (crossover), 1 (fully out) |

### Condition Variables (fsQCA Causal Conditions)

| Variable | Label | Description | Scale | Calibration |
|----------|-------|-------------|-------|-------------|
| `SYS_QUALITY` | System Quality | Perceived quality of the e-learning system (reliability, functionality) | 7-point Likert | Calibrated: 6=fully in, 4=crossover, 2=fully out |
| `INFO_QUALITY` | Information Quality | Perceived quality of content/information in e-learning tools | 7-point Likert | Calibrated: 6=fully in, 4=crossover, 2=fully out |
| `SERVICE_QUALITY` | Service Quality | Quality of support and service provided for e-learning tools | 7-point Likert | Calibrated: 6=fully in, 4=crossover, 2=fully out |
| `INDIVIDUAL_IMPACT` | Individual Impact | Perceived impact of e-learning tools on individual performance | 7-point Likert | Calibrated: 6=fully in, 4=crossover, 2=fully out |
| `ORG_IMPACT` | Organizational Impact | Perceived impact of e-learning tools on organizational outcomes | 7-point Likert | Calibrated: 6=fully in, 4=crossover, 2=fully out |

### Demographic Variables

| Variable | Label | Description | Values |
|----------|-------|-------------|--------|
| `AGE` | Age | Respondent age group | 1=Under 25, 2=25-34, 3=35-44, 4=45-54, 5=55+ |
| `GENDER` | Gender | Respondent gender | 1=Male, 2=Female, 3=Other |
| `EXPERIENCE` | Teaching Experience | Years of teaching experience | 1=<5 years, 2=5-10 years, 3=11-20 years, 4=>20 years |
| `INSTITUTION` | Institution Type | Type of educational institution | 1=University, 2=Community College, 3=K-12, 4=Other |

---

## Survey Items

### System Quality (SYS_QUALITY)
Items rated on 7-point Likert scale (1=Strongly Disagree, 7=Strongly Agree):
1. The e-learning system is reliable
2. The e-learning system is easy to use
3. The e-learning system has all necessary features
4. The e-learning system performs consistently

### Information Quality (INFO_QUALITY)
1. The information provided by the e-learning system is accurate
2. The information is up-to-date and relevant
3. The content is well-organized and clear
4. The information meets my teaching needs

### Service Quality (SERVICE_QUALITY)
1. Technical support is available when needed
2. Support staff resolve problems promptly
3. The institution provides adequate training for e-learning tools
4. Help resources are easy to access

### Individual Impact (INDIVIDUAL_IMPACT)
1. Using e-learning tools improves my teaching effectiveness
2. E-learning tools save me time in lesson preparation
3. E-learning tools enhance my ability to reach students
4. Using e-learning tools increases my productivity

### Organizational Impact (ORG_IMPACT)
1. E-learning tools contribute to overall institutional effectiveness
2. The institution benefits from faculty use of e-learning
3. E-learning adoption improves student outcomes institution-wide
4. E-learning tools support the institution's strategic goals

### Adoption (ADOPTION - Outcome)
1. I regularly use e-learning tools in my courses
2. I intend to continue using e-learning tools
3. I would recommend e-learning tools to colleagues
4. E-learning tools are an integral part of my teaching

---

## Calibration Procedure

All raw Likert scores were calibrated to fuzzy-set membership scores [0, 1] using the `calibrate()` function in the `pyfsca` library:

```python
from pyfsca import calibrate

# Three anchors: fully-in threshold, crossover point, fully-out threshold
df['SYS_QUALITY_fs'] = calibrate(df['SYS_QUALITY'], 6, 4, 2)
```

Calibration thresholds follow Ragin (2008) recommendations:
- **Fully in (0.95)**: Score >= 6 (high agreement)
- **Crossover (0.5)**: Score = 4 (neither in nor out)
- **Fully out (0.05)**: Score <= 2 (low agreement)

---

## Missing Data

- Original N = 230; cleaned N = 216 after removing:
  - Incomplete responses (n = 8)
  - Straightline responses (n = 4)
  - Outliers confirmed by Mahalanobis distance (n = 2)

---

## References

Ragin, C. C. (2008). *Redesigning social inquiry: Fuzzy sets and beyond*. University of Chicago Press.

DeLone, W. H., & McLean, E. R. (2003). The DeLone and McLean model of information systems success: A ten-year update. *Journal of Management Information Systems, 19*(4), 9-30.
