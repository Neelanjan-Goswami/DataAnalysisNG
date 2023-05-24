# Fake News Detection using NLP, Machine Learning and Deep Learning.

## Dataset and Publications Used
- The data is obtained from the following   [`dataset`](https://paperswithcode.com/dataset/liar). This contains a decade-long of 12.8K manually labeled short statements were collected in various contexts from POLITIFACT.COM, which provides detailed analysis report and links to source documents for each case.
- [`“Liar, Liar Pants on Fire”:
A New Benchmark Dataset for Fake News Detection`](https://arxiv.org/pdf/1705.00648.pdf%E2%80%8B) and  [ `Fake News Detection Using Machine Learning approaches: A systematic Review`](https://www.researchgate.net/publication/336436870_Fake_News_Detection_Using_Machine_Learning_approaches_A_systematic_Review) helped me understand the problem and get a understanding of the topic.

## Goals of the Project
This is unmistakably a "binary classification problem," where we must determine if a news report or assertion is false or not.
The actions listed below must be taken:  
1. Preprocessing of data. We divided the data into training, testing, and validation sets in the ratio 70:15:15.
2. We use the GINI Gain and Entropy criterion while running "Decision trees" with various ***(depths)*** ranging from 4 to 20. We examine which depth and criterion combination produces the highest level of accuracy on the test set.
3. We use 50% of the data to train weak decision tree classifiers with a depth of 3. We use 100 of these classifiers, and the winner is decided by majority voting. This is what creates our "random forest"
4. For different values of n estimators from 4 to 20, we are now utilising the Adaboost boosting strategy to attempt to enhance the performance of the Decision Tree we selected in Part 2.
5. To identify bogus news, we classify it using SVM and logistic regression.
6. To classify fake news, we deploy "Artificial Neural Networks."



### File Structure  
- `FakeNewsDetectionModel.ipynb` -> Jupyter Notebook with ML Model  
- `Validation_date.tsv` , `test_data.tsv` and `train_data.tsv`  -> Dataset
- `Project Report` - Report specifying the project
- `Project Presentation.pptx` - Project Presentation for Project Explanation.