
# Predicting Wine Quality using Deep Learning

## Project Overview
This project focuses on predicting the quality of wines based on their physicochemical properties. This project explores various deep learning models to find the most effective approach for this prediction task, considering the nuances between different types of wines.

## Dataset and Environment Setup
The project utilizes the "Wine Quality" dataset, accessible through the `ucimlrepo` Python package. Necessary libraries include `keras`, `numpy`, `pandas`, `seaborn`, `sklearn`, and `matplotlib`. Installation instructions are provided in the setup section.

## Key Observations from Initial EDA - ***Imbalanced Data***

- **Central Tendency**: A majority of wines are rated around 5 or 6, with white wines showing a pronounced concentration around these scores.
- **Spread and Skewness**: Red wines exhibit a broader distribution of quality scores compared to white wines, which are more skewed towards the score of 6.
- **Extremes**: There are relatively few very high or very low quality ratings for both wine types.
- **Comparison between Red and White Wine**: White wines generally have a higher concentration of ratings at quality score 6, while red wines have a more even distribution of scores around 5 and 6.

## Methodology 
Starting with basic models and progressing to more complex neural networks, we applied various strategies to combat overfitting and enhance model generalization. This included the use of regularization techniques and callbacks. Despite efforts, validation accuracy scores remained moderate, highlighting the challenge in distinguishing wine quality based solely on physicochemical features.

## Dealing with Imbalanced Data
The imbalanced nature of the dataset prompted us to employ SMOTE sampling to enhance model training. While this technique provided a slight improvement in accuracy, the inherent difficulty in differentiating features against the target variable limited significant gains.

## Model Exploration

Our exploration of models aimed to address the challenge of predicting wine quality from different angles. Here is how we approached it:

### Multiclass Classification
We began with models designed to predict the specific quality score of wine, treating the problem as a multiclass classification. This allowed us to capture the nuances across different quality levels as reflected in the data.

### Binary Classification
Acknowledging the difficulty in multiclass predictions, we also explored binary classification, simplifying the problem to discern whether a wine is of good or bad quality based on a predefined threshold.

### SMOTE Technique
To address the imbalance in the dataset, which could bias our models, we employed the Synthetic Minority Over-sampling Technique (SMOTE). This technique was applied to both multiclass and binary classification problems, enhancing the representativeness of minority classes and thus, the robustness of our models.

### Model Selection and Fine-Tuning
After applying SMOTE, we selected the best-performing model from all strategies and architectures through rigorous testing and validation. The chosen model underwent fine-tuning to further refine its predictive capabilities.

### Combined vs Separate Models
We tested various strategies for dealing with different types of wines:
- A single model for both red and white wine, seeking to find common predictive patterns across wine types.
- Separate models for each wine type, tailored to the unique characteristics of red and white wines respectively.
- Cross-fine-tuning strategies where a model trained on one wine type was fine-tuned on the other.

These approaches allowed us to gauge the effectiveness of specialized models versus a generalized model and to understand the transferability of learned features between red and white wines.

## Insights and Model Performance
Separate models for red and white wines yielded better results, particularly for red wine. Further experiments showed that models fine-tuned on one wine type and then trained on another exhibited superior generalization capabilities. The model initially trained on white wine and fine-tuned on red wine demonstrated the highest accuracy.

## Future Considerations
To address the challenges identified, we recommend:
- Increasing the dataset size to mitigate imbalances.
- Introducing new, distinguishing features to better separate different quality scores.

## Conclusion
This project underscores the complexities of predicting wine quality through deep learning. Future efforts should focus on enhancing data quality and feature engineering to improve model accuracy and applicability.
