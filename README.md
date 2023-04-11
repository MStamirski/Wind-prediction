# Wind-prediction

Notebook with this project contains a program, which predicts a speed and direction of wind in location selected by user.

It is based on data provided on the website https://map.neweuropeanwindatlas.eu/

Program downloads data from area around chosen coordinates. These data consist of wind speed (in m/s) and direction (in degrees) in nodes of gride, distant from each other by 3 kilometers.

Four periods of prediction are assumed: 1.5 hour, 3 hours, 6 hours and 12 hours.
For each of them a separate algorithm was developped. 

In 1.5 and 3 hours prediction, calculations use matrix of 9x9 nodes (with chosen location placed in the middle), and MLPRegressor model of neural network.

In 6 hours prediction, calculations use the matrix of 15x15 nodes and Sequential model of neural network.

In 12 hours prediction, calculations use also matrix 15x15 and neural network model with convolutional layer.

All hyperparameters were optimized for each model and prediction period separately.

User can chose years from which traning and testing data are collected (both from range 1989-2018).

As a result program shows MAE and MAPE metrics, calculated for predictions as well as for baseline model, which gives data from a day of prediction as a prediction. The negative difference between metrics of these two models signifies, that predictions are valuable.

Comparisons are also showed on diagrams and animations.

Project is described in details on my Medium:

https://medium.com/@maciej_stamirski/wind-forecasting-using-neural-networks-390486be7bf
