# PS-09: Plant Seedling Species Classification
**Domain:** Agriculture & Food | Precision Agriculture & Edge-AI Weed Control  
**Competition Dataset:** [Kaggle: Plant Seedlings Classification (Aarhus University)](https://www.kaggle.com/c/plant-seedlings-classification)

---

## 📌 Problem Overview
Telling crop seedlings from weed seedlings at an early growth stage allows farmers and autonomous field robots to remove weeds before they compete with crops for light, moisture, and soil nutrients. Broadcast spraying wastes up to 85% of herbicide volume and harms the environment. Autonomous optical spot-sprayers require high-speed computer vision to distinguish between **12 seedling species**, several of which appear virtually identical at early vegetative stages (a fine-grained visual classification challenge).

### The 12 Species
| Category | Species Common Name | Scientific Name | Botanical Family |
| :--- | :--- | :--- | :--- |
| **Crop** | Maize | *Zea mays* | Poaceae (Monocot) |
| **Crop** | Common wheat | *Triticum aestivum* | Poaceae (Monocot) |
| **Crop** | Sugar beet | *Beta vulgaris* | Amaranthaceae (Dicot) |
| **Weed** | Black-grass | *Alopecurus myosuroides* | Poaceae (Monocot) |
| **Weed** | Loose Silky-bent | *Apera spica-venti* | Poaceae (Monocot) |
| **Weed** | Charlock | *Sinapis arvensis* | Brassicaceae (Dicot) |
| **Weed** | Cleavers | *Galium aparine* | Rubiaceae (Dicot) |
| **Weed** | Common Chickweed | *Stellaria media* | Caryophyllaceae (Dicot) |
| **Weed** | Fat Hen | *Chenopodium album* | Amaranthaceae (Dicot) |
| **Weed** | Scentless Mayweed | *Tripleurospermum inodorum* | Asteraceae (Dicot) |
| **Weed** | Shepherd's Purse | *Capsella bursa-pastoris* | Brassicaceae (Dicot) |
| **Weed** | Small-flowered Cranesbill | *Geranium pusillum* | Geraniaceae (Dicot) |

---

## 🗂️ Project Structure
```
c:\Users\USER\Desktop\Activity\
├── plant_seedling_classification.ipynb  # End-to-end complete Jupyter Notebook
├── download_competition.py              # Script to download and extract dataset via kagglehub
├── configure_kaggle.py                  # Quick CLI script to save ~/.kaggle/kaggle.json
├── build_notebook.py                    # Generator script for the notebook
├── README.md                            # Documentation and project manual
└── dataset/                             # Created upon download (train/, test/, sample_submission.csv)
```

---

## 🚀 Quickstart Guide

### Step 1: Accept Competition Rules & Configure Kaggle API
1. Open the [Kaggle Competition Rules](https://www.kaggle.com/c/plant-seedlings-classification/rules) and click **"I Understand and Accept"**.
2. Go to [Kaggle Account Settings](https://www.kaggle.com/settings) and click **"Create New Token"** to download `kaggle.json`.
3. Run the configuration helper or manually place the file:
   ```bash
   python configure_kaggle.py
   ```
   *(Or place `kaggle.json` inside `~/.kaggle/kaggle.json`)*

### Step 2: Download Dataset
Run the automated downloader:
```bash
python download_competition.py
```
Or directly inside Python / the notebook:
```python
import kagglehub
path = kagglehub.competition_download('plant-seedlings-classification')
print("Path to competition files:", path)
```

### Step 3: Open & Run the Jupyter Notebook
Open [`plant_seedling_classification.ipynb`](file:///c:/Users/USER/Desktop/Activity/plant_seedling_classification.ipynb) in VS Code, JupyterLab, or upload to Kaggle Notebooks / Google Colab:
- **Section 1:** Environment setup & seed fixing
- **Section 2:** Kaggle authentication & archive extraction
- **Section 3:** Exploratory Data Analysis (EDA, class balance, ExG chlorophyll index, confusing monocot pairs)
- **Section 4:** Stratified 80/20 train-val split & 360° rotational augmentations
- **Section 5:** Transfer learning with ResNet-34 / EfficientNet architecture
- **Section 6:** Training with label smoothing ($\epsilon=0.1$) & cosine annealing scheduler
- **Section 7:** Model diagnostics, confusion matrix & misclassification analysis
- **Section 8:** Test-Time Augmentation (TTA) & Kaggle `submission.csv` generation
- **Section 9:** Precision agriculture deployment, tractor speed vs latency, and edge AI roadmap
