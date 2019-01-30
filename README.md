[dog_results_image]: ./images/dog_result_examples.png "Sample Output of Dog Breeds"
[human_results_image]: ./images/human_result_examples.png "Sample Output of Human Images"

# CNN Dog Breed Classifier

Convolutional Neural Network (CNN) designed and trained to detect dogs and predict their breed from user supplied images from a web app or mobile app. The application identifies the most probable dog breed from the image. If the image supplied is a human, it will identify the dog breed which most resembles the person. 

This project was completed as part of Udacity's Deep Learning Nanodegree program.

## Notebook Sections
1. Import Datasets
2. Detect Humans in Images - Using Pre-Trained OpenCV Haarcascades
3. Detect Dogs in Images - Using Pre-Trained VGG16 Model
4. Create a CNN to Classify Dog Breeds (From Scratch)
5. Create a CNN to Classify Dog Breeds (Using Transfer Learning)
6. Writing the Application Algorithm
7. Testing the Application

# Results

Model created using transfer learning from a pre-trained VGG16 network significantly outperformed my model made from scratch when tested against the test set.

## Model Test Accuracies
- Created From Scratch: 12%
- Created with Transfer Learning: 73%

## Dog Breed Classification:
When providing the model with images of dogs, it reasonably predicts the dog breed. When encountering an ambiguous breed or a breed which has similar features to another it often alternates between the two predictions. This can be seen in the far right image of a Jack Russel Terrier - the network will alternate between a Saint Bernard (similar color patterns) and the correct Jack russel breed.

![Sample Dogs][dog_results_image]

## Human-Dog Breed Classification:
In the cases where the user supplies a picture of a human, the model will detect that the image is a human and the closest resembling breed. Pre-trained OpenCV face detector Haarcascades is leveraged to detect when the image is of a human. 

It is important to note that the training methodology did not provide the model an clues on how to best match dog patterns to human patterns, the application is simply relying on its ability to detect dog breed patterns - but in this case applies it directly to humans. This provides some interesting results.. and sometimes it doesn't recognize a human wearing glasses.. or does it actually know better in this case..

![Sample Humans][human_results_image]