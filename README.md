# PennAppsXX
## View Our Devpost Here: https://devpost.com/software/don-t-be-fake
Other articles here: https://penntoday.upenn.edu/news/deepfake-detector-wins-pennapps-xx
## Table of Contents

1. [Inspiration](#inspiration)
2. [What It Does](#what-it-does)
3. [How We Built It](#how-we-built-it)
4. [Challenges We Ran Into](#challenges-we-ran-into)
5. [Accomplishments We Are Proud Of](#accomplishments-we-are-proud-of)
6. [What We Learned](#what-we-learned)
7. [What Is Next For DeFake](#what-is-next-for-defake)
8. [Technologies Used](#technologies-used)


## Inspiration
The upcoming election season is predicted to be drowned out by mass influx of fake news. Deepfakes are a new method to impersonate famous figures saying fictional things, and could be particularly influential in the outcome of this and future elections. With international misinformation becoming more common, we wanted to develop a level of protection and reality for users. Facebook's Deepfake Detection Challenge, which aims to crowdsource ideas, inspired us to approach this issue.

## What It Does
Our Chrome extension processes the current video the user is watching. The video is first scanned using AWS to identify the politician/celebrity in subject. Knowing the public figure allows the app to choose the model trained by machine learning to identify Deepfakes targeting that specific celebrity. The result of the deep fake analysis are then shown to the user through the chrome extension, allowing the user to see in the moment whether a video might be authentic or forged.

Our Web app offers the same service, and includes a prompt that describes this issue to users. Users are able to upload a link to any video they are concerned may be tampered with, and receive a result regarding the authenticity of the video.

## How We Built It
We used the PCA (Principal Component Analysis) to build the model by hand, and broke down the video into one second frames.

Previous research has evaluated the mouths of the deepfake videos, and noticed that these are altered, as are the general facial movements of a person. For example, previous algorithms have looked at mannerisms of politicians and detected when these mannerisms differed in a deepfake video. However, this is computationally a very costly process, and current methods are only utilized in a research settings.

Each frame is then analyzed with six different concavity values that train the model. Testing data is then used to try the model, which was trained in a Linear Kernel (Support Vector Machine). The Chrome extension is done in JS and HTML, and the other algorithms are in Python.

The testing data set is comprised from the user's current browser video, and the training set is composed of Google Images of the celebrity.

## Challenges We Ran Into
Finding a dataset of DeepFakes large enough to train our model was difficult. We ended up splitting the frames into 70% dataset, and 30% of it is used for testing (all frames are different however). Automatically exporting data from JavaScript to Python was also difficult, as JavaScript can not write on external files.

Therefore, we utilized a server and were able to successfully coordinate the machine learning with our web application and Chrome extension!

## Accomplishments We Are Proud Of
We are proud to have created our own model and make the ML algorithm work! It was very satisfying to see the PCA clusters, and graph the values into groups within the Support Vector Machine. Furthermore, getting each of the components ie, Flask and Chrome extension to work was gratifying, as we had little prior experience in regards to transferring data between applications.

We are able to successfully determine if a video is a deep fake, and notify the person in real time if they may be viewing tampered content!

## What We Learned
We learned how to use AWS and configure the credentials, and SDK's to work. We also learned how to configure and utilize our own machine learning algorithm, and about the dlib/OpenCV python Libraries!

Furthermore, we understood the importance of the misinformation issue, and how it is possible to utilize a conjuction of a machine learning model with an effective user interface to appeal to and attract internet users of all ages and demographics.

## What Is Next For DeFake
Train the model with more celebrities and get the chrome extension to output whether the videos in your feed are DeepFakes or not as you scroll. Specifically, this would be done by decreasing the run time of the machine learning algorithm in the background. Although the algorithm is not as computationally costly as conventional algorithms created by experts, the run time barrs exact real-time feedback within seconds.

We would also like to use the Facebooks DeepFake datasets when they are released. Specifically, deepfakes are more likely to become a potent tool of cyber-stalking and bullying in the short term, says Henry Ajder, an analyst at Deeptrace. We hope to utilize larger data bases of more diverse deepfakes outside of celebrity images to also prevent this future threat.

## Technologies Used
* ajax
* amazon-web-services
* computer-vision
* css
* flask
* html
* javascript
* machine-learning
* node.js
* open-cv
* principle-component-analysis
* python
* support-vector-machine
Try it out!
