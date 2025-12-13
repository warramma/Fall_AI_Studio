# Fall AI Studio - Entrepreneur Compass Tool
---

### 👥 **Team Members**

| Name             | GitHub Handle | Contribution                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
|  Chelsea Ezumah   | [@chelseaezumah](https://github.com/chelseaezumah) |    Research + Presentation, Training Logistic Regression Model,  Finding Areas of Improvement in the Dataset |
|  Fahmin Rahman   | [@FRAHMAN117](https://github.com/FRAHMAN117) |    Research + Presentation, Feature Engineering, Feature Selection, Training DNN Model  |
|  Kripamoye Biswas   | [@kbiswas20](https://github.com/kbiswas20) |    Research + Presentation, Project Planning, Training Random Forest Model  |
|  Ruhe Solomon   | [@ruhesolomon](https://github.com/ruhesolomon) |    Research + Presentation, Training Decision Tree Model, Expanding Resource Dataset  |
|  Wardiyah Rammazy   | [@warramma](https://github.com/warramma) |    Research + Presentation, EDA, Training KNN Model|
| Genna Gonzaga   |  | Research|

---

## 🎯 **Project Highlights**
After extensive business research, EDA, & Feature Engineering, we tested several models for Cambio Labs' Resource Recommendation system.

- We found Random Forest to be the most effective for the problem, with KNN and DNN as runner's up.

---

## 👩🏽‍💻 **Setup and Installation**

The majority of our work was done in Google Colab Notebooks then uploaded to GitHub. To run models & scripts

1. Select the `.ipynb` file you want.
2. Download it.
3. Run the notebook locally or upload to Google Colab.

Final datasets used are available in the repository under the 'Data' folder, as well as original, sample data. 

---

## 🏗️ **Project Overview - Entrpreneur Compass Tool**
Our project focuses on developing machine learning models that transform data into tailored resource recommendations, allowing small business owners to grow without wasting time on figuring out how.

- We worked on this project as AI Studio Fellows for [Cambio Labs](https://www.cambiolabs.org/) through the Break Through Tech Program.
- Cambio Labs™ empowers low income social entrepreneurs and workers through educational programs, learning technology, and by providing access to investment and job opportunities.
- With our project, we aimed to
  - Streamline Cambio Labs’ workflow - Automating resource matching, saving time, reducing manual effort
  - Leverage data and machine learning - Make recommendations faster, accurate, and scalable
- Scope: doing an in-depth analysis of possible models and presenting our findings in order to position Cambio Labs to create a user-friendly tool.
- Impact:
  - Increasing success rate of small business owners finding relevant and impactful resources
  - Simplified yet informative user onboarding experience
  - Target a broader group of business owners with a larger set of recommended resources
---

## 📊 **Data Exploration**
### Datasets Used
* **X_final_optimized** - The final optimized features
  * Origin: Created through feature selection
  * Formats: `csv`, `xlsx`
  * Size: (32 rows X 15 columns)
  * Type of data: Numerical, Continuous data and Booleans
* **target_new_resources**
  * Origin: Created a target matrix for resources (including new resources our team found), with a matrix of recommended resources for each row in features.
  * Formats:`xlsx`
  * Size: (32 rows X 30 columns)
  * Type of data: Numerical, Continuous data and Booleans
* **dummy_features** - Dummy data for features
  * Origin: Generated through random sampling & noise
  * Formats: `csv`, `xlsx`
  * Size: (1000 rows X 15 columns)
  * Type of data: Numerical, Continuous data and Booleans
* **dummy_target** - Dummy data for target matrix
  * Origin: Generated through random sampling & noise
  * Formats: `csv`, `xlsx`
  * Size: (1000 rows X 30 columns)
  * Type of data: Boolean (1 or 0)
#### Original Data
* **program_requirements**
  * Origin: Provided by Cambio Labs
  * Formats: `xlsx`
  * Size: (30 rows X 3 columns)
  * Type of data: Complex text data, several tables in one sheet.
* **sample_results**
  * Origin: Provided by Cambio Labs
  * Formats: `xlsx`
  * Size: (42 rows X 12 columns)
  * Type of data: Numerical, Continuous data, Strings/Text Data
* **survey_responses**
  * Origin: Provided by Cambio Labs
  * Formats: `xlsx`
  * Size: (37 rows X 48 columns)
  * Type of data: Numerical, Continuous data, Strings/Text Data
  
### Data Exploration & Insights
To process our data, we combined our individual responses, results, and resource datasets to create one unified dataset. From there, we performed EDA & extracted insights. 

I. Respondent Demographics & Status
- Location: **High concentration in The Bronx (most respondents)**, followed by Manhattan and Brooklyn.
- Income: **Overwhelmingly low-income**, with the vast majority reporting family income Under $25,000.
- Housing: **Highly concentrated in affordable housing**, primarily NYCHA public housing and Section 8 Voucher holders.
- Employment: A mix of Employed, Unemployed, and Self-Employed individuals.
- Tech Access: Near-universal access to a Smartphone for virtual training, with many also having access to a laptop/computer.

II. Entrepreneurial Interest & Stage
- Business Stage: Most ventures are in **the very early stages**, predominantly the Idea Stage or Planning/Getting started phase.
- Program Experience: A significant number of respondents appear to be **new to formal training**, as prior program/accelerator participation data is largely missing (likely indicating "None").
- Focus: A **clear interest in Social Entrepreneurship** (impact-focused) and **Cooperative Businesses** (community-owned) alongside general entrepreneurship.
- Money: Majority no external funding or profit

III. Data Quality and Gaps
- Key Missing Data: The highest missing values were for Language preference other than English (suggesting English is sufficient for almost all) and details on prior external funding.
- Financial Status: High number of missing/non-applicable values for questions about being cash flow positive or profitable, which aligns with the finding that most businesses are pre-revenue.
- Majority N/A or No in regards to challenges facing their business that could clarify the type of support they need

### Challenges & Assumptions
* Given only a very small set of sample data, we struggled significantly when it came to increasing accuracy and generalizing our models.

---

## 🧠 **Model Development**

* Model(s) used
  *   Decision Tree
  *   Random Forest with Grid Search
  *   K-Nearest Neighbors with Grid Search
  *   Logistic Regression (Multi-Output)
  *   Simplified DNN with Early Stopping and Dropout
### Feature Engineering
  * To prepare the features, we used 3 types of feature engineering   
    1. Natural Language Processing (NLP) on open-ended responses
    2. One-hot encoded features
    3. Min-max scaling
 * **Process:** We merged the datasheets, addressed feature variance, and cleaned hot encoded columns.
 * Removed features with less than 15% out outputs → 159 features
 * Dropping unscaled columns & redundant features
 * Used logistic regression to select the 15 most influential features

### Feature Selection
The most influential features we found for predicting resources were primarily tied to technology access, education, employment, racial demographics, need for social welfare, income level and interest in entrepreneurship.

### Training Setup
* We used a 70/30 training/test split and an 85/15 training/test split for DNN. 
* For evaluation, we used accuracy thresholds and **Jaccard Score** to measure the overlap between predicted and correct recommended set of resources.
---

## 📈 **Results & Key Findings**

### Performance
![](https://github.com/warramma/Fall_AI_Studio/blob/ffab9329777b7a250a39cf9df50965820769a012/images/KNN.png)
![](https://github.com/warramma/Fall_AI_Studio/blob/f18af35d88fc1134dd93557ad7a90b42c119b2df/images/DECISION%20TREE.png)
![](https://github.com/warramma/Fall_AI_Studio/blob/ffab9329777b7a250a39cf9df50965820769a012/images/RANDOM%20FOREST.png)
![](https://github.com/warramma/Fall_AI_Studio/blob/ffab9329777b7a250a39cf9df50965820769a012/images/LOGISTIC%20REGRESSION.png)
![](https://github.com/warramma/Fall_AI_Studio/blob/ffab9329777b7a250a39cf9df50965820769a012/images/DNN.png)

### Summary
![](https://github.com/warramma/Fall_AI_Studio/blob/23f695d7127dfecbf286410cdce326cfcae60529/images/ACCURACIES.png)
**Most accurate:** KNN

**Suggested model(s):** KNN/Random Forest (Runner-up: DNN)
* *KNN:* most accurate but not as scalable
* *Random forest:* despite lower accuracy, it is more interpretable and scalable
* *DNN:* black box predictions are harder to explain and the model is more complex to train

---

## 🚀 **Next Steps**

Our next steps as a team include:
- Increasing the dataset size and enriching features, such as survey responses, program data, and detailed entrepreneur information.
- We plan to continue testing models to improve performance, gather direct feedback from entrepreneurs to enhance personalization and relevance, and track which recommendations are most useful to inform future predictions.

* **What are some of the limitations of your model?** - We were limited by the size of our data as well as our own knowledge gaps.
* **What would you do differently with more time/resources?** - We'd love to have a visual component allowing users to directly test models to recommend resources.
---

## 🙏 **Acknowledgements** 
We would like to thank Nandini Proothi, our AI Studio Coach, and Angelo Orciuoli, our Challenge Advisor from Cambio Labs.
