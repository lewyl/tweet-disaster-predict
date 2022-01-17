# Tweet Disaster Prediction using LSTM

## Data
The dataset consists of 10,000 tweets that are hand classified. The task is to predict whether the tweet is about real disasters or not.

### Data augmentation
Data augmentation is used to expand data on imbalanced dataset, since acquiring and labeling data is expensive and time-consuming.

The data augmentation method used is **synonym replacement**, i.e. randomly sample words that are not stop words and replace them with their corresponding synonyms. 
In this task, each tweet has two words replaced using their synonyms. For example, “This exam is pretty hard.” is augmented to “This test is pretty difficult.”

To know whether a pair of words are synonyms, **GloVe word embeddings** are used. You can download them from https://www.kaggle.com/rtatman/glove-global-vectors-for-word-representation

## Model
A simple LSTM model is used for this task, built using TensorFlow with Keras. Two models with the same hyperparameters were trained on the imbalanced original data and balanced augmented data respectively. It is shown that data augmentation improves the model performance on the validation data (measured by ROC AUC score).
