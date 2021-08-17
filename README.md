## Prediction Model

# Create virtual environment
python3 -m pip install virtualenv

virtualenv --version
virtualenv 20.7.1 from /home/suhas/.local/lib/python3.6/site-packages/virtualenv/__init__.py

virtualenv venv_package
source venv_package/bin/activate

# Add following in ~/.bashrc and source bashrc
PYTHONPATH=/home/suhas/code/packages/prediction_model:$PYTHONPATH

export PYTHONPATH

or

export PYTHONPATH='/home/suhas/code/package_superman/prediction_model'

Reopen the terminal and test using ----------> echo $PYTHONPATH

pip install -r requirements.txt
# To create pickle file
python packages/prediction_model/prediction_model/train_pipeline.py

pytest -v #in tests folder

================== Install and consume pacakged ML Model ===========================
python3 setup.py sdist bdist_wheel
pip install -e .   (where setup file is located)

start python ------------> python3

import prediction_model
from prediction_model import train_pipeline
from prediction_model.predict import make_prediction
import pandas as pd

# Save pickle object of trained model
train_pipeline.run_training()

# Load external data
test_data = pd.read_csv("/home/suhas/code/test.csv")

# Make prediction
result = make_prediction(test_data[0:1])

print(result)
=============================================================
{'prediction': ['Y']}
=============================================================