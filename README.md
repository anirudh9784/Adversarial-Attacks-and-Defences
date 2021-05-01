# Major Project

<h3> Title : An integrated Auto Encoder-Block Switching defense approach to prevent adversarial attacks </h3>
<p align="justify"> According to the recent studies, the vulnerability of state of the art Neural Networks to adversarial input samples has increased drastically. Neural network
is an intermediate path or technique by which a computer learns to perform tasks using Machine learning algorithms. Machine Learning and Artificial Intelligence model has become
fundamental aspect of life, such as self-driving cars, smart home devices, so any vulnerability is a significant concern. The smallest input deviations can fool these extremely
literal systems and deceive their users as well as administrator into precarious situations. This article proposes a defense algorithm which utilizes the combination of an auto-
encoder and block-switching architecture. Auto-coder is intended to remove any perturbations found in input images whereas block switching method is used to make it more robust
against White-box attack. Attack is planned using FGSM model, and the subsequent counter-attack by the proposed architecture will take place thereby demonstrating the feasibility
and security delivered by the algorithm.</p>

<h2>Dataset :</h2><pre>It is subset of Imagenet Dataset
Source : <a href="https://imagenet.stanford.edu/" >ImageNet </a>
<img src="Dataset/1.jpg"  style="width:100%">    <img src="Dataset/29.jpg"  style="width:100%">    <img src="Dataset/213.jpg"  style="width:100%">   <img src="Dataset/53.jpg"  style="width:100%"></pre>



<h2>Architecture :</h2>
<pre>        <img src="Dump/Architecture.jpeg"  style="width:100%"></pre>
<h2>ML Models Used :</h2>
<pre>   1. <a href="https://www.tensorflow.org/api_docs/python/tf/keras/applications/resnet">Resnet</a>
   2. <a href="https://www.tensorflow.org/api_docs/python/tf/keras/applications/MobileNetV2">MobileNetV2</a>
   3. <a href="https://blog.keras.io/building-autoencoders-in-keras.html">Auto-Encoder</a>
   4. <a href="https://www.tensorflow.org/api_docs/python/tf/keras/applications/DenseNet121">DenseNet</a></pre>
<h2>Adversarial Attack :</h2>

1. Fast Gradient Sign Method(FGSM) - [Goodfellow, I. J., Shlens, J., and Szegedy, C. Explaining and harnessing adversarial examples. arXiv preprint arXiv:1412.6572, 2014b.](https://arxiv.org/abs/1412.6572)
```python
   def create_adversarial_pattern(input_image, input_label):
     with tf.GradientTape() as tape:
       tape.watch(input_image)
       prediction = pretrained_model(input_image)
       loss = loss_object(input_label, prediction)
     gradient = tape.gradient(loss, input_image)
     signed_grad = tf.sign(gradient)
     return signed_grad
```
<table>
<thead>
  <tr>
    <th>Module 1 : Auto Encoder</th>
    <th>Auto-encoders can be used for Noise Filtering purpose. By feeding them noisy data as inputs and clean data as outputs, it’s possible to make them remove noise from the input image. This way, auto-encoders can serve as denoisers.</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Module 2 : Block Switching</td>
    <td>Switching block in this experiment consists of multiple channels. Each regular model is split into a lower part, containing all convolutional layer. lower parts are again combined to form single output providing parallel channels of block switching while the other parts are discarded. These models tend to have similar characteristics in terms of classification accuracy and robustness, yet different model parameters due to random initialization and stochasticity in the training process</td>
  </tr>
  <tr>
    <td>Module 3 : Grad-CAM</td>
    <td>Grad-CAM ( Activation Maps )uses the gradients of any target concept (say logits for “dog” or even a caption), flowing into the final convolutional layer to produce a coarse localization map highlighting the important regions in the image for predicting the concept.”</td>
  </tr>
</tbody>
</table>
