# __mAP (mean Average Precision) for Object Detection__

![Capture](https://user-images.githubusercontent.com/51910127/132707789-52f5b62c-bca7-4287-94f1-1a5d3c416fc6.PNG)


- if IOU is greater than prescribed thershold, than it is TP(true positive)
- Precision =(TP)/(TP+FP)
1. TP+FP= number of bounding box suggested/detected by trained model
2. TP= Number of Bounding boxes that has IOU > certain thershold and correctly detecting the object
- Recall = (TP)/(TP+FN) 
1. TP+FN= Number of Grounf Truth box presnt in the image
