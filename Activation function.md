- __What is an activation function?__
Simply put, an activation function is a function that is added into an artificial neural network in order to help the network learn complex patterns in the data. When comparing with a neuron-based model that is in our brains, the activation function is at the end deciding what is to be fired to the next neuron. That is exactly what an activation function does in an ANN as well. It takes in the output signal from the previous cell and converts it into some form that can be taken as input to the next cell. The comparison can be summarized in the figure below.
![image](https://user-images.githubusercontent.com/51910127/131912295-97428d0a-fca4-4b60-be53-d790be9d1bee.png)

- __Why is there a need for it?__ \
There are multiple reasons for having non-linear activation functions in a network.
Apart from the biological similarity that was discussed earlier, they also help in keeping the value of the output from the neuron restricted to a certain limit as per our requirement. This is important because input into the activation function is W*x + b where W is the weights of the cell and the x is the inputs and then there is the bias b added to that. This value if not restricted to a certain limit can go very high in magnitude especially in case of very deep neural networks that have millions of parameters. This will lead to computational issues. For example, there are some activation functions (like softmax) that out specific values for different values of input (0 or 1).
The most important feature in an activation function is its ability to add non-linearity into a neural network. To understand this, let’s consider multidimensional data such as shown in the figure below:

A linear classifier using the three features(weight, Systolic Blood Pressure and Age in this figure) can give us a line through the 3-D space but it will never be able to exactly learn the pattern that makes a person a smoker or a non-smoker(the classification problem in hand) because the pattern that defines this classification is simply not linear. In come the artificial neural networks. What if we use an ANN with a single cell but without an activation function. So our output is basically W*x + b. But this is no good because W*x also has a degree of 1, hence linear and this is basically identical to a linear classifier.
What if we stack multiple layers. Let’s represent nᵗʰ layer as a function fₙ(x). So we have:
o(x) = fₙ(fₙ₋₁(….f₁(x))

However, this is also not complex enough especially for problems with very high patterns such as that faced in computer vision or natural language processing.
In order to make the model get the power (aka the higher degree complexity) to learn the non-linear patterns, specific non-linear layers (activation functions) are added in between.

- __Desirable features of an activation function___
Vanishing Gradient problem: Neural Networks are trained using the process gradient descent. The gradient descent consists of the backward propagation step which is basically chain rule to get the change in weights in order to reduce the loss after every epoch. Consider a two-layer network and the first layer is represented as f₁(x) and the second layer is represented as f₂(x). The overall network is o(x) = f₂(f₁(x)). If we calculate weights during the backward pass, we get o`(x) = f₂(x)*f₁`(x). Here f₁(x) is itself a compound function consisting of Act(W₁*x₁ + b₁) where Act is the activation function after layer 1. Applying chain rule again, we clearly see that f₁`(x) = Act(W₁*x₁ + b₁)*x₁ which means it also depends directly on the activation value. Now imagine such a chain rule going through multiple layers while backpropagation. If the value of Act() is between 0 and 1, then several such values will get multiplied to calculate the gradient of the initial layers. This reduces the value of the gradient for the initial layers and those layers are not able to learn properly. In other words, their gradients tend to vanish because of the depth of the network and the activation shifting the value to zero. This is called the vanishing gradient problem. So we want our activation function to not shift the gradient towards zero. \

Zero-Centered: Output of the activation function should be symmetrical at zero so that the gradients do not shift to a particular direction. 


Computational Expense: Activation functions are applied after every layer and need to be calculated millions of times in deep networks. Hence, they should be computationally inexpensive to calculate. \


Differentiable: As mentioned, neural networks are trained using the gradient descent process, hence the layers in the model need to differentiable or at least differentiable in parts. This is a necessary requirement for a function to work as activation function layer.

- __How to use them in deep neural networks?__
Tanh and sigmoid cause huge vanishing gradient problems. Hence, they should not be used.

Start with ReLU in your network. Activation layer is added after the weight layer (something like CNN, RNN, LSTM or linear dense layer) as discussed above in the article. If you think the model has stopped learning, then you can replace it with a LeakyReLU to avoid the Dying ReLU problem. However, the Leaky ReLU will increase the computation time a little bit. \
If you also have Batch-Norm layers in your network, that is added before the activation function making the order CNN-Batch Norm-Act. Although the order of Batch-Norm and Activation function is a topic of debate and some say that the order doesn’t matter, I use the order mentioned above just to follow the original Batch-Norm paper. \

Activation functions work best in their default hyperparameters that are used in popular frameworks such as Tensorflow and Pytorch. However, one can fiddle with the negative slope in LeakyReLU and set it to 0.02 to expedite learning.

![image](https://user-images.githubusercontent.com/51910127/131914369-661eb17b-4db1-4280-88b8-697614358fc4.png)
![image](https://user-images.githubusercontent.com/51910127/131914427-2f06d61d-c402-48d6-a0fd-571c63a0d550.png)
![image](https://user-images.githubusercontent.com/51910127/131914480-dfae0496-2fcf-4a59-aadf-7e4574f02183.png)
![image](https://user-images.githubusercontent.com/51910127/131914576-ecf23059-37aa-4e2d-8491-432c82bcd99b.png)
![image](https://user-images.githubusercontent.com/51910127/131914662-69cb8676-de5a-4f6c-8f8a-ee499c2d42f5.png)
![image](https://user-images.githubusercontent.com/51910127/131914712-cf2a8cc0-f221-4a78-9771-3c9689edd55c.png)
![image](https://user-images.githubusercontent.com/51910127/131914780-c65079d7-647e-484a-96d7-bda70e888166.png)
![image](https://user-images.githubusercontent.com/51910127/131914881-4ff09431-3a26-4b0c-9bee-5656f5b7ca0c.png)
![image](https://user-images.githubusercontent.com/51910127/131914930-f28e27da-0250-4eaa-8488-9f2ab04050c3.png)
![image](https://user-images.githubusercontent.com/51910127/131914966-a1966529-b84b-42a1-842a-39378166b452.png)
