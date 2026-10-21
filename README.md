# Unsupervised Machine Learning: Tech Workplace Mental Health Segmentation

An end-to-end data science project that uses unsupervised machine learning (clustering) to group technology workers based on their mental health and workplace support data.

## 📌 Project Summary
Using the **OSMI Mental Health in Tech Survey** (1,433 respondents), this project discovers hidden patterns in the data. It answers the question: *"Can we identify specific groups of tech workers to help HR target mental health interventions?"*

**The Key Insight:** 
The data splits into two groups (large-company employees vs. small-company employees). **Both groups have the exact same diagnosis rate (~50%)**, but small-company employees report significantly **less workplace support**. The barrier to mental health is not clinical access — it is workplace culture.

## 🛠️ The Machine Learning Pipeline
Because we have no predefined labels, we used a purely **unsupervised** approach:
1. **Preprocessing:** Cleaned raw text (e.g., standardized 70+ gender variants into 5 categories) and scaled all features.
2. **Dimensionality Reduction:** Used **PCA** to compress 57 features into 10 components (retaining 90% of the information).
3. **Clustering:** Used **K-Means** to find the optimal number of clusters (K=2).
4. **Evaluation:** Validated the clusters using the **Silhouette Score** (0.286)

## 📂 Repository Structure
```text
├── data/             # Raw OSMI survey dataset
├── notebooks/        # The main Jupyter Notebook with all Python code
├── charts/           # All generated PNG visualizations
├── output/           # Cleaned datasets and final cluster summaries (.csv)
├── requirements.txt  # Python dependencies
└── README.md
```

## 🚀 How to Install and Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/unsupervised-ml-tech-mental-health-segmentation.git
cd unsupervised-ml-tech-mental-health-segmentation
```

**2. Create and activate a virtual environment (Recommended)**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Run the notebook**
```bash
jupyter notebook
```
Open `notebooks/unsupervised_mental_health_clustering.ipynb` and go to **Kernel > Restart & Run All**. The pipeline takes about 2-3 minutes to complete.

## 📊 Results

| Metric | Cluster 0 (Large Companies) | Cluster 1 (Small Companies) |
| :--- | :--- | :--- |
| **Size** | 1,146 (80%) | 287 (20%) |
| **Diagnosis Rate** | 49.5% | 51.9% |
| **Workplace Support** | High | **Very Low (−2.99 Std Dev)** |

## 💡 HR Recommendations
Because diagnosis access is equal, HR should not focus on expanding clinical reach. Instead, target small organizations (<100 employees) with:
1. **Awareness campaigns** to reduce stigma.
2. **Manager training** to normalize conversations.
3. **Flexible leave policies** for firms without formal HR.

## 🧰 Built With
*   **Python 3.10+**
*   **scikit-learn** (PCA, K-Means)
*   **pandas** & **numpy** (Data processing)
*   **matplotlib** & **seaborn** (Visualizations)

## 📄 License
This project is licensed under the MIT License. The dataset is provided by Open Sourcing Mental Illness (OSMI).
