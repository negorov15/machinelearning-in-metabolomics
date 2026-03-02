# Metabolmics in Biomedical Research

This repository collects a series of Jupyter notebooks and supporting code used to explore machine‑learning techniques on publicly available metabolomics datasets from the MetaboLights (MTBLS) repository.

Our goal is to reproduce and extend experiments described in [a Springer article](https://link.springer.com/article/10.1007/s11306-019-1612-4) on two cohort studies (MTBLS404 and MTBLS90) to evaluate supervised classification pipelines and strategies for handling missing data.

All modelling is performed with scikit‑learn (see https://scikit-learn.org/stable/supervised_learning.html) together with common scientific libraries such as pandas, numpy and matplotlib.

---

## Projects overview

Each top‑level directory corresponds to a separate experimental theme.  The notebooks inside can be executed standalone and are designed for exploration and teaching.

1. **PROJECT_1 – Classification & multivariate modelling**
   - Workflows for three different supervised classifiers: partial least squares followed by a small neural network (PLS‑ANN), random forest and a linear support vector machine (SVM).
   - Notebooks:
     * `PLS_ANN_MTBLS404.ipynb` – implements the PLS‑ANN pipeline on dataset MTBLS404.
     * `RF_MTBLS90.ipynb` – random forest on dataset MTBLS90.
     * `SVMLin_MTBLS90.ipynb` – linear SVM on MTBLS90.

2. **PROJECT_2 – Data imputation experiments**
   - Investigates several strategies for handling missing values in metabolomics tables: mean/median filling, k‑nearest neighbours, matrix factorization, etc.
   - Notebooks:
     * `impute_MTBLS404.ipynb` – applies imputation methods to the 404‑compound dataset.
     * `impute_MTBLS90.ipynb` – analogous experiments on the 90‑compound set.

Data are stored in `/data`. Refer to `requirements.txt` for the minimal Python packages needed for this repository.

---

## Data and Preprocessing

### MTBLS404
We analyzed the dataset with the study ID MTBLS404. This dataset comprises measurements from 183 adults using liquid chromatography coupled with mass spectrometry (LC-MS). Additional information about the age, body mass index (BMI) and sex of the patients is also provided.

### MTBLS90
This dataset includes plasma LC–MS measurements of 189 named metabolites from 968 individuals (483 females, 485 males), all aged 70, from the PIVUS cohort—a community-based epidemiological study in Uppsala, Sweden. No sample in both datasets had a missing peak for any of the metabolites, therefore, no values were to be imputed. No additional preprocessing of the data was done.


The goal of the classification was to discriminate between the sex of the patients.


Links to the datasets:

- **MTBLS90** - https://www.ebi.ac.uk/metabolights/editor/MTBLS90/descriptors
- **MTBLS404** – https://www.ebi.ac.uk/metabolights/editor/MTBLS404/descriptors

---

## Getting started

1. **Clone the repository** to your local machine.

2. **Create and activate a virtual environment** (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies** for whichever project you wish to run:

   ```bash
   pip install -r requirements.txt
   ```

4. **Launch a Jupyter server**:

   ```bash
   jupyter lab        # or notebook
   ```

   Then open any of the `.ipynb` files in the browser or via VS Code’s notebook editor.

---

## Usage notes

- Notebooks are written to be executed sequentially, with explanatory text and code cells.  Feel free to tweak parameters, swap datasets, or add new classifiers.
- Data files are relatively small and checked into source control; you can also replace them with fresh exports if desired.

### Example workflow

1. Activate environment and install dependencies.
2. Run `PROJECT_1/PLS_ANN_MTBLS404.ipynb` end to end.
3. Review generated plots in `PROJECT_1/report`.
4. Duplicate the notebook to a new file to experiment with different ML models or preprocessing steps.

---

## Authors

- **Nikolai Egorov** – analysis of MTBLS90 dataset
- **Mauriz Lichtenshtein** – analysis of MTBLS404 dataset

---
