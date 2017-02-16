# SketchToFace

The project is based on [CUHK Face Sketch database](http://mmlab.ie.cuhk.edu.hk/archive/facesketch.html). There're total 188 faces and sketches combined. I have trained the model based on 185 data points, leaving following 3 for testing. As you can see the result is quite impressive. The model has learned a very good mapping between sketches and faces.

<table>
<tr><th>name</th><th>input</th><th>output</th><th>target</th></tr>
<tr><td>f005</td><td><img src='images/f005-inputs.png'></td><td><img src='images/f005-outputs.png'></td><td><img src='images/f005-targets.png'></td></tr>
<tr><td>f006</td><td><img src='images/f006-inputs.png'></td><td><img src='images/f006-outputs.png'></td><td><img src='images/f006-targets.png'></td></tr>
<tr><td>f007</td><td><img src='images/f007-inputs.png'></td><td><img src='images/f007-outputs.png'></td><td><img src='images/f007-targets.png'></td></tr>
</table>

The following two test results are quite interesting. The test data comes from XM2GTS data set. I have manually downloaded two pairs of faces and sketches. Since the model has only trained on data set based on Asian, the output also look asian, which are quite differen than the target images. However, if you look carefully, the generated images (output images) resemble sketch faces.
<table>
<tr><th>name</th><th>input</th><th>output</th><th>target</th></tr>
<tr><td>Test1</td><td><img src='images/Test1-inputs.png'></td><td><img src='images/Test1-outputs.png'></td><td><img src='images/Test1-targets.png'></td></tr>
<tr><td>Test2</td><td><img src='images/Test2-inputs.png'></td><td><img src='images/Test2-outputs.png'></td><td><img src='images/Test2-targets.png'></td></tr>
</table>
