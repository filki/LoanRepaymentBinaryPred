![Contributors](https://img.shields.io/github/contributors/:filki:LoanRepaymentBinaryPred



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




## Part one: Quick introduction to dataset
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
In the beggining we load file using pandas method ```pd.read_csv()```. Then, using ```df.head()```
method we are able to see the first glimpse on our data. As with all data, there is a place for improvement.
## Code Structure

## Results and evaluation

## Future work

Bibliography:

https://docs.docker.com/engine/install/
