# 🍽️ Culinary Compass

**Culinary Compass** is a personalized food recommendation system built to be your trusted food advisor. It helps users explore new tastes and dishes based on their unique flavor preferences and dietary restrictions.

---

## 🚀 Project Goals

Culinary Compass enables users to:
- Discover dishes tailored to their **flavor preferences** (e.g., salty, sour)
- Avoid dishes that contain **allergens** (e.g., peanuts, almonds)
- Continuously receive better recommendations through **user feedback**

---

## 🧠 Methodology

Culinary Compass leverages the [**FlavorGraph**](https://github.com/lamypark/FlavorGraph), a graph neural network that models over **6,600 ingredients** and **2,000 chemical compounds**, representing complex relationships between ingredients using **300-dimensional embeddings**.

### 🔧 Algorithms Used

- **Incremental PCA (IPCA)**  
  Reduces the high-dimensional ingredient embeddings of each dish while preserving the most variance.

- **Cosine Similarity**  
  Measures similarity between user flavor preferences and dish embeddings to find the most relevant dishes.

- **Bayesian Personalized Ranking (BPR)**  
  Optimizes dish recommendation rankings based on positive/negative user feedback, updating individual user profiles dynamically.

---

## 🧾 Data Description

| File Name                             | Description                                                                 |
|--------------------------------------|-----------------------------------------------------------------------------|
| `new_menu.csv`                       | Contains 523 dishes with restaurant information, ingredients, and descriptions (Toronto area). |
| `new_flavorgraph_df.csv`            | Contains user flavor and allergy input features.                           |
| `menu_embedded.pkl`                 | Preprocessed embeddings of dishes from `new_menu.csv`.                     |
| `flavor_embedded.pkl`               | Preprocessed embeddings of user flavor preferences from `new_flavorgraph_df.csv`. |
| `new_nodes.csv`, `FlavorGraph Node Embedding.pickle` | Embeddings of ingredients and chemical compounds used in FlavorGraph. |

---

## 📲 User Experience

### Input
- Flavors: e.g., Salty, Sour, Umami
- Allergies: e.g., Peanuts, Almonds

### Output
- Recommended dishes with:
  - Dish name
  - Restaurant info
  - Dish description

### Interaction
- Users rate each recommendation as **positive** or **negative**
- Feedback improves future recommendations using BPR

---

## ⚠️ Limitations

- Limited to **Greater Toronto Area** dishes
- Only considers **flavors** and **allergies** as input
- Requires users to interact with the app to improve recommendations

---

## 🔮 Future Work

- Expand dataset to include:
  - Broader geography
  - Additional inputs: cuisine, temperature, location, etc.
- Implement full **Graph Neural Network** for deeper understanding of **Users ↔ Dishes ↔ Ingredients**
- Build a web-based application (e.g., **Streamlit**) for live recommendations

---

