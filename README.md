
# **Pratilipi User Behavior Prediction**

A machine learning project to predict the future reading behavior of Pratilipi users by recommending the top 5 pratilipis (stories) each user is likely to read. The project utilizes hybrid recommendation techniques combining collaborative filtering and content-based filtering.

---

## **Table of Contents**
1. [Project Overview](#project-overview)
2. [Data Description](#data-description)
3. [Usage](#usage)
4. [Model Description](#model-description)
---

## **Project Overview**

The objective of this project is to build a hybrid recommendation system for predicting future user behavior on Pratilipi. It incorporates:
- **Collaborative Filtering**: Using Singular Value Decomposition (SVD) to capture latent patterns in user-item interactions.
- **Content-Based Filtering**: Using cosine similarity on pratilipi metadata (e.g., category, reading time) to enhance recommendations.
- **Hybrid Approach**: Combining collaborative and content-based methods to achieve better accuracy and personalization.

---

## **Data Description**

The dataset includes:
- **User Interactions**: Information about user activities, such as `read_percent`, `updated_at`, and `pratilipi_id`.
- **Pratilipi Metadata**: Attributes of pratilipis such as `category_name`, `reading_time`, and `author_id`.

### Data Preprocessing:
1. Missing values were handled (e.g., filling unknown categories, normalizing `reading_time`).
2. Rows with null values were removed to ensure clean data.
3. Interaction data was normalized to account for user activity levels.

---



## **Usage**

### **1. Preprocessing the Data**
Run the data preprocessing script to clean and normalize the data:


### **2. Training the Recommendation Model**
Train the hybrid recommendation model using SVD and content-based filtering:


### **3. Evaluating the Model**
Evaluate the model using precision, recall, and F1 score:


### **4. Get Recommendations**
Generate recommendations for a specific user:


---

## **Model Description**

### **Collaborative Filtering**
- **Technique**: Singular Value Decomposition (SVD).
- **Goal**: Capture latent patterns in user-item interactions (user preferences and item properties).
- **Input**: A normalized user-item interaction matrix (`read_percent`).

### **Content-Based Filtering**
- **Features Used**: `category_name` (one-hot encoded) and normalized `reading_time`.
- **Technique**: Cosine similarity between pratilipis based on their metadata.

### **Hybrid Recommendation**
- **Approach**: Combines collaborative filtering scores and content-based scores using a weighted average.
- **Output**: Top 5 recommended pratilipis for each user.

---

## **Evaluation Metrics**

The model is evaluated using:
1. **Precision@5**: The proportion of recommended pratilipis that are relevant to the user.
2. **Recall@5**: The proportion of relevant pratilipis that are recommended to the user.
3. **F1 Score@5**: A harmonic mean of precision and recall.


---

## **Results**

### **Evaluation Results**
| Metric         | Score   |
|----------------|---------|
| **Precision@5**| 0.0219  |
| **Recall@5**   | 0.0039  |
| **F1 Score@5** | 0.0066  |

*Efforts are being made to improve these results by optimizing weights and adding more advanced techniques.*

---

## **Future Work**
1. Experiment with advanced hybrid methods (e.g., weighted SVD and deep learning-based models).
2. Include temporal dynamics (e.g., time-decay factors).
3. Address cold-start problems for new users and pratilipis.
4. Use neural collaborative filtering and transformer-based models.

