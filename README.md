# Male-vs-Female-Eyes-Image-Classification
Male vs Female Eyes image classification
Project using Google colab

* Dataset is provided by Kaggle uploaded by PavelBiz
* Link to File : https://www.kaggle.com/pavelbiz/eyes-rtte/
* The dataset can be fetch using kaggle library on colab 
* 11.525 samples
* 80:20 train test split

## Library Used
* Tensorflow
* Keras
* matplotlib
* Numpy
* Pandas
* Kaggle

|    |    type   |   maleeyes |   femaleeyes |      total |
|---:|:----------|-----------:|-------------:|-----------:|
|  0 | original  |       6323 |         5202 |       11525| 
|  1 | train     |       5058 |         4161 |       9219 |  
|  2 | val       |       1265 |         1041 |       2306 |  

### Display random images to examine
![](/img/download.png)

### Rescaling Image
### Image Augmenting (train set only)
* Rotation
* Horizontal flip
* Zoom range
* Shear
* Fill mode nearest
* Data generating
* resizing image to 60x60
* batch size 64
* class mode binary
* 
### Build Convnet
* 1 hidden layer (perceptron 128 units)
* output layer 'Softmax'
* model = keras.Sequential([
*    layers.Conv2D(32, (3,3), activation = 'relu', input_shape= (60,60,3)),
*    layers.MaxPooling2D(pool_size=(2, 2)),
*    layers.Conv2D(64,(3,3), activation= 'relu'),
*    layers.MaxPooling2D(pool_size=(2, 2)),
*    layers.Conv2D(128,(3,3), activation= 'relu'),
*    layers.MaxPooling2D(pool_size=(2, 2)),
*    layers.Flatten(),
*    layers.Dropout(0.5),
*    layers.Dense(128, activation= 'relu'),
*    layers.Dense(1, activation= 'sigmoid')
* ])

### Adding Loss Function and Optimizer
* loss : binary crossentropy
* optimizer adam
* metrics binary accuracy

### Adding early stop using tensor earlystop
* 5 epoch berfore stop
* 0.01 increase per epoch to be considered an improvement

### Training the model
* epoch : 40
* steps per epoch : 20
* verbose : 1
* validation steps : 10
* callbacks
 
## Results
* Best Validation Loss: 0.27
* Best Validation Accuracy: 0.93

* Loss

![](/img/loss.png)

* Accuracy

![](/img/accuracy.png)



