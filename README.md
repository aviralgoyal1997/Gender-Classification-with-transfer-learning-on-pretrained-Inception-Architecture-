# Gender-Classification-with-transfer-learning-on-pretrained-Inception-Architecture-
Using transfer learning on pretrained  googlenet inception architecture and making our own image classifiers.We will be making gender classifier.
You know that idea of simplicity in network architecture that we just talked about? Well, Google kind of threw that out the window with the introduction of the Inception module. GoogLeNet is a 22 layer CNN and was the winner of ILSVRC 2014 with a top 5 error rate of 6.7%. To my knowledge, this was one of the first CNN architectures that really strayed from the general approach of simply stacking conv and pooling layers on top of each other in a sequential structure. The authors of the paper also emphasized that this new model places notable consideration on memory and power usage (Important note that I sometimes forget too: Stacking all of these layers and adding huge numbers of filters has a computational and memory cost, as well as an increased chance of overfitting).


<p align="center">
  <img src="https://adeshpande3.github.io/assets/GoogLeNet.png" width="700"/>
  
</p>
This box is called an Inception module. Let’s take a closer look at what it’s made of
p align="center">
  <img src="https://adeshpande3.github.io/assets/GoogLeNet3.png" width="700"/>
  
</p>
Main Points

 Used 9 Inception modules in the whole architecture, with over 100 layers in total! Now that is deep…  
 No use of fully connected layers! They use an average pool instead, to go from a 7x7x1024 volume to a                          1x1x1024 volume. This saves      a huge number of parameters.
 Uses 12x fewer parameters than AlexNet.
 During testing, multiple crops of the same image were created, fed into the network, and the softmax probabilities were averaged  to give us the final solution.
There are updated versions to the Inception module (Versions 6 and 7).
Trained on “a few high-end GPUs within a week”.
   <h1>Starting to make classifier</h1>
   Hey,I am going to tell you how to make an accurate gender classifier and good thing about this is once you learn how to make this you can use this for classification of any thing not only genders but we will talk for genders now:

1.As all of you know first we need good data so for that,clone or download –

https://github.com/StephenMilborrow/muct

and extract all image files in one folder and now you will see 15 images of a single person (at 3 diff angles by 5 cams) now we need to separate male images and female images so for that we can just search for ‘m’ character and it will separate out male images,then copy them into a folder ‘males’ and similarly female images into a folder ‘female’.

2. Now we need to download Inception Architecture in our machine so for that clone this repo –  https://github.com/tensorflow/models

and then in models folder go to

models/tutorials/image/imagenet

and open terminal and run

python classify_image.py

This downloads the trained model from tensorflow when the program is run for the first time.

And congrats now u have made a classifier which can classify among these 1000_classes

you can classify any image by running:

    >python classify_image.py --image image_directory

And u will get 5 possible results with prediction scores.

3. Now we need to perform transfer learning which is basically using same trained model but now we will train last layer of this architecture for our gender data.

Make a folder genderrecog on ur desktop and then in that make a folder genders and in that copy males and females folder u made in first step.In genderrecog folder copy

label_image    and   retrain in .py format,then open terminal there and run
</p>
This box is called an Inception module. Let’s take a closer look at what it’s made of
<p align="center">
  <img src="https://datasciencebasicsblog.files.wordpress.com/2017/12/a.png" width="600"/>
  
</p>
now this will take about 1.30 hr if u don’t have gpu in ur machine like me else 30 minutes approx.

4. To classify any image :
</p>
This box is called an Inception module. Let’s take a closer look at what it’s made of
<p align="center">
  <img src="https://datasciencebasicsblog.files.wordpress.com/2017/12/b.png" width="600"/>
  
</p>
*subdirectories in genders folder are used as classes so for diff classification use data of that category and make folder on basis of that.

Reference:

<a href='https://www.tensorflow.org/tutorials/image_recognition'>https://www.tensorflow.org/tutorials/image_recognition</a>

