### __Bias and Variance__

__Conceptual definition :__
 - __Bias__ \
The error due to bias is taken as the difference between the expected (or average) prediction of our model and the correct value which we are trying to predict. Of course you only have one model so talking about expected or average prediction values might seem a little strange. However, imagine you could repeat the whole model building process more than once: each time you gather new data and run a new analysis creating a new model. Due to randomness in the underlying data sets, the resulting models will have a range of predictions. __Bias measures how far off in general these models' predictions are from the correct value.__
 - __Variance__ \
 The error due to variance is taken as the variability of a model prediction for a given data point. Again, imagine you can repeat the entire model building process multiple times. __The variance is how much the predictions for a given point vary between different realizations of the model.__ \
 




More complex models will, in general, perform better on training data than simpler ones. Complex models have more parameters that can be adjusted during training to get a good fit to the desired result. Therefore, their error-rate when measured on the data-set used for training will usually be lower.

However, a model that is too complex can end up over-fitting to random effects that are present only in the specific data-set used for training. If these random effects are not present in new data when the model is asked to make predictions, then the model will produce incorrect results when it tries to use them. To judge whether this is happening, measure the model's error-rate on a validation data-set that was not used during training.

- A high error-rate on both training and validation data indicates that the model may be too simple to faithfully capture any relationships present in the data. In this case, the model is said to have high bias.
- If the error-rate is low on training data but high on validation data, then the model may be too complex - it suffers from high variance.

A complex model exhibiting high variance may improve in performance if trained on more data samples. Learning curves, which show how model performance changes with the number of training samples, are a useful tool for studying the trade-off between bias and variance.

Typically, the error-rate on training data starts off low when the number of samples is small, and increases as more samples are used (because a larger training set is harder to fit to). On the other hand, the error-rate on validation data is typically high for a model trained on very few samples and decreases with more training (because the relationships learned during training are more likely to be valid for new data).

If the validation error-rate remains much higher than the training data error rate even when the training set is large, then the model is over-fitting and could benefit from reduced complexity. There are several ways to vary the complexity of a model to try to improve its performance:

- Using fewer features reduces model complexity. However, inadvertently removing key features that are important for prediction can quickly make your model too simplistic to perform well. An alternative is to apply regularization, which allows the model to exploit all features but penalizes it based on the number it uses.
- Increasing the number and size of layers used in a neural network model, or the number and depth of trees used in a random forest model, increases model complexity.

![image](https://user-images.githubusercontent.com/51910127/130131447-538bb39c-b23c-459a-a680-7af54c3cb369.png)
![image](https://user-images.githubusercontent.com/51910127/130131518-094d8d45-3e80-4619-b683-a3156de220ef.png)
![image](https://user-images.githubusercontent.com/51910127/130131556-1015e330-31a8-4da1-a80a-b28e161df9a7.png)

Figure 1. Learning curves showing measured error for different regression models applied to a prediction problem. The top-most chart is for a simple model which uses very few features but is already reasonably accurate. Adding more features reduces error on both training and validation data (middle chart). But when complexity is increased again with yet more features (bottom chart), training error improves but validation error does not - a sign that the model Is now beginning to over-fit.

[Source 1- Understanding the Bias-Variance Tradeoff](http://scott.fortmann-roe.com/docs/BiasVariance.html#fnref:1)\
[Bias-variance trade-off.pdf](https://github.com/gauravkr0071/Data_Structures_and_Algorithms/files/7017420/Bias-variance.trade-off.I.m.always.confusing.the.two._.by.Super.Albert._.The.Making.Of.a.Data.Scientist._.Medium.pdf)\
[Finding the right model complexity using Regularization.pdf](https://github.com/gauravkr0071/Data_Structures_and_Algorithms/files/7017418/Finding.the.right.model.complexity.using.Regularization._.by.Sufyan.Khot._.Towards.Data.Science.pdf)
