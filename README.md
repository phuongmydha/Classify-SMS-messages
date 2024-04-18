# Natural Language Processing
Text Processing: strip special characters, removing stopwords, Tokenization and Lemmatization
Using Machine Learning model: SVM, MaxEnt; and deep learning LSTM  model to classify sms message is ‘ham’ or ‘spam’


Through the process of research and study, the team has developed a classification model for categorizing SMS messages into two types: ham and spam (useful and non-useful) using three models: SVM, LSTM, and Regularized Logistic Regression, utilizing libraries. The results show that both models achieved relatively high accuracy. Additionally, the team applied the knowledge learned about Natural Language Processing to perform Text Mining (data extraction and processing of text data).
## SVM 
Build a linear SVM classification model for the SMS Spam Collection dataset, with the parameter kernel='linear'. The runtime of the model is measured from the training process to the completion of prediction for the test set.
## MaxEnt - Using Logistic Regression


### Choosing C parameter
<div align="center">  
 <img width="428" alt="l1 performance" src="https://github.com/phuongmydha/NLP/assets/166359916/e83e253b-155b-4224-bce8-936e917fb00f">
 <img width="428" alt="l2 performance" src="https://github.com/phuongmydha/NLP/assets/166359916/31a8cbb0-b4a3-4660-9e6f-46e775c9dd40">
</div>
    
### Choosing models
<div align="center">  
  <img width="428" alt="l1l2" src="https://github.com/phuongmydha/NLP/assets/166359916/9eb3ff91-1cfa-4a01-9ab3-df236320c499">
</div>


## LSTM

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <p>To build an LSTM model, the following steps are undertaken:</p>
  <ol>
    <li>Vectorize the data using the Count Vector method. Since the output data will be a sparse matrix, it needs to be converted into a dense array before feeding it into the LSTM model.</li>
    <li>Convert the sparse matrix into a dense array.</li>
    <li>Reshape the data to fit the input requirements of the LSTM model, which necessitates three dimensions: samples, time steps, and features.</li>
    <li>Build the LSTM model using the Keras framework:
      <ul>
        <li>Create a Sequential model.</li>
        <li>Add an LSTM layer with 50 units and define its input shape.</li>
        <li>Add a dropout layer with a rate of 0.5 to mitigate overfitting.</li>
        <li>Add a Dense layer with a sigmoid activation function for binary classification.</li>
      </ul>
    </li>
    <li>Compile the model using the Adam optimizer and binary crossentropy loss function.</li>
    <li>Train the model with 10 epochs and a batch size of 32, while also specifying validation data.</li>
  </ol>
  <p>The choice of epochs and batch size balances between model learning capacity and computational efficiency. Too few epochs or a small batch size might lead to underfitting, while too many epochs or a large batch size might lead to overfitting or increased training time. The Adam optimizer is chosen for its popularity and efficiency, and binary crossentropy loss is used for binary classification tasks.</p>
</body>
</html>

After training the algorithm, the team obtained results presented through Learning curves and confusion matrices as shown below:

<div align = "center">
 <img width="602" alt="accuracy" src="https://github.com/phuongmydha/NLP/assets/166359916/f7f004da-5356-4c14-8cbe-c2176d2a3fa6">
</div> 

We observe that as the number of epochs (the number of times the model is trained) increases, the loss (loss index) decreases. With a relatively small loss value, in the range from [0, 0.2], this is a positive sign indicating that the LSTM model is quite effective and performs well on both the training and validation sets.
Additionally, we see that as the number of epochs increases, the Accuracy on both the training and validation sets also increases. With a high Accuracy index on the validation set, in the range from [0.96, 0.98], we can consider this model capable of making highly accurate predictions on new data.
From the graph, with the number of epochs = 6, the highest accuracy for the model will be achieved, with an accuracy at epoch = 6 of 0.975 on the validation set.





## Models Evaluation

![cm_lstm](https://github.com/phuongmydha/NLP/assets/166359916/ec6c3b9f-7f9f-4ddb-a3ec-e7685dc0f8ee)
![cm_maxent](https://github.com/phuongmydha/NLP/assets/166359916/ed765769-6d60-41e0-b4ee-4050c9de18f1)
![cm_svm](https://github.com/phuongmydha/NLP/assets/166359916/15c72963-f2b1-43c1-96c2-2f6c0a724dce)


## Summary of Model Evaluation Metrics

![result](https://github.com/phuongmydha/NLP/assets/166359916/3957114d-ad19-45a7-9c3f-117cd1157d67)



## Limitations and Directions for Development
### Limitations
The rate of misclassifying spam as ham is not yet optimized. In the classification of messages into ham and spam groups, accuracy is not fully achieved, leading to inconvenience when messages labeled as 'ham' are actually 'spam', or useful messages are mislabeled as 'spam', resulting in loss of important information for users. Due to limited research time, the input dataset used by the team is the Kaggle dataset, which has not been able to exploit and collect real-time input data from SMS messages from network providers.
### Development Directions
Mispredictions may also be due to unbalanced data in terms of spam and ham. To address this, development steps are needed in the data collection phase:
Building a large and diverse dataset with examples of both ham and spam messages. This helps the model learn common characteristics of both types of messages. Alternatively, using balancing methods such as Under-sampling, Over-sampling, or a combination of both to avoid imbalance in the data.
Regularly updating the model: Continuously updating the model with new data to ensure it can identify new signs of spam messages. However, when obtaining information about the content of SMS messages, it is also necessary to ensure the security of personal information.
