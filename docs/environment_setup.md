# Environment Setup Guide

## Course: Data Analysis, AI and Machine Learning in Finance

This guide explains how to set up your local Python environment for running the course notebooks.

For a one-page overview of the project and a quick-start command sequence, see the
[README.md](../README.md) in the project root.

---

## Step 0 — Get the course materials

All notebooks, datasets and configuration files live in the same GitHub repository.
You need to download it **once** before doing anything else.

### Option A — Clone with Git (recommended if Git is installed)

```bash
git clone https://github.com/griu/ai-ml-finance-hands-on.git
cd ai-ml-finance-hands-on
```

Git keeps the full history and lets you pull future updates with `git pull`.

### Option B — Download as a ZIP (no Git required)

1. Open [https://github.com/griu/ai-ml-finance-hands-on](https://github.com/griu/ai-ml-finance-hands-on) in your browser.
2. Click the green **Code** button → **Download ZIP**.
3. Extract the ZIP to a folder of your choice (e.g. `Documents/ai-ml-finance-hands-on`).
4. Open a terminal and navigate to that folder:
   ```bash
   cd path/to/ai-ml-finance-hands-on
   ```

> All subsequent commands in this guide assume you are inside the project root folder.

---

## Option 1 — Google Colab (quickest start, no installation)

### Getting the files into Colab

**Recommended — clone the repo directly inside Colab:**

Add this cell at the very top of any notebook before running anything else:

```python
import os
if not os.path.exists('/content/ai-ml-finance-hands-on'):
    !git clone https://github.com/griu/ai-ml-finance-hands-on.git /content/ai-ml-finance-hands-on
os.chdir('/content/ai-ml-finance-hands-on')
```

This clones the full repo (notebooks + datasets) into the Colab session.
The `os.chdir` call ensures relative paths resolve correctly.

> The Colab session resets when it disconnects. Re-run the cell above each time you open a new session.

**Alternative — mount Google Drive (persistent between sessions):**

```python
from google.colab import drive
drive.mount('/content/drive')
import os
os.chdir('/content/drive/MyDrive/ai-ml-finance-hands-on')  # adjust path as needed
```

Clone or copy the repo into your Drive once; after that, mounting is enough.

### Install the extra packages

Colab already includes pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost and torch.
Only three additional packages are needed:

```python
!pip install -q shap eurostat world_bank_data
```

See `requirements-colab.txt` in the project root for the complete minimal list.

**Pros:** No local installation, free GPU (T4), full repo available after the clone cell.  
**Cons:** Session resets on disconnect — re-run the setup cell each time (data is preserved if using Drive).

> `torch` (PyTorch) is **already installed** in Colab with GPU support. No extra install needed for NB05d.

---

## Option 2 — Local Anaconda installation (recommended)

### Step 1: Install Anaconda

If you have not done **Step 0** yet (downloading the repo), do that first — see the top of this guide.

Download Anaconda from: https://www.anaconda.com/download

- **Windows:** Run the `.exe` installer. Accept defaults. Check "Add to PATH" if prompted.
- **macOS (Intel):** Use the `.pkg` installer.
- **macOS (Apple Silicon / M1/M2/M3):** Use the ARM64 installer. If you see errors with `xgboost`, try: `conda install -c conda-forge xgboost`.
- **Linux:** Run `bash Anaconda3-*.sh` and follow prompts.

### Step 2: Create a dedicated environment

Open a terminal (Anaconda Prompt on Windows) and run **one** of the two options below.

**Option A — from the environment file (recommended):**

```bash
conda env create -f environment.yml
conda activate finance_ml
```

**Option B — manual creation + pip:**

```bash
conda create -n finance_ml python=3.11 -y
conda activate finance_ml
pip install -r requirements.txt
```

### Step 3: Register the Jupyter kernel

```bash
python -m ipykernel install --user --name finance_ml --display-name "finance_ml"
```

### Step 4: Launch Jupyter

```bash
jupyter notebook
```

Or open VS Code and select the `finance_ml` kernel.

### Step 5: Verify

Open `01_python_setup_and_first_steps.ipynb` and run the first few cells. If imports work, you're ready.

---

## Required packages

| Package | Version | Purpose |
|---|---|---|
| pandas | ≥ 2.0 | Data manipulation |
| numpy | ≥ 1.24 | Numerical computing |
| matplotlib | ≥ 3.7 | Plotting |
| scikit-learn | ≥ 1.3 | Machine learning |
| xgboost | ≥ 2.0 | Gradient boosting |
| shap | ≥ 0.42 | Model explainability |

**Optional (only for notebook 05d — neural networks):**

| Package | Version | Purpose |
|---|---|---|
| torch | (latest) | PyTorch deep learning framework |

To install PyTorch separately:

```bash
# CPU-only (lighter, works on all platforms):
pip install torch --index-url https://download.pytorch.org/whl/cpu
```

---

## Common issues

| Problem | Solution |
|---|---|
| `ModuleNotFoundError: No module named 'pandas'` | Run `pip install pandas` or activate the correct environment |
| `ModuleNotFoundError: No module named 'xgboost'` | Run `pip install xgboost` or `conda install -c conda-forge xgboost` |
| Jupyter shows wrong kernel | Kernel → Change Kernel → select `finance_ml` |
| Plots don't appear in Jupyter | Add `%matplotlib inline` at the top of the notebook |
| Apple Silicon errors with xgboost | Use `conda install -c conda-forge xgboost` instead of pip |

---

## Recommended VS Code extensions

If you are using VS Code, install the following extensions for the best experience with this course:

| Extension | Publisher | Purpose |
|---|---|---|
| Python | Microsoft | Python language support, linting, and debugging |
| Jupyter | Microsoft | Run and edit `.ipynb` notebooks inside VS Code |
| Pylance | Microsoft | Fast type checking and IntelliSense for Python |
| GitHub Copilot | GitHub | AI code completion (optional but useful) |
| Rainbow CSV | mechatroner | Colour-coded CSV preview for exploring datasets |
| Excel Viewer | GrapeCity | Preview `.csv` and `.xlsx` files as a spreadsheet |

### How to install

1. Open VS Code.
2. Press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (macOS) to open the Extensions panel.
3. Search for each extension by name and click **Install**.

After installing, select the `finance_ml` kernel when opening any notebook: click the kernel selector in the top-right corner of the notebook and choose **finance_ml**.

---

## Folder structure

```
ai-ml-finance-hands-on/
├── data/
│   ├── processed/    ← Cleaned teaching datasets (used by notebooks)
│   └── dictionaries/ ← Column descriptions for each dataset
├── notebooks/        ← Jupyter notebooks (run in order 01–06)
├── docs/             ← Manifests, teaching manual and this setup guide
├── requirements.txt
└── environment.yml
```

Notebooks load data from `../data/processed/` using relative paths.
