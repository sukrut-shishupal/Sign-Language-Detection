# Sign-Language-Detection


# Problem:
It has been difficult for people who are visually impaired or deaf to communicate with others, and it is complex to understand sign language as it is not something familiar to all. This ultimately leads to communication barriers.

There have been several advancements in technology, and much research has been done to help people who are visually impaired and deaf. Sign Language Detection is a helpful tool for them to convey the meaning of sentences instead of words. It is a fully-fledged natural language with its grammar and lexicons. Using this, we can easily communicate with people who use sign language.

There are two prominent sign language recognition approaches image-based and sensor-based. Much research is going on the image-based approach only because of the advantage of not needing to wear complex devices like hand gloves, helmets, etc., like the sensor-based approach.

Since deep learning has a robust feature extraction ability and high accuracy, we choose to use it to solve this problem. Here, deep learning techniques are used to train the dataset based on sign language and train a model which predicts the meaning of the sign language. We use convolutional neural networks as our model to recognize the alphabet.


# Data Set:
The primary dataset we are using is the MNIST dataset for this project. This dataset consists of 24 American Sign Language alphabets (excluding J and Z), which will be used to train the data. Each image has 28X28 pixels which come to a total of 784 pixels per image. There are 27,455 cases in the dataset, which should be sufficient to train the model.

Each letter indicates a sign produced by our fingers. We will apply deep learning to these images to ensure the model understands what sign indicates what letter. Once the model is trained, we will test it using a laptop camera and show sign language to check its performance.

![image](https://user-images.githubusercontent.com/37614346/209702083-e2424b96-be85-43dc-94a0-1f85c1e08c81.png)

In this project, we used a couple of Conv2D and MaxPooling layers, followed by some fully connected dense layers. The first Conv2D layer takes an input image of shape (28,28,1), and the last fully connected layer gives us output for 26 alphabets. We also used Dropout after the 3rd  Conv2D layer to regularize training. 


# Result:
We have to create a window to take the input from our webcamera. The image we are taking as input should be a 28X28 grayscale image since we trained our model on a 28X28 size image. To create this window, we used the OpenCV and NumPy library to modify the image to have the same characteristics as the images the model was trained on. 

While thinking about this part, we came across an idea to create a bounding box, as it will allow the model to focus directly on the portion of the image needed for the function (the hand). The model might correlate the feature to some random thing in the background if we do not do that. This might reduce the accuracy of the model. 

![image](https://user-images.githubusercontent.com/37614346/209703034-8a1eeeb8-5ac6-4be6-825b-4cb6f70f9d23.png)

We used a for loop to go through the dictionary to match the highest values to their corresponding keys and print the output with the probability. Using list comprehension to sort values from highest to lowest, we take the first few items in the list and designate them three characters that closest correspond to the sign language image shown. 

# 1:
![image](https://user-images.githubusercontent.com/37614346/209703117-b9dce574-a2d0-4fae-a9ee-0fd097dd0ea6.png)

# 2:
![image](https://user-images.githubusercontent.com/37614346/209703360-c71ae544-2d44-466e-8053-f901cf3d403f.png)

The model accurately predicted the characters in the camera, along with the confidence of classification from the CNN model. 


# Conculsion:
We created a model that can be used in many sectors, such as video calls and android applications, to teach people sign language or try to understand the word the mute person is saying. It can also be used as a fun gaming exercise to create a language between two people so that no one can understand it. 

Overall, there are many applications, but an application developed on this model must have a frame-by-frame running detection to capture everything the person is saying. It can also string the letters together to get a word or a sentence and eventually recognize the complete word. There will be no communication barrier if this is developed into a device. 

We got a high accuracy on the test model, which helped us predict the ASL. In addition, we explored the use of CNN and how it can help remove barriers. It was interesting to understand the problem, analyze the dataset and develop a model that can benefit people. 
