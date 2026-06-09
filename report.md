# Capstone Project Report: Titanic Dataset Analysis

## 1. Introduction
I chose the Titanic dataset for my capstone project because it represents a classic, highly interpretable machine learning challenge. The model is trying to predict whether a passenger survived (1) or did not survive (0) based on their socio-economic status, demographics, and ticket details. This is an interesting problem because it allows us to see how historical tragedy intersects with predictive variables—for example, evaluating the rule of "women and children first" or seeing how ticket class impacted survival odds.

## 2. Dataset Description
The dataset contains 891 rows and 12 columns. Key features include `Pclass` (ticket class), `Sex`, `Age`, `Fare`, and `Embarked` (port of embarkation). The target variable is `Survived`. The classes in this dataset are mildly imbalanced, with roughly 61% of passengers not surviving and 39% surviving. Because of this imbalance, I noted that F1-score is a crucial metric to monitor, as it balances precision and recall. To handle missing values, I filled the `Age` column with its median value and the `Embarked` column with the mode. I dropped the `Cabin` column entirely because it contained too many missing values to be reliably imputed.

## 3. Models Used
I trained three traditional machine learning models:
* **Logistic Regression (F1-score: ~0.74):** I included this model because it is a strong baseline algorithm for binary classification and offers high interpretability for tabular data.
* **Random Forest Classifier (F1-score: ~0.72):** I included this ensemble method because it naturally captures non-linear relationships and interactions between features like age and passenger class.
* **K-Nearest Neighbours (F1-score: ~0.71):** I included this algorithm to see how a distance-based approach would perform after scaling the numerical features.

**Logistic Regression** performed the best overall. While Random Forest had similar overall accuracy, Logistic Regression managed the best balance of precision and recall for the minority class (survivors), leading to the highest F1-score without overfitting the training data.

## 4. Neural Network
My neural network was built using a Sequential Keras architecture. It consists of an input Dense layer with 128 neurons and a ReLU activation function, followed by a Dropout layer set to a 30% rate to prevent overfitting. This was followed by a hidden Dense layer of 64 neurons (ReLU) and a second 30% Dropout layer. The final output layer used a single neuron with a sigmoid activation function to output binary probabilities. I trained the model for 25 epochs. The final validation accuracy hovered around 81%. Thanks to the inclusion of the dropout layers, I did not observe any severe overfitting; the training and validation loss curves decreased together in a stable manner. 

## 5. Results & Comparison
When comparing the models, traditional machine learning algorithms performed exceptionally well given the dataset's constraints. Logistic Regression proved to be the most reliable and fastest to train, achieving a strong F1-score with minimal configuration. The Neural Network achieved comparable accuracy to the traditional models but did not drastically outperform them. For a tabular dataset of this small size (under 1,000 rows), the extra complexity, computational cost, and tuning required for the Neural Network were not worth it. Deep learning models generally thrive on massive datasets with complex unstructured data, whereas simple tabular relationships are often best handled by simpler models like Logistic Regression or Random Forests.

## 6. What I Learned
The most important lesson from this project was that more complex models are not inherently better; data size and type dictate the optimal algorithm. I also learned that data cleaning—such as dropping unhelpful columns and imputing missing data accurately—has a massive impact on model stability. Finally, utilizing standard scalers and dropout layers proved to be highly effective techniques for stabilizing distance-based algorithms and preventing neural networks from memorizing training data.

---

AI was used for helping the student write the code and the report but it is not fully AI genrated and the student fully understands the code and the material.