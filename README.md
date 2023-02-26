## install mlflow with conda
https://anaconda.org/conda-forge/mlflow
```
conda install -c conda-forge mlflow
```

## run ui
```
mlflow ui -p 5100
```

## run serve
### run model serve
```
mlflow models serve --model-uri runs:/893a65ab50e7479dbe12835059cc318f/model --port 5101
```

### run inference
```
curl -X POST -H "Content-Type:application/json" --data '{"dataframe_split": {"columns":["alcohol", "chlorides", "citric acid", "density", "fixed acidity", "free sulfur dioxide", "pH", "residual sugar", "sulphates", "total sulfur dioxide", "volatile acidity"],"data":[[12.8, 0.029, 0.48, 0.98, 6.2, 29, 3.33, 1.2, 0.39, 75, 0.66]]}}' http://127.0.0.1:5101/invocations
```
