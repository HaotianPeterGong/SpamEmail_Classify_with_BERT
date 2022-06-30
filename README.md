# SpamEmail_Classify_with_BERT
Spam Email is harmful for users experiences. By detecting unsolicited and unwanted emails, we can prevent spam messages from creeping into the user’s inbox.

# Dataset
Our data set has 5k+ rows with three two columns, binary indicator specifying whether Email is spam or not, raw text messages, and file name. And each row represents one Email. We will use category as label (1: spam, 0: not spam), and raw text messages to extract features.

<img src="pictures/Screen Shot 2022-06-30 at 11.23.56 AM.png" width="350"> 

# Fit BERT - Tokenization
After text cleaning and tokenization, some Email has more than 512 tokens, which is longer than the capacity of base BERT.
So we need to truncate long sentence to several pieces, each having 510 tokens with [CLS] and [SEP] tokens added later. 

# Fit BERT - Feature Extraction
We used the feature of [CLS] position in the last hidden state, a 768-dimensional vector.

<img src="pictures/Screen Shot 2022-06-30 at 10.57.15 AM.png" width="350">
