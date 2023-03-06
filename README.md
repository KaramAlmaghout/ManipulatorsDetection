# ManipulatorsDetection
AML Course - Assignment 1


### Dataset Preperation 

A dataset of two classes of manipulators (Kuka and UR manipulators) is used to train a Faster RCNN model using Detectron 2 and YOLOv8

The dataset is is collected from images of the two manipulators from the robotic lab in Innopolis University, and some other images from Internet

![image](https://user-images.githubusercontent.com/94979970/222917841-488795ed-3610-44cf-a8f4-3324af9b66c1.png)

The images are annotated using Roboflow platform

After the annotation, the images are preprocessed to have the same size.

Then, some additional augmentation is applied on the image to generate additional image with different conditions (brightness and noise levels)

Finally, we got a 240 annotated images divided into train, validation, and test as it shown below:

![image](https://user-images.githubusercontent.com/94979970/222917590-44f101f9-9726-44c6-ab8b-6ab77d65c6df.png)

### Train FastRCNN model using Detectron2 on our Dataset

The generated dataset is exported in ***COCO Format***. A set of lines will be generated:

    !pip install roboflow

    from roboflow import Roboflow
    rf = Roboflow(api_key="***********")
    project = rf.workspace("*****").project("**************")
    dataset = project.version(*).download("coco")


[the project colab file for Faster RCNN](https://colab.research.google.com/drive/1xpR85LLGhhSeDygR-TSIvTaH9s_Ltxne?usp=sharing) 

### Train YOLOv8 model on our Dataset

The generated dataset is exported in ***COCO Format***. A set of lines will be generated:

    !pip install roboflow
    
    from roboflow import Roboflow
    rf = Roboflow(api_key="="***********")
    project = rf.workspace("amlcourse").project("***********")
    dataset = project.version(*).download("yolov8")


[the project colab file for YOLOv8](https://colab.research.google.com/github/KaramAlmaghout/ManipulatorsDetection/blob/main/AML_Assignment1_YOLOv8.ipynb)

