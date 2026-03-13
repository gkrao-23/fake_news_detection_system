**Mini Project**
# **Fake News Detection using BERT**



## Problem Statement
The rapid spread of misinformation through online news platforms and social media has become a serious issue. Fake news can mislead the public, influence opinions, and create social and political instability. Manually verifying every news article is difficult and time-consuming.

The objective of this project is to build an automated system that can classify news articles as Real or Fake using Natural Language Processing (NLP) and deep learning techniques.



## **Approach**

**Dataset Preparation**

The dataset contains **44,898** news samples with 4 columns.
title, text, subject, date .


As subject and date columns were not necessary, I combined title and text into content column and created a label column, so final dataset consists of


- content – combined news text (title+text column)
- label – classification (0 = Fake, 1 = Real)

The dataset is balanced:

**Real News**: 23,481

**Fake News**: 21,417

No missing values were present.

**Kaggle dataset link**- https://www.kaggle.com/datasets/emineyetm/fake-news-detection-datasets



## **Preprocessing**

Text data was tokenized using a pretrained tokenizer.

Maximum sequence length was set to **256** tokens.

Dataset was split into training and testing sets.



## **Model Training**

**Model Used**

This project uses the pretrained transformer model
**DistilBERT**
for text classification.

The pretrained transformer model was fine-tuned for binary text classification.

Training was performed using a trainer pipeline with batch training and evaluation.

**Reasons for choosing this model:**

--Faster than full BERT
--Lower memory usage
--High accuracy for NLP classification tasks
--The model was fine-tuned using the
--Transformer library.



## **Evaluation Metrics**

Model performance was evaluated using standard classification metrics:

**Accuracy**, **Precision**, **Recall**, **F1 Score**



                  precision    recall  f1-score   support

           0       1.00      1.00      1.00      4247
           1       1.00      1.00      1.00      4733

    accuracy        -          -       1.00      8980
   macro avg       1.00      1.00      1.00      8980
weighted avg       1.00      1.00      1.00      8980

These metrics help measure how well the model correctly identifies fake and real news articles.

**Model accuracy** -**100%**
with 3 epochs 


learning_rate=3e-5, 


per_device_train_batch_size=16,


per_device_eval_batch_size=16,


        
Max Length     	Accuracy
256	             100% with 3 epochs
512	             100% with 2 epochs


The model achieved 100% accuracy on the validation set, and no misclassified samples were found. This indicates that the model learned strong patterns in the dataset. However, perfect performance on a validation set may also indicate that the dataset is relatively easy or that the model may be slightly overfitting.


## **Improvements**

- Several improvements were explored to enhance model performance:

- Hyperparameter tuning:

- Learning rate adjustment

- Batch size modification

- Increasing maximum sequence length

- Fine-tuning transformer layers

- Testing with different dataset samples

- These experiments helped improve the model's classification capability and robustness.


## **Deployment**

The trained model was deployed using a simple **gradio** web interface where users can input a news article and receive a prediction.
https://5fb2a85f65e8df7f68.gradio.live/
A simple web interface was created using Gradio where users can input news text. The trained DistilBERT model processes the text and predicts whether the news is fake or real.


## **Key Learnings**

Through this project, the following concepts were learned:

Data preprocessing for NLP tasks

Tokenization and text encoding

Fine-tuning transformer models

Model evaluation using classification metrics

Deploying machine learning models with Gradio

Building an end-to-end NLP pipeline from dataset to deployment

This project demonstrates how transformer-based models can effectively detect misinformation in textual data.
