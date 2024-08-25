curl -fsSL https://raw.githubusercontent.com/linuxbrew/install/master/install.sh | bash

brew update && brew upgrade

brew install python@3

pip3 install mlflow==1.20.0

export MLFLOW_TRACKING_URI=http://localhost
export MLFLOW_S3_ENDPOINT_URL=http://localhost:9000

git clone https://github.com/simbakot/mlflow_example.git
cd mlflow_example

mlflow run . -m S3://mlflow/0/98bdf6ec158145908af39f86156c347f/artifacts/model -p 1234
