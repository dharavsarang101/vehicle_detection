### Car Detection from Images Using Deep Neural Networks

**Dharav Sarang**

#### Executive summary
This project aims to build a deep learning model that can classify whether a given image contains a car or no car. Using convolutional neural networks (CNNs), the model is trained on real-world datasets consisting of cars, pets, and plain roads, preparing it for diverse and practical use cases such as smart home security cameras and doorbells.


#### Rationale
With the rise of smart security devices like video doorbells and AI cameras, the ability to accurately detect specific objects (like humans, cars, and pets) has become crucial.
Currently, most devices mainly detect humans, but identifying vehicles is increasingly important for monitoring motion activity at driveways, parking lots, and street activity.

Expanding object detection to vehicles can help:
	1. Reduce false alarms
	2. Improve homeowner awareness
	3. Enable better logging of non-human activity on private properties
Thus, building a reliable car detection model addresses a real-world market need.

#### Research Question
Can a deep convolutional neural network (CNN) reliably classify whether an image contains a vehicle (car) or no vehicle across varied real-world lighting conditions, backgrounds?

#### Data Sources
**Vehicle Images**
  - Stanford Cars Dataset on Kaggle - https://www.kaggle.com/datasets/jutrera/stanford-car-dataset-by-classes-folder

**Non-Car Images**
  - Oxford-IIIT Pet Dataset on Kaggle - https://www.kaggle.com/datasets/tanlikesmath/the-oxfordiiit-pet-dataset (Pets dataset to simulate non-vehicle objects)
  - Pothole and Plain Road Images on Kaggle - https://www.kaggle.com/datasets/virenbr11/pothole-and-plain-rode-images (Empty roads dataset)

**Testing Dataset**
  - Vehicle Detection GitHub Dataset - https://github.com/MaryamBoneh/Vehicle-Detection/tree/main  (Real-world vehicle images)

#### Methodology

**Dataset Labeling**
 1. Organize images into two classes:
   - Images containing cars
   - Images with no vehicles (Plain roads, pets, random backgrounds)
 2. Create a corresponding **text label file** for each image:
   - `'Vehicle Detected'` for images containing a car
   - `'Vehicle Not Detected'` for images without a car

**Preprocessing**
- Resize all images to (128x128)
- Normalize pixel values between 0 and 1

**Model Architecture**
- Custom 2D CNN model with three convolutional layers
- Activation functions: ReLU (hidden layers) and Sigmoid (output layer)
- BatchNormalization and Dropout for regularization
- Loss function: Binary Cross-Entropy
- Optimizer: RMSprop with a small learning rate

**Training Strategy**
- Split dataset using train_test_split
- Use Data Augmentation to simulate real-world variability
- Monitor training and validation accuracy and loss

#### Results
**Metric Achieved Value**
Final Training Accuracy	~97%
Final Validation Accuracy ~89%

The model successfully learned to distinguish images with and without cars across different lighting and background conditions.

Correctly identifies clean car images, cars on streets, and partial car visibility.
Correctly rejects empty roads and pet images as "No Vehicle Detected."

#### Next steps
Expand dataset: Gather more nighttime and rainy-day images to improve low-light robustness.
Fine-tune brightness augmentation: Introduce controlled brightness variation during training.
Explore Transfer Learning: Apply VGG16, MobileNetV2 to further boost accuracy with smaller datasets.
Deploy to lightweight edge devices: Optimize model for real-time inference on Raspberry Pi, low memory SoC
Expand Object Categories: Extend the classifier to handle multiple objects (Car, Truck, Motorcycle, Bicycle, Pet, Empty Road).

#### Outline of project

├── project-vehicle-detection
│    ├── README.md
│    ├── vehicle_detection.ipynb 
|    ├── images
        ├──train
        ├──train_labels
        ├──test
        ├──test_labels

##### Contact and Further Information

Author: Dharav Sarang
Email: dharavsarang101@gmail.com

