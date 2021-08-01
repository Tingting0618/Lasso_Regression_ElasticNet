# Lasso Regression and ElasticNet

- Least Absolute Shrinkage and Selection Operator Regression (usually simply called Lasso Regression) is another regularized version of Linear Regression.

- Just like Ridge Regression, it adds a regularization term to the cost function, but it uses the ℓ1 norm of the weight vector instead of half the square of the ℓ2 norm. 

- An important characteristic of Lasso Regression is that it tends to eliminate the weights of the least important features (i.e., set them to zero).

![2021-08-01 10_09_12-Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow_ Concepts, To](https://user-images.githubusercontent.com/44503223/127775933-abcf2c26-6c6e-4049-b805-285b9b12ed4c.png)

In general, Elastic Net is preferred over Lasso because Lasso may behave erratically when the number of features is greater than the number of training instances or when several features are strongly correlated.

#### Content Includes:
- Lasso Regression
- Elastic Net

#### Lasso Regression
- Perform Lasso Regression with Scikit-Learn using a closed-form solution.

  ```python
  from sklearn.linear_model import Lasso
  lasso_reg = Lasso(alpha=0.1)
  lasso_reg.fit(X, y)
  ```
 
- Perform Lasso Regression using Stochastic Gradient Descent by adding a regularization term to the cost function equal to the ℓ1 norm of the weight vector.

  ```python
  from sklearn.linear_model import SGDRegressor
  sgd_reg = SGDRegressor(penalty="l1")
  sgd_reg.fit(X, y.ravel())
  y_predict_SGD = sgd_reg.predict(X)
  ```
  ![download](https://user-images.githubusercontent.com/44503223/127775996-e91ead3c-8d74-45cd-bae7-04d71364ecdf.png)

#### Elastic Net

Elastic Net is a middle ground between Ridge Regression and Lasso Regression. The regularization term is a simple mix of both Ridge and Lasso’s regularization terms, and you can control the mix ratio r. When r = 0, Elastic Net is equivalent to Ridge Regression, and when r = 1, it is equivalent to Lasso Regression.

In general, Elastic Net is preferred over Lasso because Lasso may behave erratically when the number of features is greater than the number of training instances or when several features are strongly correlated.

![2021-08-01 10_14_22-Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow_ Concepts, To](https://user-images.githubusercontent.com/44503223/127776104-c2d2286c-23e7-4a3b-8064-772edba10854.png)

  ```python
  from sklearn.linear_model import ElasticNet
  elastic_net = ElasticNet(alpha=0.1, l1_ratio=0.5) #l1_ratio corresponds to the mix ratio r
  elastic_net.fit(X, y)
  y_predict_elastic_net = elastic_net.predict(X)
  ```
  
## Learn More

For more information, please check out the [Project Portfolio](https://tingting0618.github.io).

## Reference

This repo is my learning journal following:
- Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition, by Aurélien Géron (O’Reilly). Copyright 2019 Kiwisoft S.A.S., 978-1-492-03264-9.
