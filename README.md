**Fake News Detection using BERT**
**Problem Statement**
The rapid spread of misinformation through online news platforms and social media has become a serious issue. Fake news can mislead the public, influence opinions, and create social and political instability. Manually verifying every news article is difficult and time-consuming.

The objective of this project is to build an automated system that can classify news articles as Real or Fake using Natural Language Processing (NLP) and deep learning techniques.



**Approach**

Dataset Preparation

The dataset contains **44,898** news samples with two columns:

content – combined news text

label – classification (0 = Fake, 1 = Real)

The dataset is balanced:

**Real News**: 23,481

**Fake News**: 21,417

No missing values were present.



**Preprocessing**

Text data was tokenized using a pretrained tokenizer.

Maximum sequence length was set to **256** tokens.

Dataset was split into training and testing sets.



**Model Training**

The pretrained transformer model was fine-tuned for binary text classification.

Training was performed using a trainer pipeline with batch training and evaluation.



**Deployment**

The trained model was deployed using a simple gradio web interface where users can input a news article and receive a prediction.



**Model Used**

This project uses the pretrained transformer model
**DistilBERT**
for text classification.

**Reasons for choosing this model:**

Faster than full BERT
Lower memory usage
High accuracy for NLP classification tasks
The model was fine-tuned using the
Transformer library.



**Evaluation Metrics**

Model performance was evaluated using standard classification metrics:

**Accuracy**

**Precision**

**Recall**

**F1 Score**
        precision    recall  f1-score   support

           0       1.00      1.00      1.00      4247
           1       1.00      1.00      1.00      4733

    accuracy                           1.00      8980
   macro avg       1.00      1.00      1.00      8980
weighted avg       1.00      1.00      1.00      8980

These metrics help measure how well the model correctly identifies fake and real news articles.



**Improvements**

Several improvements were explored to enhance model performance:

Hyperparameter tuning:

Learning rate adjustment

Batch size modification

Increasing maximum sequence length

Fine-tuning transformer layers

Testing with different dataset samples

These experiments helped improve the model's classification capability and robustness.



**Key Learnings**

Through this project, the following concepts were learned:

Data preprocessing for NLP tasks

Tokenization and text encoding

Fine-tuning transformer models

Model evaluation using classification metrics

Deploying machine learning models with
Gradio

Building an end-to-end NLP pipeline from dataset to deployment

This project demonstrates how transformer-based models can effectively detect misinformation in textual data.
