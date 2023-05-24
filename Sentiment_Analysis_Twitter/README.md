## Neelanjan Goswami

## Dataset Information

For sentiment analysis on tweets (a binary classification problem), we employ and contrast a variety of alternative strategies. The training dataset is anticipated to be a csv file of type "tweet_id, sentiment, tweet," where "tweet_id" is the unique number that identifies the tweet, "sentiment" denotes whether the tweet is good or negative, and "tweet" denotes the tweet itself. The test dataset is also a csv file of the format "tweet_id, tweet." Please be aware that the training and test datasets shouldn't have csv headers because they aren't anticipated.  

## Requirements

Some of the project's library needs are broad, while others are method-specific. The following are the prerequisites in general.  
* `numpy`
* `scikit-learn`
* `nltk`
* `scipy`

The following libraries are needed in order to use certain methods:
* `keras` with `TensorFlow` backend for Logistic Regression, MLP, RNN (LSTM), and CNN.
* `xgboost` for XGBoost.

### Preprocessing 

1. Execute 'preprocess.py' on the train and test sets of data. A preprocessed version of the dataset will result from this.
2. Start 'stats.py' and enter '' as the path to the csv produced by 'preprocess.py'. This provides a summary of the dataset's statistical characteristics and will produce two pickle files that represent the frequency distribution of bigrams and unigrams in the training dataset. 

After completing the aforementioned procedures, you should have four files total: preprocessed-train-csv, preprocessed-test-csv, "freqdist," "freqdist-bi," which stand for preprocessed train dataset, preprocessed test dataset, frequency distribution of unigrams, and frequency distribution of bigrams, respectively.

Change the values of 'TRAIN_PROCESSED_FILE', 'TEST_PROCESSED_FILE', 'FREQ_DIST_FILE', and 'BI_FREQ_DIST_FILE' to your own paths in the corresponding files for all the methods that follow. Change the settings of "USE_BIGRAMS" and "FEAT_TYPE" as necessary to get the results utilising the various feature types specified in the report.


### Baseline
3. Run `baseline.py`. With `TRAIN = True` it will show the accuracy results on training dataset.

### Naive Bayes
4. Run `naivebayes.py`. With `TRAIN = True` it will show the accuracy results on 10% validation dataset.

### Maximum Entropy
5. Run `logistic.py` to run logistic regression model OR run `maxent-nltk.py <>` to run MaxEnt model of NLTK. With `TRAIN = True` it will show the accuracy results on 10% validation dataset.

### Decision Tree
6. Run `decisiontree.py`. With `TRAIN = True` it will show the accuracy results on 10% validation dataset.

### Random Forest
7. Run `randomforest.py`. With `TRAIN = True` it will show the accuracy results on 10% validation dataset.

### XGBoost
8. Run `xgboost.py`. With `TRAIN = True` it will show the accuracy results on 10% validation dataset.

### SVM
9. Run `svm.py`. With `TRAIN = True` it will show the accuracy results on 10% validation dataset.

### Multi-Layer Perceptron
10. Run `neuralnet.py`. Will validate using 10% data and save the best model to `best_mlp_model.h5`.

### Reccurent Neural Networks
11. Run `lstm.py`. Will validate using 10% data and save models for each epock in `./models/`. (Please make sure this directory exists before running `lstm.py`).

### Convolutional Neural Networks
12. Run `cnn.py`. This will run the 4-Conv-NN (4 conv layers neural network) model as described in the report. To run other versions of CNN, just comment or remove the lines where Conv layers are added. Will validate using 10% data and save models for each epoch in `./models/`. (Please make sure this directory exists before running `cnn.py`). 

### Majority Vote Ensemble
13. Run "extract-cnn-feats.py saved-model>" to obtain penultimate layer features for the training dataset. Three files, 'train-feats.npy', 'train-labels.txt', and 'test-feats.npy', will be created as a result of this.
14. Run the 'cnn-feats-svm.py' programme, which applies SVM classification to the features taken from the CNN model using the files from the previous step.
15. Run "majority-voting.py" after putting all of the forecast CSV files you wish to take a majority vote in "./results/". 'majority-voting.csv' will be produced as a result.

## Information about other files

* `dataset/positive-words.txt`: List of positive words.
* `dataset/negative-words.txt`: List of negative words.
* `dataset/glove-seeds.txt`: GloVe words vectors from StanfordNLP which match our dataset for seeding word embeddings.
* `Plots.ipynb`: IPython notebook used to generate plots present in report.