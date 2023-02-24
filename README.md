# Team-Snowflakes

## Cyclica Challenge

### Introduction

Teaming up as mainly Statistics students, we decided to work on the Cyclica challenge and explore the world of Bioinformatics. We learned more about AlphaFold2 protein structures and different binding sites. We chose this challenge because this problem hasn't been completely solved in the real world yet. We 
ran into various modelling and computation issues given how largely imbalanced this dataset was. Through many days of model training and data analysis, the one and only customized prediction for Cyclica data has been created through the genius minds of four.

### What we did

Our goal is to build a classification model to predict the drug binding sites on AlphaFold2-predicted proteins. We do this by:
- Classifying residue as either a 'drug binding site' or 'non-binding site'
- Listing out the most important features/columns for drug binding

#### Data preprocessing

We did some preliminary data analysis to determine features that are not statistically significant towards predicting the response. After dropping those features, we also converted categorical features to numerical ones (True/False to 1/0). Lastly, for 'feat_SCSASA', we set all negative values to 0. The following features were dropped: 'annotation_sequence', 'feat_C', 'feat_D', 'feat_I', 'feat_K', 'feat_T', 'feat_V', 'annotation_atomrec', 'feat_DSSP_12', 'feat_THETA', 'entry', 'entry_index'.

#### Our model

After trying many different models, we chose a BalancedRandomForestClassifier model with 10-fold cross-validation and got the following results:
- Mean f1 for RBF: 0.195
- Mean recall for RBF: 0.753
- Mean precision for RBF: 0.112
- Mean ROC-AUC for RBF: 0.860
- Mean balanced_accuracy for RBF: 0.771

#### Feature importance

We found the following features to be most important for drug binding:
1) feat_pLDDT
2) coord_X
3) coord_Y
4) coord_Z
5) feat_BBSASA
6) feat_SCSASA

### Challenges

A lot of us were new to ML. So we have to learn about the nuances of certain algorithms like SVM and neural networks as well as deal with an imbalanced dataset. In addition, it was difficult for us to understand the different features because we were unfamiliar with their biochemical context.

Another challenge our team faced was the lack of computation power when processing large amounts of data. This prevented us from fine-tuning any of our models. We partially mitigated this issue by dividing and conquering computational tasks.

### Conclusion

For many of us, it was our first time working in a group environment at a datathon and we are all proud of what we were able to build during the period. Through the implementation of our model, we learned many new concepts like how to work with an imbalanced dataset and how to choose the best model based on evaluation metrics. The biggest takeaway from this event is the importance of collaboration and help among peers to put together a shared vision.




