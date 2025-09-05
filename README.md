# 🍄 Mushroom Classification with PCA and Logistic Regression

## 📌 Assignment Overview
This assignment focuses on classifying mushrooms as **edible** or **poisonous** using machine learning techniques. The dataset is transformed and analyzed using **Principal Component Analysis (PCA)** to explore dimensionality reduction and its effect on classification performance.  
A **Logistic Regression** model is trained both on the **original dataset** and the **PCA-transformed dataset** to compare performance.

---

## ⚙️ Steps in the Workflow

### 1. Data Loading
- The **mushrooms dataset** (`mushrooms.csv`) was loaded into a Pandas DataFrame.

### 2. Preprocessing
- All features are **categorical**, so they were **encoded into numeric format**.
- Features were then **scaled using `StandardScaler`** to standardize distributions and prepare for PCA.

### 3. Principal Component Analysis (PCA)
- PCA was applied without specifying components, so all were computed.
- The **explained variance ratio** was analyzed:
  - First 2 PCs explain about **17%** of the variance.
  - Indicates many components are needed to capture the full structure.

### 4. Visualization
- **Scatterplot of first 2 PCs**: Shows edible vs poisonous mushrooms projected in 2D space.
- **Pairplot of first 4 PCs**: Helps visualize class separation across different PC combinations.

### 5. Model Training and Evaluation
- **Logistic Regression** trained on:
  - Original dataset.
  - PCA-transformed dataset.
- Performance evaluated using:
  - **Accuracy**
  - **Classification Report (precision, recall, F1-score)**

---

## 📊 Results

### Original Data
- **Accuracy**: 1.0  
- **Classification Report**: Perfect classification for both edible and poisonous mushrooms.

### PCA-Transformed Data
- **Accuracy**: ~0.999  
- **Classification Report**: Nearly perfect classification with only a minor drop.

---

## 🔎 Analysis & Discussion

1. **Performance Difference**  
   - The difference between original and PCA-transformed models is negligible.  
   - Original features give slightly better results since no information is lost.

2. **Impact of PCA**  
   - PCA reduced dimensionality while preserving most variance.  
   - It handles **feature collinearity and redundancy** effectively.  
   - Even with some information loss, Logistic Regression still performs almost perfectly.

3. **Usefulness of Logistic Regression as Surrogate**  
   - Logistic Regression is **simple, interpretable, and sensitive to linear separability**.  
   - Makes it a good baseline to evaluate PCA’s effectiveness.  
   - If PCA preserves enough variance, Logistic Regression can still classify effectively, which we observed here.

4. **Takeaway**  
   - PCA is useful for visualization, reducing complexity, and tackling redundancy.  
   - However, when computational cost is not an issue and perfect accuracy is achievable, using the full dataset may be preferable.

---

## 📈 Visualizations

- **Scatterplot (PC1 vs PC2):** Shows edible vs poisonous separation in reduced space.  
- **Pairplot (PC1–PC4):** Illustrates clustering across multiple principal components.  

---

## 🚀 Conclusion
- Logistic Regression achieved **perfect accuracy** on the original dataset and **nearly perfect** accuracy on PCA-transformed data.  
- **PCA is beneficial** for visualization and reducing dimensionality but may slightly reduce performance due to variance loss.  
- In this case, the dataset was already well-structured, so PCA’s benefits were more in visualization than performance improvement.

---

## 🛠️ Tools & Libraries
- **Python**
- **Pandas, NumPy**
- **Scikit-learn** (PCA, Logistic Regression, StandardScaler)
- **Seaborn, Matplotlib** (visualizations)
