# Project Description
<center>
  <h2>
      <b>Optimizing License Plate Detection using Adaptive Rotation and <a href="https://github.com/xinntao/Real-ESRGAN">REAL-ESRGAN</a></b>
  </h2>
</center>
<center>
  <img src="https://learnopencv.com/wp-content/uploads/2022/03/Automatic-License-Plate-Recognition-using-Deep-Learning.gif">
</center>

<p align="justify">
    The development of automatic license plate detection systems provides extensive benefits in transportation, security, and traffic surveillance. Vehicle number recognition technology enables the system to automatically identify license plate characters which can reduce manual inspection. This is beneficial in more effective traffic handling, parking control, and security surveillance. In addition, automatic license plate detection plays an important role in security and law enforcement, by providing accurate information about vehicles involved in crimes or traffic violations, allowing law enforcement to take quick and appropriate action.
</p>
<p align="justify">
    This automatic license plate detection system can also be used for parking time monitoring, automatic payment, and parking access control. This technology eliminates the need for physical tickets or access cards, reduces congestion, and improves user experience. In automated tolling systems, license plate detection helps identify vehicles and enables more efficient electronic payments, thereby improving traffic flow and reducing queues. Through license plate data collection, the system also provides valuable information for further analysis, such as traffic patterns and parking usage, which supports better transportation planning.
</p>
<center>

  <h3><b>The following is the Flowchart of Our Research</strong></b></h3>
  <br>
  <img src="https://s11.gifyu.com/images/SgHOE.gif" width="750">
</center>

<p align="justify">
    First, we <b>input the dataset</b> into Google Colab. Then, we perform <b>preprocessing</b> which is crucial to enhance the data quality. This preprocessing involves <b>two main stages</b>, namely <b>ESRGAN <a href="https://github.com/xinntao/Real-ESRGAN">(Enhanced Super-Resolution Generative Adversarial Network)</a></b> to improve image resolution and <b>Adaptive Rotate</b> for adjusting the rotation angle of the image. These two stages help ensure that our dataset is ready for model training and testing.
</p>

<p align="justify">
    Next, our dataset is <b>split into two parts</b>, namely <b>train set</b> and <b>test set</b>, through a splitting process. The train set will serve as our foundation for model fine-tuning. We use this train set to <b>train our model</b> to generate better predictions. After going through the <b>training</b> and <b>fine-tuning stages</b>, we <b>produce a model</b> that has been tailored to our dataset. This model is then used to <b>make predictions</b> using the <b>test set</b>. By following these steps, we successfully developed an optimized model capable of generating better predictions.
</p>

<center>
  <h3><b>The following are the results of ESRGAN and Adaptive Rotating</strong></b></h3>
  <br>
  <img src="https://s11.gifyu.com/images/SgHyH.gif" width="750">
</center>

<p align="justify">
   The following are some sample images that illustrate the comparison between the original image, the image after going through the ESRGAN process, and the image after undergoing the ESRGAN and rotation process. It is clearly seen that the original image has a poor quality and is a little blurry. After going through the ESRGAN process, the image becomes sharper and clearer. Furthermore, with the application of rotation, the image looks very good with the correct orientation (not tilted).
</p>
<center>
  <img src="https://s11.gifyu.com/images/SgHo4.gif">
</center>


<p align="justify">
<strong>Initially</strong>, the image dataset is provided as input. Each image in the dataset then undergoes <strong>contrast stretching</strong> process, which helps enhance the contrast and visual quality of the images. Subsequently, these images are <strong>resized</strong> to ensure they are not too large or too small, ensuring consistency in image sizes.
</p>
<p align="justify">
Next, <strong>edge detection</strong> is performed on the images using the <strong>Canny</strong> method to identify areas with sharp changes in color intensity. This process generates edges in the image, including <strong>horizontal</strong> and <strong>vertical edges</strong>. These edges are then <strong>grouped</strong> based on their <strong>edge slopes</strong>, resulting in separate groups of horizontal and vertical edge slopes. After grouping the edges, the next step is to <strong>determine the dominant horizontal and vertical edge slopes</strong> in each group. This information is used to <strong>rotate the images</strong> to align them with a more accurate orientation.
</p>
<p align="justify">
Next, the rotated images are passed to <strong>bounding box detection</strong> using a <strong>YOLO</strong> model that has been specifically <strong>fine-tuned</strong> for <strong>license plate detection</strong>. This model predicts <strong>bounding boxes</strong> around license plates in the images. If the <strong>confidence score</strong> of the prediction is greater than <strong>0.9</strong>, a <strong>cropping</strong> process is performed to focus on the license plate area. If the confidence score is less than <strong>0.9</strong>, this step is skipped. Afterward, the image is ready to be fed into a <strong>deep learning model</strong> to <strong>predict its license plate</strong>.
</p>

## How we Train the Model?
Because the input data is image data and it is not possible to use only the CPU. Our project is trained using a pretrained model with the help of GPU. We only use google collab Pro in making the model. with the help of the A100 GPU, we managed to do fine tuning of the previous pretrained TROCR and get much better accuracy.
