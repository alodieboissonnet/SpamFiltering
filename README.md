# Spam Filtering with Memory-Based and Naive Bayes models
This project has been carried on as part of the final assignment of the L101 module. It aims at studying Memory-Based and Naive Bayes models for Spam Filtering. 

It is composed of multiple elements:
- a PDF report that describes all the work done, presents results and offers analyses about models and results
- a jupyter notebook *spam_filtering.ipynb* that gathers all the code used to preprocessed data and run models
- a jupyter notebook *results.ipynb* that gathers plots to visualise and compare results
- a directory *GenSpam* that gathers data from the GenSpam dataset introduced by Ben Medlock
- a directory *data_tf* that gathers files in which train, adaptation and test data encoded with 700 Term-Frequency attributes
- a directory *data_timbl* that gathers files in which train, adaptation and test data encoded with *m* Boolean attributes, with *m* varying from 50 to 700 by 50
- a csv file *df_pre_processing.csv* that gathers pre-processing training data
- a csv file *timbl_results.csv* that gathers results of all experiments with Memory-Based models
- a csv file *nb_results.csv* that gathers results of all experiments with Memory-Based models


All this work can be found on my GitHub account: [https://github.com/alodieboissonnet/SpamFiltering](https://github.com/alodieboissonnet/SpamFiltering)


## Memory-Based models
Memory-Based models are run thanks to TiMBL Software (Daelemans et al., 2000). To do so, we run in our console the command line: `timbl -f data_timbl/data_700.train -t data_timbl/data_700.test -wgr -dID -k1 +vcs`  
This command line is composed of the following arguments:
- `-f`: file with the train set in the C4.5 format (see Section 2.2 in the report)
- `-t`: file with the adaptation/test set in the C4.5 format
- `-w`: feature-weighting scheme (gr: Gain Ratio, 0: Equal Weights)
- `-d`: distance-weighting scheme (z: Equal Distance, ID: Inverse Distance, IL: Inverse Linear, ED: Exponential Decay)
- `+v`: output format (cs: class statistics with precision, recall, f1-score and AUC metrics)  

Models and parameters selection are carried out with the train and adaptation sets, while methods comparison is realised with the train and test sets.



## Naive Bayes models
Naive Bayes models are run through to their `scikit-learn` implementation for Python. Corresponding code can be found in the *spam_filtering.ipynb* notebook.