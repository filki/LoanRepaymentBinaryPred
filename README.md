# LoanRepaymentBinaryPred
The aim of this project is to present author skills in data analysis and machine learning fields. Due to author's isnufficient knowledge about banking, the analysis took only the quantitive character.

Data source:
https://www.kaggle.com/datasets/rohitudageri/credit-card-details
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

```arduino
http://127.0.0.1:8888/tree?token=bd94c3f1484bd27ef10905104cf622ea4ec3a5fd23563ef6
```

Use the URL provided in the terminal (it includes an authentication token) to access the Jupyter server securely. This token ensures that only authorized users can access the Jupyter environment.

### Additional Information

For more details on managing your Docker containers or Jupyter notebooks, refer to the respective official documentation.

## Part one: Quick introduction to dataset

## Part two: EDA and data cleansing
After reading the file using pandas method ```pd.read_csv()```, we can see that some of the values in our dataset are not clear as they should be.

Bibliography:

https://docs.docker.com/engine/install/