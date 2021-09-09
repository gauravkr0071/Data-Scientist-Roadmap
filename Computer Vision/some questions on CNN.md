### __some questions on CNN__

- __Difference between SGD and GD__

![image](https://user-images.githubusercontent.com/51910127/132727548-abaac1ec-7308-4e7a-840e-bceb72079bbe.png)

__But SGD has some cons too…__

SGD is much faster but the convergence path of SGD is noisier than that of original gradient descent. This is because in each step it is not calculating the actual gradient but an approximation. So we see a lot of fluctuations in the cost. But still, it is a much better choice.

![image](https://user-images.githubusercontent.com/51910127/132750911-7a298c3d-4513-411e-a237-d91dfedc2e2f.png)

We can see the noise of SGD in the above contour plot. It is to be noted that vanilla GD takes a fewer number of updates but each update is done actually after one whole epoch. SGD takes a lot of update steps but it will take a lesser number of epochs i.e. the number of times we iterate through all examples will be lesser in this case and thus it is a much faster process.

As you can see in the plot there is a third variant of gradient descent known as Mini-batch gradient descent. This is a process that uses the flexibility of SGD and the accuracy of GD. In this case, we take a fixed number(known as batch size) of training examples at a time and compute the cost and corresponding gradient. Then we update the weights and continue the same process for the next batch. If batch size = 1 then it becomes SGD and if batch size = m then it becomes normal GD.
