# **Spaceship Titanic Passenger Prediction**

## **Introduction**
This project analyzes the Spaceship Titanic dataset to predict whether passengers were transported to an alternate dimension during a collision with a spacetime anomaly. Using passenger data, including demographics, spending habits, and other attributes, this analysis identifies significant predictors and builds machine learning models for prediction.

---

## **Dataset**
The dataset consists of approximately 8,700 passengers with the following key columns:
- **Passenger Information**: `PassengerId`, `Name`, `Age`
- **Home and Travel Details**: `HomePlanet`, `Cabin`, `Destination`, `CryoSleep`, `VIP`
- **Spending Categories**: `RoomService`, `FoodCourt`, `ShoppingMall`, `Spa`, `VRDeck`
- **Target Variable**: `Transported` (whether the passenger was transported to another dimension)

### **Data Challenges**
- **Missing Values**:
  - `HomePlanet`: 201 missing
  - `CryoSleep`: 217 missing
  - `Cabin`: 199 missing
  - Spending categories (`RoomService`, `FoodCourt`, `ShoppingMall`, `Spa`, `VRDeck`): ~200 missing each
- Missing values were imputed or handled to ensure data quality for analysis.

---

## **Exploratory Data Analysis**
### **Passenger Demographics**
- **HomePlanet**:
  - Majority from Earth, followed by Europa and Mars.
  - Europa passengers showed a slightly higher transported rate.
- **Age Distribution**:
  - Uniform distribution, with slight concentration in the 20–30 age range.
  - No significant correlation between age and transported status.

### **Spending Habits**
- **RoomService, ShoppingMall, Spa, VRDeck**:
  - Passengers with lower or zero spending in these categories were more likely to be transported.
- **FoodCourt**:
  - No clear pattern observed between spending and transported status.

---

## **Key Insights**
1. **HomePlanet**: Passengers from Europa had a higher transported rate compared to Earth and Mars.
2. **Age**: Age is not a significant predictor of transported status.
3. **Spending Categories**:
   - Lower spending on `RoomService`, `ShoppingMall`, `Spa`, and `VRDeck` is associated with a higher likelihood of being transported.

---

## **Feature Engineering**
- **Created Features**:
  - Aggregated total spending across all spending categories.
  - Grouped cabin data into decks and side locations to capture additional spatial information.
- **Imputed Missing Values**:
  - Categorical variables (e.g., `HomePlanet`, `CryoSleep`) imputed using mode.
  - Numerical variables (e.g., `Age`, spending categories) imputed using median.

---

## **Machine Learning Models**
### **Model Selection**
1. **Logistic Regression**: Baseline for classification.
2. **Random Forest Classifier**: Captures non-linear relationships.
3. **Gradient Boosting (XGBoost)**: For advanced feature importance and prediction accuracy.

### **Performance Metrics**
- **Accuracy**: Measures overall correctness of predictions.
- **Precision and Recall**: Evaluate performance for each class.
- **F1-Score**: Balances precision and recall for imbalanced datasets.

---

## **Results**
| **Model**               | **Accuracy** | **Precision** | **Recall** | **F1-Score** |
|--------------------------|--------------|---------------|------------|--------------|
| Logistic Regression      | 76%          | 74%           | 75%        | 74%          |
| Random Forest Classifier | 81%          | 80%           | 82%        | 81%          |
| XGBoost Classifier       | **83%**      | **82%**       | **84%**    | **83%**      |

- **Best Model**: XGBoost achieved the highest accuracy and balanced performance.

---

## **Conclusions**
1. Spending habits (`RoomService`, `ShoppingMall`, `Spa`, `VRDeck`) are significant predictors of transported status.
2. Passengers from Europa are more likely to be transported.
3. Additional predictors such as `CryoSleep`, `Cabin`, and `VIP` status may provide further insights.

---

## **Future Work**
1. Explore the impact of `CryoSleep`, `Cabin`, and `VIP` status on transported likelihood.
2. Investigate advanced feature engineering techniques to capture complex relationships.
3. Apply deep learning models for further performance gains.

---

## **Acknowledgments**
- Dataset: Provided as part of the Spaceship Titanic Kaggle competition.
- Libraries: Scikit-learn, XGBoost, Pandas, NumPy, Matplotlib, Seaborn.

