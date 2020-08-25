# gcp

## create ubuntu 20.04LTS sever
 - ```sudo apt update```

## install nginx
 - ```sudo apt install nginx```
 
## install python3-pip
 - ```sudo apt install python3-pip```

## install jupyter notebook and setup
 - ```sudo pip3 install numpy pandas jupyter notebook```
 - ```jupyter notebook password```
 - ```jupyter notebook --ip 0.0.0.0 --port 8888```
 
## create storage server

## create gcp jupyter notebook
 > install tensorflow 2.3
 

## create model 
 - ```sudo pip3 install matplotlib sklearn pandas numpy```
 - jupyter notebook   
  ```
  %pylab inline   
  
  import numpy as np   
  from sklearn import datasets, linear_model   
  from sklearn.metrics import mean_squared_error, r2_score

  x_data, y_data = datasets.load_diabetes(return_X_y=True)

  x_data = x_data[:, np.newaxis, 2]

  x_train = x_data[:-20]
  y_train = y_data[:-20]
  x_test = x_data[-20:]
  y_test = y_data[-20:]

  print(x_test.shape)
  print(y_test.shape)
  
  regr = linear_model.LinearRegression()
  regr.fit(x_train, y_train)
  
  y_pred = regr.predict(x_test)

  print('MSE:', mean_squared_error(y_test, y_pred))
  print('R2Score:', r2_score(y_test, y_pred))
  
  scatter(x_test, y_test, color='black')
  plot(x_test, y_pred, color='blue', linewidth=2)
  ```
  
 
