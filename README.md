# chest-cancer-classification 85% accuracy
In this [notebook](https://github.com/miraslavats/chest-cancer-classification/blob/2ad138418c328c4840bedef8c17f7cfb9db186b6/Chest_cancer_classification.ipynb), I am building several image classification deep learning models to identify the type of cancer given an image of a lung.

GOAL: build and train a model that accurately identifies whether the lung in the image is cancerous or not and what type of cancer it is.
My approach: I compared a shallow neural network with EffecientNetB0 feature extraction and fine tuning models. I also tested how the models perform with or without EarlyStopping, Batch Normalization, Dropout, Data Augmentation. Having tested all the models, I saw that the most effective one was the first model (EfficientNetB0 feature extraction) with early stopping, batch normalization & learning rate scheduler. The model had 85% accuracy on the test data. I am planning to come back to this notebook with more knowledge and achieve ~90% accuracy. 

RESULTS: The final model had ~85% accuracy on unseen data, meaning that it predicted whether an image contains a diseased lung or not and which type of cancer it has (if it has any) accurately in 85% of the cases. The model was built using EfficientNetB0 model as a base. To increase performance I used batch normalization and learning rate scheduler. To reduce overfitting I used EarlyStopping.

Notebook Outline:
1. Exploring the data:
   a. Manually looking through random images in the data set to understand the data;
2. Preprocessing the images:
   Converting the images into data;
3. Building a shallow CNN model
   TEST accuracy: 0.4095
   The model was also overfitting;
5. Feature extraction model:
   I used EfficientNetB0 as a base_model. This first feature extraction model did not have Dropout layers, Data augmentation or batch normalization.
   TEST accuracy: 0.7810
   a. Fine tuning the model:
   TEST accuracy: 0.8063
6. Adding Dropout layer to the first feature extraction model:
   TEST accuracy: 0.7968
   a. Fine tuning:
   TEST accuracy: 0.7397
7. Adding data augmentation to the first feature extraction model:
   TEST accuracy: 0.5937
   a. Fine tuning:
   TEST accuracy: 0.5714
8. Looking at all the results
   The first fine tuned model had the best performance, so I moved on with that model as a base.
9. Adding Batch Normalization and Learning rate scheduler to the best model
   TEST accuracy: 0.7746
   a. Fine tuning:
   TEST accuracy: 0.8508

You can find the code and all the in ["Chest_cancer_classification-2.ipynb"](https://github.com/miraslavats/chest-cancer-classification/blob/2ad138418c328c4840bedef8c17f7cfb9db186b6/Chest_cancer_classification.ipynb) file above.
