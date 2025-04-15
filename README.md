# MLFlow-demo

## For Dagshub:

MLFLOW_TRACKING_URI=https://dagshub.com/Durgeshsingh12712/MLFlow-demo /
MLFLOW_TRACKING_USERNAME=Durgeshsingh12712 \
MLFLOW_TRACKING_PASSWORD= \
python script.py



```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/Durgeshsingh12712/MLFlow-demo

export MLFLOW_TRACKING_USERNAME=Durgeshsingh12712

export MLFLOW_TRACKING_PASSWORD=


```


# MLflow on AWS

## MLflow on AWS Setup:

1. Login to AWS console.
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo apt install pipenv

sudo apt install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials
aws configure


#Finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://s3bucketname # s3bucketname=bucket name

#open Public IPv4 DNS to the port 5000


#set uri in your local terminal and in your code 
export MLFLOW_TRACKING_URI=http://ec2-54-147-36-34.compute-1.amazonaws.com:5000/
```