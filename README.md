# Predictive-Modeling-and-Clustering-for-Home-Loan-Campaign-Optimization

# 🧠 Regional Clustering using K-Means on Indian Population Data

This project uses **K-Means Clustering** to group different geographic regions of India based on population statistics, helping a marketing team allocate resources for targeted campaigns. The clustering is based on demographic variables such as Indian and foreign population, gender-wise counts, and total population.

---

## 📝 Problem Statement

A marketing firm wants to launch a promotional campaign in different regions across India. In order to plan resource allocation efficiently, they need to segment the regions into logical groups based on demographic characteristics.

We use **unsupervised learning** (K-Means Clustering) to categorize the regions into clusters using features like total population, Indian/foreign population, and gender distribution.

---

## 📊 Dataset

- File: `Population_Data.csv`
- Features used:
  - `Indians`, `Foreigners`
  - `Indian_Male`, `Indian_Female`
  - `Foreigners_Male`, `Foreigners_Female`
  - `Total Population`

---

## ⚙️ Tools & Technologies

- Python (Google Colab / Jupyter Notebook)
- pandas, NumPy
- scikit-learn
- matplotlib

---

## 🧪 Methodology

1. **Data Cleaning**
   - Cleaned numeric columns (e.g., removed commas, converted strings to integers)
   - Ensured `Total Population` = sum of all components

2. **Data Normalization**
   - Applied `Normalizer` from scikit-learn to scale values uniformly

3. **K-Means Clustering**
   - Used Elbow Method to find optimal number of clusters
   - Trained K-Means model on normalized data
   - Assigned cluster labels to each region

4. **Visualization**
   - Plotted clusters using scatter plots for feature pairs (e.g., `Indians vs Foreigners`)

---

## 📈 Elbow Method Output

The Sum of Squared Errors (SSE) was plotted to determine the best value of `k` for K-Means clustering.

```python
SSE = []
for cluster in range(1, 10):
    kmeans = KMeans(n_clusters=cluster, random_state=42)
    kmeans.fit(data1)
    SSE.append(kmeans.inertia_)

plt.plot(range(1, 10), SSE, marker='o')
plt.title("Elbow Method")
