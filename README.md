# Deep-Learning-Based-Product-Reordering-Prediction


# 🛒 Deep Learning Based Product Reordering Prediction

This project aims to build a **deep learning model** that predicts whether a user will reorder a product, using historical purchase behavior from the **Instacart Market Basket Analysis** dataset.

---

## 📌 Problem Statement

To predict whether a customer will reorder a specific product based on their past shopping history using machine learning and deep learning techniques.

---

## 🎯 Business Use Cases

- **Personalized Recommendations:** Suggest products users are likely to reorder.
- **Inventory Forecasting:** Predict future demand to reduce overstock/understock.
- **Customer Retention:** Identify changes in reorder habits to target churn.
- **Targeted Marketing:** Optimize campaigns using reorder likelihood.

---

## 🗃️ Dataset

Source: [Instacart Market Basket Analysis (Kaggle)](https://www.kaggle.com/c/instacart-market-basket-analysis/data)

**Files Used:**
- `orders.csv`
- `order_products__prior.csv`
- `order_products__train.csv`
- `products.csv`
- `aisles.csv`
- `departments.csv`

**Key Features:**
- `user_id`, `product_id`, `order_dow`, `order_hour_of_day`, `days_since_prior_order`, `reordered`, etc.

---

## 🔍 Approach

### 1. **Data Preparation & Merging**
- Merged all CSV files to create a user-product interaction view.
- Handled missing values and removed duplicates.

### 2. **Feature Engineering**
- **User Features:** total orders, reorder ratio.
- **Product Features:** reorder rate, order frequency.
- **User-Product Interaction:** times reordered by user.
- **Time Features:** is_weekend, is_morning_order, etc.

### 3. **Preprocessing**
- Normalized features using `StandardScaler`.
- Dropped irrelevant columns (e.g., product name, aisle).
- Converted the target (`reordered`) to binary format using one-hot encoding.

### 4. **Model Building**
- Deep Neural Network (Feedforward) using **TensorFlow/Keras**.
- Architecture:  
  - Input → Dense(200) → Dense(150) → Dense(100) → Dense(50) → Dense(20) → Dense(1)
- Activation: ReLU for hidden layers, Sigmoid for output.
- Loss: Binary Crossentropy  
- Optimizer: Adam

### 5. **Training & Validation**
- 80:20 train-test split with 10% validation.
- Used **EarlyStopping** to prevent overfitting.

---

## 📊 Results

| Metric              | Score     |
|---------------------|-----------|
| Training Accuracy   | 85.28%    |
| Training Loss       | 0.3158    |
| Validation Accuracy | 82.39%    |
| Validation Loss     | 0.4107    |

✔️ The model is stable and performs well on unseen data.

---

## 📁 Project Structure

