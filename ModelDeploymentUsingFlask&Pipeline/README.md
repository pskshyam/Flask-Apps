# PIMA Indians Diabetes Predictor

This repository shows how to take a trained model to production using Flask and Pipeline.

Our reference example is a logistic regression on the classic Pima Indians Diabetes Dataset which has 8 numeric features and a binary label.

The demo repo contains two packages, the first simulates the training environment and the second simulates the server environment.

## Training
After we split the data, we can train our LogReg and save its coefficients in a json file. Once we have our coefficients in a safe place, we can reproduce our model in any language or framework we like. Concretely we can write these coefficients in the server configuration files. This way, when the server starts, it will initialize the logreg model with the proper weights from the config.

As part of data preprocessing, we have tried a custom transformation **is_adult** on the “age” feature. Let’s try to build this using Pipeline from Scikit-learn and Dill library for serialization. 

```python
def is_adult(x): return x > 18

clf = Pipeline([
    ("mapper", DataFrameMapper([
        (['age'], FunctionTransformer(is_adult)),
        (features, None)
    ])),
    ("classifier", LogisticRegression())
])
```
## Server 
To better simulate the server environment, try running the pipeline somewhere the training modules are not accessible. Make sure that whatever libraries you used to build the model, you must have them installed in your server environment as well. Concretely, if you used Pandas and Sklearn in the training, you should have them also installed in the server side in addition to Flask or Django or whatever you want to use to make your server.

```python
# run this anywhere and change the pipeline.pk path
import dill
from pandas import read_csv

url = "https://raw.githubusercontent.com/baatout/ml-in-prod/master/pima-indians-diabetes.csv"
features = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age']
label = 'label'
dataframe = read_csv(url, names=features + [label])
X = dataframe[features]
Y = dataframe[label]

with open('pipeline.pk', 'rb') as f:
    clf = dill.load(f)

print clf.score(X, Y)
```

## Building the pipeline
```python
$ cd training
$ virtualenv venv
$ source venv/bin/activate
$ pip install -r requirements.txt
$ python training.py
```
## Running the server
```python
$ cd ../; deactivate
$ cd server
$ virtualenv venv
$ source venv/bin/activate
$ pip install -r requirements.txt
$ python main.py
```

## Making online predictions
Once the server is running you can send features via POST requests and then receive the corresponding prediction (0 or 1). You can find an example of the request body in server/post.json:

`$ curl -H "Content-Type: application/json" -X POST --data @post.json http://localhost:5000/predict`

Source: https://medium.com/contentsquare-engineering-blog/machine-learning-in-production-c53b43283ab1
