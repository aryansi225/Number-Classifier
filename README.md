# Number-Classifier
Model classifies image of digits trained on MNIST image data

The python notebook contains the implementation of a convolutional neural network which is trained MNIST hand written digit data set to classify hand written when given new input.

Following steps were taken to implement the solution :
1. Grayscale normalization to make the cell value to [0..1] from [0..255]. CNN converge faster on [0..1]
2. Each test and train data is converted to a 28x28 matrix.
3. One hot encoding is done to create category for digits 0 through 9.
4. Created a CNN model of following configuration
    In -> [[Conv2D->relu]*2 -> MaxPool2D -> Dropout]*2 -> Flatten -> Dense -> Dropout -> Out
    In first go the Conv2D layer the filers are 32 and kernel size is (5,5) and relu as activation function.
    In second go the Conv2D layer the filers are 64 and kernel size is (3,3) and relu as activation function.
    The poolsize for MaxPool2D layer for both sets is (2,2) and dropout is 0.25.
    Then flatten layer is applied, followed by Dense layer of 256 with activation function relu.
    Then agin a droupout layer of 0.25 is applied followed, by finally a Dense layer of 10 with activation function softmax.
5. Since the dataset provided is too small, data augmentation id performed where the data is zoomed, rotated, shifted horizontally and shifted vertically.
6. Finally model is trained using train data and augmented data.
7. A confusion matrix is created to check how good the model predicted.
8. Finally the value for test data is performed.

# Screenshot

Kaggle Submission shows 97.128% accuracy. The accuracy could have improved if model was allowed to run for more epochs (Currently model is trained with 1 epoch)

![image](https://user-images.githubusercontent.com/16362957/54154199-5af77d80-4467-11e9-9066-da02c98f005d.png)

Leaderboard Ranking

![image](https://user-images.githubusercontent.com/16362957/54154231-6f3b7a80-4467-11e9-82d0-283d4e9ab2b9.png)

Confusion Matrix of model's prediction

![image](https://user-images.githubusercontent.com/16362957/54154306-9eea8280-4467-11e9-9fc2-06ca0d08f8ac.png)

Some examples where model predicted wrongly

![image](https://user-images.githubusercontent.com/16362957/54154355-bd507e00-4467-11e9-967e-6516c64ce6aa.png)

# Credit
Great kernel -> Good explanation and fantastic piece of coding https://www.kaggle.com/yassineghouzam/introduction-to-cnn-keras-0-997-top-6
