# Best-feature-decoding
Supervised by [@mabdelhack](https://github.com/mabdelhack), I atempted to classify fMRI data of seen images using a novel method and compared its performance to commonly used ML methods.

# Data used
We used the data featured in https://www.nature.com/articles/ncomms15037.pdf?fbclid=IwAR1wVvviuO3cQFhTeF-152W2_itsGyqhVgTAT3POGOQa8G6JRvcJ5ugqJT4, produced by the Kamitani lab. 

Data (and associated dataset info) can be found here: https://github.com/KamitaniLab/GenericObjectDecoding/tree/master/data

# Files description

> 1. Functions.ipynb: has all the custom functions used in the workflow. Could be used later to remove redundancy.
> 2. bfd.ipynb: 
  In this notebook, I tested the hypothesis of this project by performing the following steps:
  
      a. Find the images intersecting between imagenet and the fMRI dataset, and use their data only.
      b. Clean the data so that the preferred images features and the fMRI dataset features are present in the same order in different dataframes.
      c. Correlate the features together (per subject, per layer, per roi).
      d. Save the results (can be found at bfd.csv)
      
> then I performed a following experiment on two other methods (logistic regression and SVM), using them to classify the images from feature data. Results can be found
 plotted at others_avg.xlsx.
      
> 3. Logreg.ipynb: In this notebook, I first did a 7-fold cross validation to test 4 different methods on classifying the images using the feature data. Methods used were Logistic regression, SVM, random forest, and Gradient boosting. Thirty images were used for training and 5 for testing, and the mean score for each model across CV attempts was recorded. The output of this experiment is available in the model_scores.csv file. I then did some hyperparameter tuning using random search CV on multinomial logistic regression to classify the images using their feature data. The output of this experiment is available in the best_logreg2.csv file.
