# Exoplanet Habitability Prediction with Recurrent Neural Networks and K-Nearest Neighbors
This repository contains a deep learning project focused on predicting the habitability of exoplanets based on their temperature. The project utilizes Recurrent Neural Networks (RNN) with Long Short-Term Memory (LSTM) units to model the sequential nature of the data. Additionally, the K-Nearest Neighbors (K-NN) algorithm is employed to find exoplanets with similar characteristics.

## Dataset
[https://www.kaggle.com/datasets/diaaessam/exoplanets-planets-outside-our-galaxy](https://www.kaggle.com/datasets/diaaessam/exoplanets-planets-outside-our-galaxy)

## Model Description
The model is built using the Keras library with the following architecture:
- Input Layer: Accepts the reshaped training data.
- LSTM Layer: 50 units with return sequences set to True, regularized with L2 regularization.
- Dropout Layer: 20% dropout rate to prevent overfitting.
- LSTM Layer: Another 50 units with L2 regularization.
- Dropout Layer: Another 20% dropout rate.
- Dense Layer: Output layer with a single unit and L2 regularization.

The model is compiled with the Adam optimizer and mean squared error loss function.

## Training Process
The model is trained using the following approach:
- Early Stopping: Monitors the validation loss and stops training when it stops improving, with a patience of 10 epochs.
- Validation Split: 10% of the training data is used as a validation set.
- Batch Size: 32 samples per batch.
- Epochs: Up to 100 epochs, but may stop early due to early stopping.

## Evaluation
The model’s performance is evaluated using K-Fold Cross-Validation with 5 splits. The results are as follows:
- Cross-Validation Scores: The negative mean squared error scores for each fold.
- Average MSE: The average mean squared error across all folds.
- Standard Deviation: The standard deviation of the mean squared error scores.

Additionally, the model’s predictions are compared against the actual values to calculate the Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

## Prediction and Analysis
The model can predict the temperature of an exoplanet given its features. It also classifies the habitability based on the predicted temperature, assuming that habitable temperatures are between 0°C and 100°C.

To find exoplanets with similar characteristics, the K-NN algorithm is used. Given the features of an exoplanet, the model can find the nearest neighbors in the dataset and list exoplanets with similar properties.

## Visualization
The repository includes code to plot the training and validation loss values over epochs, providing a visual representation of the model’s learning process. Additionally, a scatter plot compares the actual versus predicted temperatures, illustrating the model’s prediction accuracy.

<img src="https://github.com/user-attachments/assets/9e49cffa-dd33-445f-afd0-cf82a7f4f148" width="500" alt="Actual vs Predicted Temperature" />
<img src="https://github.com/user-attachments/assets/c2ab437d-bda9-46ab-b2f0-225e038a4816" width="500" alt="Loss" />

## Saving and Loading
The trained model, along with the minimum and maximum values of each feature, is saved to CSV files. This allows for easy loading and reuse of the model for future predictions.

## Conclusion
This project demonstrates the application of deep learning techniques to the field of astronomy, specifically in predicting the habitability of exoplanets. The combination of RNN with LSTM and K-NN provides a robust approach to modeling and analyzing exoplanetary data.

Please note that the above README is a template and should be customized to fit the specifics of your project and repository structure. If you have any additional sections or information you would like to include, feel free to modify the README accordingly. 😊
