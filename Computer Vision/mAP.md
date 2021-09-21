# __mAP (mean Average Precision) for Object Detection__
[video link](https://www.youtube.com/watch?v=QdWidmgLwbw&list=PL1GQaVhO4f_jE5pnXU_Q4MSrIQx4wpFLM&index=4)
![Capture](https://user-images.githubusercontent.com/51910127/132707789-52f5b62c-bca7-4287-94f1-1a5d3c416fc6.PNG)


- if IOU is greater than prescribed thershold, than it is TP(true positive)
- Precision =(TP)/(TP+FP)
1. TP+FP= number of bounding box suggested/detected by trained model
2. TP= Number of Bounding boxes that has IOU > certain thershold and correctly detecting the object
- Recall = (TP)/(TP+FN) 
1. TP+FN= Number of Ground Truth box presnt in the dataset(image 1 ground truth boxes + image 1 ground truth boxes + image 1 ground truth boxes.....) \
[video Link](https://www.youtube.com/watch?v=jAMxrRw4PMY&list=PL1GQaVhO4f_jE5pnXU_Q4MSrIQx4wpFLM&index=3)
[medium link](https://jonathan-hui.medium.com/map-mean-average-precision-for-object-detection-45c121a31173)


### WHy mAP??

Lets say, you have just 2 classes 0, 1, where the correct result is 1 and wrong one is 0: (eg. like coin toss, where you only consider Heads as a win)

And your actual and predicted results are:
actual  = [1,1,0,0,0] \
pred    = [1,0,1,0,0] \

In this case
TP = 1 -> 1st column
FP = 1 -> 3rd
TN = 2 -> 4,5 cols
FN = 1 -> 2nd col
--------
Tot = 5
--------
Total count here is 5, which is the number of samples/trials in our data.
With this, we can get Precision, Recall etc.

Now, lets say, you have 3 classes 1,2,3:
And your actual and predicted results are:
actual  = [1,1,2,2,3]
pred    = [1,2,3,2,1]

In this case,
TP = 2 -> 1, 4 cols

But how do you get FP/FN/TN?
If you see 2nd col, it can be considered as FP for class 2, but it is also TN for class 3 and FN for class 1.
Similarly, for all other wrong answers, it is not possible to get FP/FN/TN.

So, instead, what we do is calculate on a class by class basis, by a technique called one-vs-rest classification. 
If we are calculating for Class 1, then all other classes are marked as wrong answer (0)

So, the modified table for class 1 becomes:
actual  = [1,1,0,0,0]
pred    = [1,0,0,0,1]

Now,
TP = 1 -> 1st col
FP = 1 -> 5th col
TN = 3 -> 3,4th cols
FN = 1 -> 2nd col

With this we get precision/recall for class 1.

Similarly, the modified table for class 2 and 3 becomes:
actual  = [0,0,2,2,0]
pred    = [0,2,0,2,0]

actual  = [0,0,0,0,3]
pred    = [0,0,3,0,0]

With this we can get P/R/F1 for all classes and then average them out.
