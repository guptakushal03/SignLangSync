# SignLangSunc - Webcam Image Classification for Sign Language Recognition

SignLangSunc is a web-based project for real-time sign language recognition using your webcam. It utilizes transfer learning with MobileNet and a K-Nearest Neighbors (KNN) classifier to identify custom sign language gestures. Users can add new signs, capture images to train the model, and make predictions using webcam input.

---

## Features

- **Webcam Input**: Capture real-time images from your webcam for training and classification.
- **Custom Sign Language Class Training**: Add new sign language classes (e.g., "Hello", "Thank you"), capture images, and store them in the model.
- **Transfer Learning with MobileNet**: Leverage MobileNet’s pre-trained model for feature extraction to classify signs.
- **KNN Classifier**: Classify captured images using a KNN classifier that is updated with new sign images.
- **Save and Load Model**: Persist the trained model by saving it into a JSON file and load it for later use.
- **Speech Feedback**: Hear the predicted sign language class spoken aloud using speech synthesis.

---

## Prerequisites

Before running SignLangSunc, ensure that you have the following dependencies:

- **TensorFlow.js**: For machine learning operations and tensor handling.
- **MobileNet**: A pre-trained model for feature extraction.
- **KNN Classifier**: Used to classify images based on the nearest neighbors.
- **Web Speech API**: For text-to-speech functionality.

Install the necessary libraries via npm:

```bash
npm install @tensorflow/tfjs @tensorflow-models/mobilenet @tensorflow-models/knn-classifier
```

---

## How It Works

1. **Webcam Input**:
   - Access your webcam using `navigator.mediaDevices.getUserMedia()` and display the live feed in an HTML element.

2. **MobileNet Model**:
   - The MobileNet model is loaded using `mobilenet.load()`, enabling feature extraction from captured images.

3. **KNN Classifier**:
   - Create a KNN classifier with `knnClassifier.create()`, which uses feature activations from MobileNet for classification.

4. **Add Custom Sign Language Classes**:
   - Users can add new classes (representing sign language gestures) by entering a class name and capturing images.
   - Each new image is added to the corresponding class in the KNN classifier.

5. **Train the Model**:
   - For each captured image, MobileNet generates a feature vector (activation), which is then added to the KNN classifier.

6. **Classify Signs**:
   - When the webcam feed is processed, the classifier predicts the most likely sign class from the current image.
   - The predicted class and confidence score are displayed in the UI.

7. **Model Persistence**:
   - Save the trained model into a JSON file using the "Save Model" button.
   - Load a previously saved model using the "Load Model" button to continue training or make predictions.

8. **Speech Output**:
   - The predicted sign language class can be announced aloud using the Web Speech API when the "Speak" button is clicked.

---

## Setup Instructions

1. Clone or download the repository to your local machine.
2. Open the `index.html` file in a modern browser (Chrome, Firefox, etc.) that supports Web APIs and TensorFlow.js.
3. The application will automatically request permission to access your webcam.

---

## User Interface

- **Input Class Name**: Enter the name of the new sign language class you want to create (e.g., "Hello", "Thank You").
- **Add Class**: Click this button to create a new class and start collecting images for it.
- **Training Cards**: Displays the added classes and their associated image counts.
- **Add New Images**: Capture new images for the selected class.
- **Predictions**: Displays the predicted sign language class for the current webcam frame.
- **Confidence**: Shows the classification confidence in percentage.
- **Save Model**: Save the current trained model to a JSON file.
- **Load Model**: Upload and load a previously saved model to continue training or use for classification.
- **Speak**: Hear the predicted class read aloud by clicking this button.

---

## Running the Application

1. Add a new class by typing a name (e.g., "Hello") and clicking **Add Class**.
2. Begin training the class by capturing images. Once you have enough images, start the classification process.
3. Use the **Start Classifying** button to begin predicting new sign gestures from the webcam.
4. Optionally, save your trained model using **Save Model** and load it again using **Load Model**.

---

## Important Notes

- **Performance**: The application runs in the browser, so performance may vary depending on the device and browser.
- **Compatibility**: Ensure your browser supports Web APIs like SpeechSynthesis, TensorFlow.js, and webcam access.
- **Webcam Permissions**: The app will prompt you to grant permission to access your webcam; please allow it for the app to function correctly.

---

## License

This project is open-source and available under the MIT License.

---

## Acknowledgements

- **TensorFlow.js**: For providing the machine learning framework in the browser.
- **MobileNet**: For the pre-trained feature extraction model.
- **KNN Classifier**: For easy classification of custom datasets.
