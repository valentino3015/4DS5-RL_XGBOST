# 4DS5-RL_XGBOST

# Reinforcement Learning–Inspired Modeling for Concrete Strength Prediction

This project explores an alternative formulation of concrete compressive strength prediction by reframing it as an **offline reinforcement learning (RL)** problem.  
We compare classical supervised learning models with **RL-based Q-function approximation** using both tree-based and deep learning methods.

---

## 📌 Problem Overview

Concrete compressive strength is a key indicator of construction quality and safety.  
However, measuring it requires time-consuming and destructive laboratory tests.

Using the **UCI Concrete Compressive Strength Dataset**, this project aims to:
- Predict concrete strength from mixture composition
- Compare classical regression with reinforcement learning–inspired approaches
- Study interpretability and decision-based modeling

---

## 📊 Dataset

**Source:** UCI Machine Learning Repository  
**Samples:** 1,030  
**Features (State variables):**
- Cement
- Blast Furnace Slag
- Fly Ash
- Water
- Superplasticizer
- Coarse Aggregate
- Fine Aggregate
- Age (days)

**Target:**
- Concrete compressive strength (MPa)

---

## 🧠 Methodology

### 1️⃣ Classical Supervised Learning
Used as performance baselines:
- Linear Regression
- Support Vector Regression (SVR)
- Random Forest
- Gradient Boosting

Evaluation metric: **Mean Absolute Error (MAE)**

---

### 2️⃣ Reinforcement Learning Reformulation

The prediction task is reframed as an **offline, one-step reinforcement learning problem**:

- **State (s):** Concrete mixture features  
- **Action (a):** Continuous prediction of strength (discretized grid)  
- **Reward (r):**
\[
r(s, a) = - (y_{\text{true}} - a)^2
\]

This setting is equivalent to a **contextual bandit**.

---

### 3️⃣ RL with XGBoost (Tree-Based Q-function)

- Q-function \( Q(s,a) \) approximated using **XGBoost**
- Strong performance on tabular data
- Interpretable via feature importance and tree visualization
- Policy selects the action maximizing the predicted Q-value

---

### 4️⃣ Deep Learning Extension (Neural Q-function)

- Q-function approximated using a **neural network**
- Implemented with **TensorFlow / Keras**
- Two hidden layers with ReLU activation
- Trained offline on state–action–reward tuples
- Inspired by **Deep Q-Learning**, adapted to a single-step setting

---

## 📈 Evaluation

Models are evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Residual analysis
- Error distributions

Confusion matrices are **not used** due to the continuous action space.

---

## 🔍 Interpretability

- Feature importance from XGBoost
- Q-function analysis via action distributions
- SHAP analysis applied directly to the learned Q-function

---

## 🛠 Technologies Used

- **Python**
- **scikit-learn** — baseline models
- **XGBoost** — tree-based Q-function
- **TensorFlow / Keras** — neural Q-function
- **Matplotlib & Seaborn** — visualization
- **Google Colab** — execution environment

---

## 📌 Key Takeaways

- Reinforcement learning can be applied to static datasets via offline reformulation
- Tree-based models remain highly effective for tabular data
- Deep learning provides flexibility but requires more data and tuning
- RL framing enables decision-based interpretation of predictions

---

## 📄 License

This project is intended for **academic and educational purposes**.

---

## 👤 Author

Ahmed Abid  
University Project — Reinforcement Learning & Machine Learning
