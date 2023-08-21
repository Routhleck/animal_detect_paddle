# animal_detect_paddle
[English](README.md) | [中文](README_CN.md)
 Animal recognition of twelve species based on the paddlepaddle framework.

Project's aistudio link: https://aistudio.baidu.com/aistudio/projectdetail/4214486?contributionType=1

### Project Introduction:

#### Project Approach:

(1) Create dataset annotation files

Annotations are made for the training set, validation set, and test set.

(2) Data preprocessing

Randomly crop the original images to a size of 224*224. There's a 50% chance of horizontal flipping for images in the training set.

(3) Data loading

Use paddle.io.DataLoader to load data into the paddlepaddle framework, setting parameters like batch_size, shuffle, and dropout.

(4) Neural network architecture

Constructed two classic CNNs: VGG16 and RepVGG.

(5) Evaluate trained models

Evaluate models trained using different neural networks and optimizers, calculating values such as accuracy, error rate, precision, and recall.

#### Final Results:

The final accuracy rate is 83.33%. Due to the use of the VGG16 network and a larger training set, resulting in multiple outputs, training was slow. Further improvements would require more time. The confusion matrix reveals interesting insights: mice and dragons have a lower recognition success rate. This could be due to variations in image styles within their respective training sets. Cows might be recognized as sheep, and horses might be identified as cows, given the similarity between these animals. Pigs and chickens have a higher recognition success rate, possibly because their shapes and colors differ significantly from other species.
