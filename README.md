# MLFlow-Basic-Operation


### dagshub
[dagshub](https://dagshub.com/)

MLFLOW_TRACKING_URI=https://dagshub.com/tejas_patni/MLFlow-Basic-Operation.mlflow \
MLFLOW_TRACKING_USERNAME=tejas_patni \
MLFLOW_TRACKING_PASSWORD=6824692c47a4545eac5b10041d5c8edbcef0 \
python script.py

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/tejas_patni/MLFlow-Basic-Operation.mlflow

export MLFLOW_TRACKING_USERNAME=tejas_patni

export MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9353c5b10041d5c8edbcef0

```

<!-- ML Flow on AWS Setup -->

1. Login into AWS console
2. Create IAM User with Adminstrator
3. Export the credential in you AWS CLI by running "aws configure"
4. Create a S3 bucket
5. Create EC2 Machine (Ubuntu) and security group 5000 port

Run the following commands on Ubuntu EC2:

```bash
Sudo apt update
sudo apt install python3-pip
sudo pipx install pipenv
sudo pipx install virtualenv
mkdir mlflow
cd mlflow
pipenv install mlflow
pipenv install awscli
pipenv install boto3
pipenv shell

aws configure
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlops-buc

export MLFLOW_TRACKING_URI=http://ec2-3-109-186-10.ap-south-1.compute.amazonaws.com:5000/

```