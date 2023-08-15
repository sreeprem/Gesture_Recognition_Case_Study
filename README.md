# Gesture_Recognition_Case_Study

The challenge at hand involves the creation of an innovative feature for smart TVs produced by a home electronics company. This feature aims to empower users by allowing them to control the TV using hand gestures, eliminating the need for a remote control.

The gestures are captured by the TV's built-in webcam, which constantly monitors the user's movements. Each distinct gesture corresponds to a specific action:

Thumbs up: Amplifies the volume
Thumbs down: Decreases the volume
Left swipe: Skips back 10 seconds
Right swipe: Advances forward 10 seconds
Stop: Pauses the ongoing content
The dataset comprises several hundred videos categorized into five distinct classes. Each video, lasting between 2 to 3 seconds, is segmented into a sequence of 30 images or frames. These videos depict individuals executing the five gestures in front of a webcam, mimicking real-world usage.

The data is organized in a zip file containing 'train' and 'val' folders, each housing CSV files. These files carry essential information about the videos, including the subfolder name (containing the 30 images), the gesture's name, and a corresponding numeric label (ranging from 0 to 4).

For the analysis, two common neural network architectures are considered:

Standard CNN + RNN architecture: This involves extracting feature vectors for each image using Conv2D, then feeding these vectors into an RNN-based network. The RNN's output is fed to a softmax for classification.

3D convolutional network: In this setup, 3D convolutions are employed to process the video data as a sequence of 30 RGB images. The input is a 4D tensor representing the video, and the architecture takes advantage of the sequence and spatial information in the data.

The analysis leverages the Keras API with TensorFlow as the backend. Key steps include reading and preprocessing the image folders, which entails cropping, resizing, and standardizing the images. Data augmentation is applied if necessary to enhance training, and factors like batch size, epochs, image size, and the number of frames per video are optimized.

A custom generator function is crafted to efficiently handle data flow. Different models, including Conv2D+LSTM, Conv2D+GRU, and Conv3D, are evaluated. The conclusion from the analysis is that the Conv2D+LSTM model demonstrates promising performance. The proximity of these two accuracy values suggests that the model is well-trained without overfitting. Thus, the Conv2D+LSTM model is selected as the final choice for implementation, providing an effective solution for gesture recognition and control of the smart TV.

Contributers:
Sree P
