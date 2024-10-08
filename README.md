# Image Classification using Convolutional Neural Network
The aim in this ![project](https://github.com/MuhamadSyarifFakhrezi/FaceMaskDetection/blob/master/image_classification_deployment.ipynb) is to classify the images of people wearing masks and not wearing masks using Convolutional Neural Network(CNN).

## The workflow in this project is as below:
### Understanding and Pre-processing Data
Before we can start to predict, we first need to understand the dataset we are going to use. The next step is to process the data so that it can be used to train the model, some of the data processing performed is as follows:
- Read images from dataset.
- Resize images to the same size to make the model predictions are more accurate.
- Separate the data into train_data and validation_data.
- Data augmentation to expand the training data by creating variations in the image.

### Create the Model
The model consists of four convolution blocks with max pool layer in each of them, activated by 'ReLU' activation function and 'Sigmoid' activation function in the output layer.
And then in the process of compiling the model we use 'Adam' optimizer and 'Binary Crossentropy' for the loss function.

### Train the Model
The training process is run for 10 epochs and the model is regenerated with batch data generated by the generator. The model is evaluated using validation data, the results of model learning at each epoch are monitored using callbacks to ensure model optimization, and the process of each epoch is displayed to show the time taken to train the model.

**RESULTS**

Results after training 9,433 images:
* number of epochs = 10
* training data / validation data split = 80/20
* MODEL:
    - CONV 3x3 filter layers with MaxPooling 2x2 - 32 x 64 x 128 x 512
    - Dense layers - 128 x 1
    - loss: 0.1415
    - accuracy: 0.9521
    - val_loss: 0.1006
    - val_accuracy: 0.9691

**The performance of the model was very good and was able to predict the image with 96% accuracy.**

Plots for model accuracy and loss are following:

![accuracy](https://github.com/user-attachments/assets/39f78b3b-8bdc-498f-9db3-419d47ee2dd4)
![loss](https://github.com/user-attachments/assets/d3a89b0c-2edd-49ea-9d48-cc2b9a293732)

### Try to Predict the Image
The model was tested using images beyond the training and validation data

![predict](https://github.com/user-attachments/assets/35678e9e-b4a0-41c3-a664-23059385d546)

### Save the Model
This model was saved in tflite form for ![deployment](https://github.com/MuhamadSyarifFakhrezi/FaceMaskDetection/tree/master/deploy) on a simple Android app with the Kotlin programming language.
