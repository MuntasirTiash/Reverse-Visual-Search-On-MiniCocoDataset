This repository shows how to execute reverse visual search on the MS COCO dataset.

In many domains we are interested in finding artifacts that are similar to a query artifact. In this assignment you are going to implement a system that can find artifacts when the queries are visual.

I will test the queries on the MS COCO dataset.

4.1. Dataset 
The images are from the MSCOCO mini dataset and will be of class person. I downloaded the data from the link provided in the assignment.

4.2. Pretrained Object Detection 

I have used the pretrained Faster RCNN model with ResNet-50 backbone to perform object detection on MS COCO dataset to extract the bounding box of all the people in the dataset. I have only kept the label 1 which is 'person' and the image list along with bounding box and probability. With this I have created the json file.

4.3. Reverse Image Search - Feature extraction 

After this, I iterate thorugh the dataframe that has all the person bounding boxes and then preprocess them similarly as the input to the pretrained Faster RCNN. Then I use the transfrom function along with the backbone function. I use the "pool" layer of the input to use the feature vector. 

4.4. Reverse Image Search - Similarity Search

For the final question, I have selected 5 bounding box as query. I iterate through the entire dataset and perform the cosine similarity search after using the pricinpal component analysis. Then I print the images and the bounding box information of the 10 similar bounding box and the 5 randomly chosen images.

