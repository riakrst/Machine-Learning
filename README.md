# Machine-Learning

### Model Architecture
In this project, we utilize a pre-trained MobileNet model, which is a CNN model trained using large datasets such as ImageNet, for food classification. This means the model has already learned strong visual features from previous training on various types of images. By leveraging these pre-trained weights, we can apply the model to various image processing tasks without needing to train it from scratch, saving time and computational resources.
1. Loading the Pre-trained MobileNet Model
   First, we loaded the pre-trained MobileNet model with ImageNet weights, which provide a good initial set of learned features for our food classification task. 
2. Freezing the Base Layer
   To ensure that the pre-trained MobileNet model remains unchanged during training, we have frozen all of its layers. This approach guarantees that only the newly introduced classification layers undergo training.
3. Adding Custom Classification Layers
   We built the model using the Functional API. First, we added the base MobileNet model, followed by a GlobalAveragePooling2D layer to average the feature maps into a 1D vector. Then, a Dropout layer with a rate of 0.5 was applied to reduce overfitting. We added a Dense layer with 512 units and ReLU activation to capture more complex patterns, followed by another Dropout for further stability. Finally, a Dense layer with units matching the number of predicted classes (num_classes) and softmax activation was added as the output layer, complete with L2 regularization to reduce overfitting.
