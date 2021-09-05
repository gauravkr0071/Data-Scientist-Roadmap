### __Ensemble Machine Learning Approach__

An ensemble is a composite model, combines a series of low performing classifiers with the aim of creating an improved classifier. Here, individual classifier vote and final prediction label returned that performs majority voting. Ensembles offer more accuracy than individual or base classifier. Ensemble methods can parallelize by allocating each base learner to different-different machines. Finally, you can say Ensemble learning methods are meta-algorithms that combine several machine learning methods into a single predictive model to increase performance. Ensemble methods can decrease variance using bagging approach, bias using a boosting approach, or improve predictions using stacking approach.
![image](https://user-images.githubusercontent.com/51910127/132134550-424f5501-ea18-42c4-8562-6ba5455a7248.png)

1. __Bagging__ stands for bootstrap aggregation. It combines multiple learners in a way to reduce the variance of estimates. For example, random forest trains M Decision Tree, you can train M different trees on different random subsets of the data and perform voting for final prediction. Bagging ensembles methods are Random Forest and Extra Trees.
2. __Boosting algorithms__  are a set of the low accurate classifier to create a highly accurate classifier. Low accuracy classifier (or weak classifier) offers the accuracy better than the flipping of a coin. Highly accurate classifier( or strong classifier) offer error rate close to 0. Boosting algorithm can track the model who failed the accurate prediction. Boosting algorithms are less affected by the overfitting problem. The following three algorithms have gained massive popularity in data science competitions.
- AdaBoost (Adaptive Boosting)
- Gradient Tree Boosting
- XGBoost
3. __Stacking(or stacked generalization)__ is an ensemble learning technique that combines multiple base classification models predictions into a new data set. This new data are treated as the input data for another classifier. This classifier employed to solve this problem. Stacking is often referred to as blending. 
![image](https://user-images.githubusercontent.com/51910127/132134651-10a3a430-4fea-49a8-bc54-0b7a05689493.png)

On the basis of the arrangement of base learners, ensemble methods can be divided into two groups: In parallel ensemble methods, base learners are generated in parallel for example. Random Forest. In sequential ensemble methods, base learners are generated sequentially for example AdaBoost.

On the basis of the type of base learners, ensemble methods can be divided into two groups: homogenous ensemble method uses the same type of base learner in each iteration. heterogeneous ensemble method uses the different type of base learner in each iteration.

### __Boosting vs. Bagging__ \

Bagging doesn’t work so well with stable models.
Boosting might still help.
- Boosting might hurt performance on noisy datasets. Bagging doesn’t have this problem
- In practice bagging almost always helps.
- On average, boosting helps more than bagging, but it is also more common for boosting to hurtperformance.
- The weights grow exponentially.
- Bagging is easier to parallelize.
