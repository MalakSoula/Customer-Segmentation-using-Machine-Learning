# 🛍️ Customer Segmentation Using Machine Learning



## 📌 Overview
This project applies unsupervised machine learning (K-Means Clustering) to segment customers based on their transactional behavior and coupon usage patterns. The goal is to identify different customer groups and provide business insights for better-targeted marketing strategies.


## 📊 Dataset Description
The dataset includes:
- Customers: Information about customer ID, gender, city, and join date.
- Transactions: Includes transaction status (subscribed, burned), coupon usage, and transaction dates.
- Additional Tables: Gender mapping, city mapping, branch, and merchant details.
 **Selected Features for Clustering:**
  - `coupon_usage_frequency`: How often a customer uses coupons.
  - `burned`: Number of coupons the customer redeemed.
  - `subscribed`: Number of transactions where the customer opted into a service.



## 🛠️ Methodology
### 1️⃣ Exploratory Data Analysis (EDA)
- Checked dataset structure, missing values, and duplicate records.
- Visualized transaction patterns and coupon usage.

### 2️⃣ Data Cleaning
- Removed missing values in key transaction fields.
- Dropped `burn_date` (since it's not needed for clustering).
- Converted date columns to proper datetime format.
  
### 3️⃣ Feature Engineering & Selection
- Created **coupon usage frequency** per customer.
- Counted **burned and subscribed transactions** per customer.
- Standardized features using **StandardScaler**.

### 4️⃣ Clustering Model Training
- Used **K-Means Clustering** to segment customers.
- Determined the optimal number of clusters using:
  - ✅ **Silhouette Score** (higher is better).
  - ✅ **Davies-Bouldin Index** (lower is better).
  - ✅ **Elbow Method** (to observe inertia drop-off).

### 5️⃣ Model Evaluation & Selection
- Chose the **best cluster count** based on Silhouette Score.
- Assigned customers to clusters and analyzed their behavior.



## 📈 Evaluation Metrics
### **✅ Silhouette Score**
- Measures how well-separated the clusters are (**higher is better**).
- Helps identify **the most meaningful segmentation**.

### **✅ Davies-Bouldin Index**
- Measures cluster compactness and separation (**lower is better**).
- Helps fine-tune the **optimal cluster count**.



## 🎯 Key Findings & Business Insights
After clustering, we found **distinct customer groups**:
1. **Frequent Coupon Users** 🎟️  
   - Customers who **use and redeem** coupons often.
   - Should be targeted with **loyalty rewards and VIP offers**.

2. **One-Time Buyers** 🛍️  
   - Customers who used **coupons once and stopped**.
   - Can be **re-engaged with personalized discounts**.

3. **Loyal Non-Coupon Users** 🏆  
   - Customers who **make purchases but don't use coupons**.
   - May be **interested in premium services instead of discounts**.




## 🖥️ How to Run the Code
### **1️⃣ Install Dependencies**
Ensure you have Python installed, then run:
```bash
pip install pandas numpy matplotlib scikit-learn
```
### **2️⃣ Run the Jupyter Notebook**
```bash
jupyter notebook
```
Open `Customer_Segmentation.ipynb` and run all cells.

3️⃣ View Results
The code generates key visualizations:
Silhouette Score Plot
Elbow Method Plot
Cluster Scatter Plot




## 📊 Visualizations
### 1️⃣ Elbow Method for Optimal Clusters
![Elbow Method](https://github.com/user-attachments/assets/f59749e0-8763-44eb-9bba-ac80c724306c)

### 2️⃣ Silhouette Score for Cluster Quality
![silhouette_score](https://github.com/user-attachments/assets/90793887-7693-4c6e-b2e9-f4ba6c70fa28)

### 3️⃣ Customer Segmentation Visualization
![Visualize the clusters](https://github.com/user-attachments/assets/8491f98d-4ab8-4eaa-8794-85b38d717a56)





## 📚 Conclusion
This project successfully segments customers into meaningful groups, helping businesses improve marketing strategies and customer retention. Further improvements could include:

Adding more features (e.g., average spend per transaction).
Testing different clustering algorithms (DBSCAN, Hierarchical Clustering).
Incorporating time-series analysis to track customer trends.
