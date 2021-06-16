# Vehicle Detection
This repository contains a deep learning model I have trained for vehicle detection. You can find information about the model and training data in the following sections.

## How to use it
You can quickly try the trained model by going to this [**Google Colab**](https://colab.research.google.com/drive/1is86PqKsPYFdP4VmhGMb4mwp9Enp51mM?usp=sharing), then click **Run cell** (Ctrl-Enter), upload your vehicle image and click **Detect vehicles**.  

***\*\*If you run this colab for the first time, it may take about 55s to install the Tensorflow Object Detection API, so please be patient!\*\****   

![Demo using the vehicle detector on Colab](/resources/demo.gif "Hope you enjoy it!") 

If you want to see the code cell of the colab, double-click the first line that says **Click "Run cell" (Ctrl-Enter) to start**. The code is quite self-explanatory. 

If you want to use the model in your project, first install the Tensorflow Object Detection API (see, for example, [instruction here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2.md)), then download my trained model [here](https://drive.google.com/file/d/1RQsPHiWtWTbFM5n4ofg3p9F3FdHbmO6e/view?usp=sharing). You may also want to have a look at my colab and use some parts of it to quickly build your detection function.

## About the model and training data 
I have followed this [tutorial](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/index.html) to train the model. In short, the model was trained using transfer learning technique. I have chosen the *SSD MobileNet V2 FPNLite 640x640* pre-trained on the COCO 2017 dataset (provided in the [TensorFlow 2 Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md)) as its base model. You can try using other base models that suits your needs (e.g., speed, accuracy). 

The training data includes about 11.000 HD images (1280×720px) extracted from traffic monitoring cameras in Vietnam. The data were provided by this AI contest hold in 2020: http://ai.icti-hcm.gov.vn/. I have cleaned up the data a little bit, such as removing images without labeled objects, correcting labels in some xml files, shuffling and splitting the data into training and test set (1276 images in the test set).

**NOTE:** Due to the lack of resources, I have trained this model with a relatively small batch-size of 8 for a not-so-long training time (I can't remember how many epochs I have trained the model since it has been months ago. I have a short memory. Sorry!). I have also tried other base models, such as the ssd_resnet50_v1 and efficientdet_d1_coco17 (both from the TensorFlow 2 Detection Model Zoo) but they took so long on my computer hence I gave up. I believe that if you could train the model with a larger batch-size and/or for more epochs you can achieve ***better models***. I would appreciate it if you share your model. Please feel free to drop me an email at [quangtn@hcmute.edu.vn](mailto:quangtn@hcmute.edu.vn)
