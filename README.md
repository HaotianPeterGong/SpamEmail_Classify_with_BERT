# SpamEmail_Classify_with_BERT
Spam Email is harmful for users experiences. By detecting unsolicited and unwanted emails, we can prevent spam messages from creeping into the user’s inbox.

## Dataset
Our data set has 5k+ rows with three two columns, binary indicator specifying whether Email is spam or not, raw text messages, and file name. And each row represents one Email. We will use category as label (1: spam, 0: not spam), and raw text messages to extract features.

<img src="pictures/Screen Shot 2022-06-30 at 11.23.56 AM.png" width="350"> 

## Fit BERT - Tokenization
After text cleaning and tokenization, some Email has more than 512 tokens, which is longer than the capacity of base BERT.
So we need to truncate long sentence to several pieces, each having 510 tokens with [CLS] and [SEP] tokens added later. 

## Fit BERT - Feature Extraction
We used the feature of [CLS] position in the last hidden state, a 768-dimensional vector.

To fit the pre-trained BERT, besides input_id, token_type_ids and attention_mask need to be added.

<img src="pictures/Screen Shot 2022-06-30 at 10.57.15 AM.png" width="350">

## Fit BERT - Max Pooling
As each Email corresponding to one label, the dimension of long Email with multiple chunks needs to be reduced.

## Logistic Regression
Extract BERT feature for both training and testing data set. 
