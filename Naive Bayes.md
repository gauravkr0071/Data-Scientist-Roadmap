
- __Why Naive Bayes is known as Naive ? what makes it Naive ?__ 
- __What are some assumption in Naive Bayes ?__ \
In naive bayes we assume, [conditional indpendence](https://youtu.be/zpELC6i90Sc?list=PLBv09BD7ez_7-4V3IJIzCHWQj9nd4rVWB) among the features of training data given the class.
But why this is needed ?
Consider a example of 20*20 image, and each pixel of that image can take value 0 or 1.
we can have total possiblities of 2^400 images, clearly no dataset contains images with 
every possiblity of images, here x1, x2,... x400 are  feature of training data.
So what we can do is to count how many times xi takes 0 or 1 value. Here we assume xi are 
__conditionally independent from each other given the class.__

- __Naive Bayes with Continious variable__ : [click here](https://www.youtube.com/watch?v=r1in0YNetG8&list=PLBv09BD7ez_7-4V3IJIzCHWQj9nd4rVWB&index=4)


[Source 1 Naive bayes explained by Josh Stammer](https://www.youtube.com/watch?v=O2L2Uv9pdDA)
