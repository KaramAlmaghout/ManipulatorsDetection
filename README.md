# ManipulatorsDetection
AML Course - Assignment 1


## Dataset Preperation 

A dataset of two classes of manipulators (Kuka and UR manipulators) is used to train a Faster RCNN model using Detectron 2 and YOLOv8

The dataset is is collected from images of the two manipulators from the robotic lab in Innopolis University, and some other images from Internet

![image](https://user-images.githubusercontent.com/94979970/222917841-488795ed-3610-44cf-a8f4-3324af9b66c1.png)

The images are annotated using Roboflow platform

After the annotation, the images are preprocessed to have the same size.

Then, some additional augmentation is applied on the image to generate additional image with different conditions (brightness and noise levels)

Finally, we got a 240 annotated images divided into train, validation, and test as it shown below:

![image](https://user-images.githubusercontent.com/94979970/222917590-44f101f9-9726-44c6-ab8b-6ab77d65c6df.png)

[Link to the annotated dataset](https://universe.roboflow.com/amlcourse/manipulators-detection/dataset/4)

## Train FastRCNN model using Detectron2 on our Dataset

The generated dataset is exported in ***COCO Format***. A set of lines will be generated:

    !pip install roboflow

    from roboflow import Roboflow
    rf = Roboflow(api_key="***********")
    project = rf.workspace("*****").project("**************")
    dataset = project.version(*).download("coco")


[the project colab file for Faster RCNN](https://colab.research.google.com/github/KaramAlmaghout/ManipulatorsDetection/blob/main/AML_Assignment1_FasterRCNN.ipynb) 


### Results

![image](https://user-images.githubusercontent.com/94979970/223220273-e55ecb31-99ad-42fd-a61c-11f731eb4b2e.png)
![image](https://user-images.githubusercontent.com/94979970/223220319-8dd7951c-d251-48e7-ad3d-c8274ce82977.png)
![image](https://user-images.githubusercontent.com/94979970/223220339-1e0e4358-4f6f-48ae-987d-a3a68dc0c922.png)
![image](https://user-images.githubusercontent.com/94979970/223220390-373d1cd3-9ab8-4061-95b7-1485d37ee880.png)



![image](https://user-images.githubusercontent.com/94979970/223219896-6ac2c07d-dfb1-4ea7-bd34-5daa537f0753.png)






## Train YOLOv8 model on our Dataset

The generated dataset is exported in ***COCO Format***. A set of lines will be generated:

    !pip install roboflow
    
    from roboflow import Roboflow
    rf = Roboflow(api_key="="***********")
    project = rf.workspace("amlcourse").project("***********")
    dataset = project.version(*).download("yolov8")


[the project colab file for YOLOv8](https://colab.research.google.com/github/KaramAlmaghout/ManipulatorsDetection/blob/main/AML_Assignment1_YOLOv8.ipynb)

### Results

![image](https://user-images.githubusercontent.com/94979970/223213170-93043072-6e5e-491e-9c6a-b580a8e72ea4.png)

![image](https://user-images.githubusercontent.com/94979970/223213206-9050237a-7b0b-4124-bd05-87081a047b12.png)

![image](https://user-images.githubusercontent.com/94979970/223213302-73d32b30-0d1d-40e3-9a1d-fa5bc92ceced.png)

