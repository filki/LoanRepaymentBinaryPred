![Contributors](https://img.shields.io/github/contributors/filki/LoanRepaymentBinaryPred?style=for-the-badge&logo=github)
![Release](https://img.shields.io/github/release/filki/LoanRepaymentBinaryPred?style=for-the-badge&logo=github)
![Last_commit](https://img.shields.io/github/last-commit/filki/LoanRepaymentBinaryPred?style=for-the-badge&logo=github)\
![License](https://img.shields.io/github/license/filki/LoanRepaymentBinaryPred?style=for-the-badge&logo=github)




# LoanRepaymentBinaryPred
The aim of this project is to present author skills in data analysis and machine learning fields. Due to author's isnufficient knowledge about banking, the analysis took only the quantitive character.


## Prerequisites
This project can be opened by using ``docker`` and predefined ```Dockerfile```. You'll need to have docker installed locally, see:
https://docs.docker.com/engine/install/.

After sucesfully installing docker on your machine, type
```bash
docker build -t <your-container-name> .
```

to build container using image built on ```Dockerfile```. This way, you won't have to download any dependecies locally, therefore saving management issuess and memory space.

To run the Docker container and set up the network:

```bash
docker run -p 8888:8888 <your-container-name>
```
This command maps port 8888 of the Docker container to port 8888 on your host machine, allowing you to access the Jupyter server through your browser. 

Look for the correct url with authentication token, it should look this

```bash
http://127.0.0.1:8888/tree?token=bd94c3f1484bd27ef10905104cf622ea4ec3a5fd23563ef6
```

Use the URL provided in the terminal (it includes an authentication token) to access the Jupyter server securely. This token ensures that only authorized users can access the Jupyter environment.

## Packages used
* General Purpose
    
* Data Manipulation
    * numpy==1.26.4
    * pandas==2.2.1
* Data Visualization
    * matplotlib==3.8.3
    * seaborn==0.13.2
* Machine Learning
    * scikit_learn==1.4.1.post1
* Statistics
    * scipy==1.12.0




# Data
Data source:
https://www.kaggle.com/datasets/rohitudageri/credit-card-details

Metadata:
* Features name: (Credit_Card.csv)

* Ind_ID: Client ID

* Gender: Gender information

* Car_owner: Having car or not

* Propert_owner: Having property or not

* Children: Count of children

* Annual_income: Annual income

* Type_Income: Income type

* Education: Education level

* Marital_status: Marital_status

* Housing_type: Living style

* Birthday_count: Use backward count from current day (0), -1 means yesterday.

* Employed_days: Start date of employment. Use backward count from current day (0). Positive value means, individual is currently unemployed.

* Mobile_phone: Any mobile phone

* Work_phone: Any work phone

* Phone: Any phone number

* EMAIL_ID: Any email ID

* Type_Occupation: Occupation

* Family_Members: Family size

Another data set (Credit_card_label.csv) contains two key pieces of information

* ID: The joining key between application data and credit status data, same is Ind_ID

*Label: 0 is application approved and 1 is application rejected.
## Data Acquisition
Data was artificially generated.
## Data Preprocessing

After loading the file, copy was created and several approaches were taken. 
Multiple columns were modified to improve data readibility and to reduce curse of dimensionality. Some columns were added to improve variance of dataset.

The process was then split into two strategies:
* NA ignoring

* NA Imputation


Then, numerous visualizations were carried out in search of relationships between variables or other data properties.

Finally, in order for our model to understand categorical data, we've used Label Encoding.



# Results and evaluation
Based on imputed dataframed using the "most frequent" method we've trained DecisionTreeClassifier. After training and predicting, below results were produced:

| class | precision | recall | f1-score | support |
|-------|-----------|--------|----------|---------|
| 0     | 0.94      | 0.86   | 0.90     | 465     |
| 1     | 0.25      | 0.46   | 0.32     | 46      |

As we can see, due to low support of clas 1, model had poor scores in classification of those. Therefore, we will try hyperparameter optimization using 
```GridSearchCV```. 

Below parameters grid used for tuning.
```python
param_grid = {
    'criterion': ['gini', 'entropy'],
    'max_depth': [None, 5, 10, 15],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4],
    'max_features': ['sqrt', 'log2']
}
```

After optimization, below resulsts were produced:
|             | precision | recall | f1-score | support |
|-------------|-----------|--------|----------|---------|
| 0           | 0.91      | 0.99   | 0.95     | 465     |
| 1           | 0.43      | 0.07   | 0.11     | 46      |
| accuracy    |           |        | 0.91     | 511     |
| macro avg   | 0.67      | 0.53   | 0.53     | 511     |
| weighted avg| 0.87      | 0.91   | 0.88     | 511     |

As we cam see, model is surely overtrained, because f1-score of 0 class is much higher, meanwhile the scores for 0 are drastically lower. Therefore, this model failed in predicting.

# Future work

There is possibility that oversampling techniques would benefit our work, due to low support of one class. Furthermore, creating more models using various imputation techniques could aslo bolster search of ideal classifier. Different encoding approaches could also reinforce our model robustness.

Bibliography:

https://docs.docker.com/engine/install/
