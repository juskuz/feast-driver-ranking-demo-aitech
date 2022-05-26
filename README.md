# Feast Driver Ranking Example

Repo contains code presented during Szkoła Majowa AI TECH 2022 . It's an example of using feast based on [this tutorial](https://docs.feast.dev/tutorials/driver-ranking-with-feast) from official Feast website.

Walkthrough is presented in file Driver_Ranking_Tutorial_AITech.ipynb (notebooks/Driver_Ranking_Tutorial_AITech.ipynb).


### Overview

Making a prediction using a linear regression model is a common use case in ML. In this guide tutorial, we build the model that predicts best driver (by driver id).

The basic local mode gives you ability to quickly try Feast.


### Tutorial

1. Install Feast and scikit-learn
```
pip install feast scikit-learn
```

(This tutorial has been tested with Feast==0.21.0)

2. Set up a local feature store (on your laptop).
```
cd driver_ranking/
feast apply
cd ..
```

3. Train a model
```
python train.py
```

4. Load data into your local sqlite online store
```
cd driver_ranking/
feast materialize-incremental 2022-01-01T00:00:00
cd ..
```


5. Test your model with your local sqlite online store

```
python predict.py
```

6.Apply and materialize data.
```
cd driver_ranking/
feast apply
feast materialize-incremental 2022-01-01T00:00:00
cd ..
```

7.  Test your model with your online store

```
python predict.py
```
