# Quora_Question_Pairs

The goal of this project is to identify duplicate questions i.e. questions of similar meaning given 2 questions on Quora. The competition was hosted on Kaggle and all the resources are freely available. Quora has provided labeled data identifying duplicates and the prediction of the models is tested on some part of this labeled set i.e. the test set. The success of the predictions is measured in terms of the following metrics:

- Log loss: $$ \sum_i −(𝑦_i 𝑙𝑜𝑔(ŷ_i ) + (1 − 𝑦_i) 𝑙𝑜𝑔(1 − ŷ_i )) $$
y = true label 
ŷ = predicted probability of a pair being duplicate

- Accuracy of the predictions

The study is divided into 4 parts:
- **Exploratory Data Analysis:** The analysis gives us an idea about the data at hand to tackle it most appropriately while modeling
- **Data Cleaning and Root Word Generation:** Raw text data is cleaned, and root words are generated from the words in the text to reduce the vocabulary for faster modeling 
- **Predictive Modeling with Classical Techniques:** In this section, features are extracted using character counts, term frequency-inverse document frequency (TF-IDF) along with cosine similarity. Common models are trained with these features
- **Predictive Modeling with Advanced Techniques:** Various Neural Network Architectures are tried with word embeddings created from questions’ text




Following is the summary of various models on the validation set: 

| Model | Avg-Precision |F1-Score|
| :-: | :-: |:-: |
|Char counts & char length difference with Logistic Regression| 0.58|65%|
| Char counts & char length difference with Random Forest | 0.55 | 68%|
| Char counts & char length difference with XGBoost | 0.55 |68%|
| Tf-idf & char length difference with Logistic Regression | 0.58 |65%|
| Tf-idf & char length difference with Random Forest | 0.47 |0.50|
| Tf-idf & char length difference with XGBoost | 0.55|67%|
| Sentence Embeddings based Neural Network architecture | 0.47 |77%|
| Word embeddings and LSTM based Neural Network architecture | 0.45 |77%|
| Word embeddings and CNN architecture | 0.43 |79%|

CNN model is tried on the Kaggle's test set and the best log-loss score is 0.41 
