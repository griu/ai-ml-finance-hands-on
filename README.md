# Data Analysis, AI and Machine Learning in Finance

## Course Materials — Practical Block

**Instructor:** Ferran Carrascosa
**Language:** English
**Audience:** Master's students in Economics, Business Administration and Finance

---

## What is this?

This folder contains the datasets, notebooks and support files for the practical sessions of the course module on Data Analysis, AI and Machine Learning in Finance.

The materials cover:
- **Session 1:** Introduction to Python for finance students
- **Session 2:** Descriptive statistics, EDA, and modelling table construction
- **Session 3:** Baseline models, decision trees, XGBoost, validation and business interpretation

---

## Software Installation

Before creating the Python environment, install these three tools:

- **Visual Studio Code (VS Code)** for editing notebooks and project files
- **Anaconda or Miniconda** for managing Python environments
- **Git** for cloning and updating the repository

### 1. VS Code

**Windows**

- Download and install VS Code from the official Microsoft website.
- During installation, it is useful to enable "Add to PATH", "Open with Code" in the file explorer, and "Register Code as an editor for supported file types".

**macOS (Intel or Apple Silicon / M-series)**

- Download the macOS build of VS Code from the official Microsoft website.
- Apple Silicon users should prefer the Apple Silicon build when available.
- Move VS Code to the `Applications` folder and open it once to complete the first-run setup.

**Recommended VS Code extensions for these notebooks**

- `Python` by Microsoft
- `Jupyter` by Microsoft
- `Pylance` by Microsoft

These extensions cover notebook execution, kernel selection, autocomplete, linting and variable inspection for the course workflow.

### 2. Anaconda or Miniconda

**Windows**

- Install either **Anaconda** if you want a full scientific Python distribution, or **Miniconda** if you prefer a lighter installation.
- Keep the default settings unless your institution has a specific policy.
- After installation, open **Anaconda Prompt** or another terminal where `conda` is available.

**macOS (Intel or Apple Silicon / M-series)**

- Install the correct macOS version for your processor:
- Intel Mac: x86_64 installer
- Apple Silicon Mac: arm64 / Apple Silicon installer
- Anaconda and Miniconda both work; Miniconda is usually the lighter option.
- After installation, open a new Terminal and confirm Conda is available:

```bash
conda --version
```

### 3. Git Client

**Windows**

- Install **Git for Windows**.
- The default installation options are usually appropriate for students.
- A practical setup is to allow Git from the command line and keep Git Bash available.

**macOS (Intel or Apple Silicon / M-series)**

- Install Git using Apple Command Line Tools, Homebrew or the official Git installer.
- Confirm installation with:

```bash
git --version
```

### Basic configuration to use VS Code, Conda and Git together

1. Clone the repository with Git:

```bash
git clone https://github.com/griu/ai-ml-finance-hands-on.git
cd ai-ml-finance-hands-on
```

2. Create and activate the Conda environment:

```bash
conda env create -f environment.yml
conda activate finance_ml
```

3. Install the local pip requirements inside the activated environment:

```bash
pip install -r requirements.txt
```

4. Register the environment as a Jupyter kernel:

```bash
python -m ipykernel install --user --name finance_ml --display-name "finance_ml"
```

5. In VS Code:

- Open a notebook from `notebooks/`
- Select the `finance_ml` kernel when prompted
- Run cells from top to bottom
- Keep the terminal in the project root so relative paths work correctly

6. Typical workflow:

- Use **Git** to clone the repository or pull updates
- Use **Conda** to activate the correct Python environment
- Use **VS Code + Jupyter** to open and execute the notebooks

---

## Quickstart

1. Open VS Code manually and use **File > Open Folder...** on the repository root.

2. Open notebooks in order starting from `notebooks/01_python_setup_and_first_steps.ipynb`

3. Google Colab alternative:

- Open [colab.research.google.com](https://colab.research.google.com)
- Choose **File > Open notebook > GitHub**
- Paste `https://github.com/griu/ai-ml-finance-hands-on`
- Open `notebooks/01_python_setup_and_first_steps.ipynb` or another notebook from the repository
- Execute the **first cell** before running any other cell
- That first cell performs the Colab initialization: it detects Colab, clones the repository resources, installs `requirements-colab.txt`, and copies the `data/` folder next to the notebook so the rest of the notebook can resolve `data/processed`

## Neural networks and deep learning 

If you want to explore them, the `requirements-colab.txt` file includes the necessary dependencies for PyTorch. If you are setting up a local environment and want to include PyTorch, follow the instructions below.

```bash
# ── Deep learning (PyTorch) ──────────────────────────────────────────────────
# For CPU-only install (lighter, works on all platforms):
#   pip install torch --index-url https://download.pytorch.org/whl/cpu
# For GPU (CUDA 12.x):
#   pip install torch --index-url https://download.pytorch.org/whl/cu121
```

## Execution notes

- Notebooks are designed to run **from the project root or from the `notebooks/` folder**.
  A small `pathlib` helper at the top of each data-loading notebook resolves `data/processed/`
  automatically regardless of the current working directory.
- Run the core notebooks **in order** (01 → 02 → 03 → 04 → 05 → 05b → 06).
  The compact-extension notebooks (04a, 04b, 05c, 05d, 06e, 06f) can be explored
  alongside their parent. Each modelling notebook (04–06) rebuilds the feature matrix
  from scratch, so they are self-contained, but concepts build on prior notebooks.
- All random seeds are fixed at `42` for reproducibility.

---

## Folder structure

```
ai-ml-finance-hands-on/
├── README.md                 ← You are here
├── requirements.txt          ← pip dependencies
├── environment.yml           ← Conda environment spec
├── data/
│   ├── processed/            ← Cleaned teaching datasets (used by notebooks)
│   └── dictionaries/         ← Column descriptions per dataset
├── notebooks/                ← Jupyter notebooks (run in order)
└── docs/
    ├── environment_setup.md  ← Detailed setup guide
    ├── Theory_contents.md    ← Course manual (Topics 1 & 2)
    ├── instructor_teaching_map.md
    ├── dataset_manifest.csv  ← Registry of all datasets
    └── notebook_manifest.csv ← Registry of all notebooks
```

---

## Datasets

| ID | File | Rows | Purpose |
|---|---|---|---|
| A | `dataset_A_python_warmup.csv` | 50 | First Python exercises |
| B | `dataset_B_descriptive_stats_eda.csv` | 45 | Descriptive statistics & EDA (an extended version may be added if Notebook 03 needs richer visuals) |
| C | `dataset_C_bank_attrition_core.csv` | 10 000 | **Core modelling case** (bank churn) |
| D | `dataset_D_unsupervised_extension.csv` | 10 000 | PCA & clustering |
| E | `dataset_E_time_awareness.csv` | 46 | Temporal awareness |
| F | `dataset_F_deep_learning_awareness.csv` | 2 000 | Neural network demo |
| G | `dataset_G_finance_headlines_sentiment.csv` | 144 | Sentiment analysis |
| H | `dataset_H_financial_product_baskets.csv` | 250 | Association rules (Apriori) |

See `data/dictionaries/` for full column descriptions.

---

## Notebooks

| # | Notebook | Session | Dataset |
|---|---|---|---|
| 01 | Python Setup and First Steps | 1 | (inline) |
| 02 | Python Warm-up for Finance Students | 1 | A |
| 03 | Descriptive Statistics and EDA for Finance | 1–2 | B |
| 03b | Official Statistics and API Practice for Finance | 1 (ext.) | APIs |
| 04 | Building the First Modelling Table | 2 | C |
| 04a | *(compact)* Data Structures for Finance | 2 | C |
| 04b | *(compact)* Data Treatment for Model-Ready Data | 2 | C |
| 05 | Linear and Logistic Baseline Models | 3 | C |
| 05b | Decision Trees, Ensembles and XGBoost | 3 | C |
| 05c | *(compact)* Naïve Bayes, SVM and k-NN | 3 | C |
| 05d | *(compact)* Supervised Neural Networks with PyTorch | 3 | F |
| 06 | Validation, Regularization and Business Interpretation | 3 | C |
| 06b | *(optional)* Temporal, Spatial and Unsupervised Awareness | — | E, D |
| 06c | *(optional)* Neural Networks and Deep Learning Awareness | — | F |
| 06d | *(optional)* K-Means, PCA and Sentiment in Finance | — | D, G |
| 06e | *(compact)* Hierarchical Clustering and Gaussian Mixtures | — | D |
| 06f | *(compact)* Association Rules and Apriori for Finance | — | H |

---

## Requirements

- Python 3.11 (3.10 also works)
- pandas ≥ 2.0
- numpy ≥ 1.24
- matplotlib ≥ 3.7
- scikit-learn ≥ 1.3
- xgboost ≥ 2.0

No internet access required after initial setup. All datasets are local CSV files.
The only exception is notebook 03b (official statistics APIs), which optionally fetches live data but includes local fallback files.
