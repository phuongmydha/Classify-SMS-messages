# NLP
Text Processing: strip special characters, removing stopwords, Tokenization and Lemmatization
Using Machine Learning model: SVM, MaxEnt; and deep learning LSTM  model to classify sms message is ‘ham’ or ‘spam’


Through the process of research and study, the team has developed a classification model for categorizing SMS messages into two types: ham and spam (useful and non-useful) using three models: SVM, LSTM, and Regularized Logistic Regression, utilizing libraries. The results show that both models achieved relatively high accuracy. Additionally, the team applied the knowledge learned about Natural Language Processing to perform Text Mining (data extraction and processing of text data).

## Limitations and Directions for Development
### Limitations
The rate of misclassifying spam as ham is not yet optimized. In the classification of messages into ham and spam groups, accuracy is not fully achieved, leading to inconvenience when messages labeled as 'ham' are actually 'spam', or useful messages are mislabeled as 'spam', resulting in loss of important information for users. Due to limited research time, the input dataset used by the team is the Kaggle dataset, which has not been able to exploit and collect real-time input data from SMS messages from network providers.
### Development Directions
Mispredictions may also be due to unbalanced data in terms of spam and ham. To address this, development steps are needed in the data collection phase:
Building a large and diverse dataset with examples of both ham and spam messages. This helps the model learn common characteristics of both types of messages. Alternatively, using balancing methods such as Under-sampling, Over-sampling, or a combination of both to avoid imbalance in the data.
Regularly updating the model: Continuously updating the model with new data to ensure it can identify new signs of spam messages. However, when obtaining information about the content of SMS messages, it is also necessary to ensure the security of personal information.
