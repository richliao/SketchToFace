# SketchToFace
The original code for the project comes from [Christopher Hesse's pix2pix tensorflow implementation](https://github.com/affinelayer/pix2pix-tensorflow), which translates Phillip Isola's [Torch code](https://phillipi.github.io/pix2pix/) into tensorflow.  Chris has a very detailed explanation of the network in his [blog](http://affinelayer.com/pix2pix/). I have learned a quite deal reading it. 

For this excercise I have only made very little changes, primarily changed the Generative and Discriminator network to take in 64X64 images by removing two layers, so that the size of parameters and time to train the model can be reduced. The dataset I used comes from [CUHK Face Sketch database](http://mmlab.ie.cuhk.edu.hk/archive/facesketch.html). The original resolution of each image is 200X250. I have reduced each to 64X64 and further convert gray image to RBG by using openCV.

The dataset contains 188 faces and sketches combined. I have trained the model based on 185 data points, leaving following 3 for testing. As you can see results are quite impressive. The model has learned a very good mapping between sketches and faces.

<table>
<tr><th>name</th><th>input</th><th>output</th><th>target</th></tr>
<tr><td>f005</td><td><img src='images/f005-inputs.png'></td><td><img src='images/f005-outputs.png'></td><td><img src='images/f005-targets.png'></td></tr>
<tr><td>f006</td><td><img src='images/f006-inputs.png'></td><td><img src='images/f006-outputs.png'></td><td><img src='images/f006-targets.png'></td></tr>
<tr><td>f007</td><td><img src='images/f007-inputs.png'></td><td><img src='images/f007-outputs.png'></td><td><img src='images/f007-targets.png'></td></tr>
</table>

The following two additional test results are quite interesting. The test data comes from XM2GTS data set. I have manually downloaded two pairs of faces and sketches from the front page of CUHK face database. Since the model has only trained on data set based on CUHK students who are mainly Asian, the outputs also look asian, which are quite differen than the target images. However, if you look carefully, the generated images do resemble sketch faces very well.
<table>
<tr><th>name</th><th>input</th><th>output</th><th>target</th></tr>
<tr><td>Test1</td><td><img src='images/Test1-inputs.png'></td><td><img src='images/Test1-outputs.png'></td><td><img src='images/Test1-targets.png'></td></tr>
<tr><td>Test2</td><td><img src='images/Test2-inputs.png'></td><td><img src='images/Test2-outputs.png'></td><td><img src='images/Test2-targets.png'></td></tr>
</table>

For those interested in playing with the data, I have uploaded clean data in the sketches folder. You can follow the exact commands as written in the original author's blog.

#Conclusion and ideas
It will make sense to add another one hot label as input, such as Male vs. Female, ethnicity etc so that it can maximize the benefit of conditional adversarial network.

Also, the network only works when the input and target images are very well aligned. I initally were going after other data sources but that project failed miserably. The results of this dataset showed me what the capacity and limitation of the network are. After this, I plan to study further and see if I can come up with better discriminator network. If I have further work done, I'll update this page or you can go to my [blog](https://richliao.github.io/) for further information.
