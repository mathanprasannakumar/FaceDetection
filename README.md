# FaceDetection

<h1>Face Detection using VGG16 as a inital layer backend with a combination of custom built model</h1>

<h1>1) Datapreparation</h1>
<ul>
  <li>Here i used labelled faces in the wild , and annoted the 1000 images by myself using  labelme tool </li>
<p>Check out here for <a href= "https://github.com/wkentaro/labelme"><b>label me</b></p>
  <li>After annotating, Using <a href="https://github.com/albumentations-team/albumentations"><b>albumentations tool</b></a> applied transormation to each image</li>
  <li>Best thing about albumentations is if you resize the image after annotation using albumentations it will resize the bbox or annotations as well</li>
  <p><b>File structure</b></p>
  <ul>
    <li>/root</li>
    <ul>
      <li>aug</li>
      <ul>
        <li>train</li>
        <ul>
          <li>images</li>
          <li>labels</li>
        </ul>
        <li>test</li>
        <ul>
          <li>images</li>
          <li>labels</li>
        </ul>
        <li>val</li>
        <ul>
          <li>images</li>
          <li>labels</li>
      </ul>
    </ul>
  </ul>
</ul>
  <li>Train - 20,000 images</li>
  <li>Test - 5000 images</li>
  <li>val - 5000 images</li>
</ul>
<ul>
  <li>For the data pipeline , shuffle size in buffer - size of images in each category</li>
  <li>batch size : 16</li>
  <li>prefetch: 8 </li>
</ul>
<h1>2) Model Structure</h1>
<ul>
  <li>Total params: 16,826,181</li>
  <li>Trainable params: 16,826,181</li>
</ul>

<ul>
  <li>The output layer will be of two part </li>
  <p>1) classification layer - (Binary Classification with sigmoid activation function)</p>
  <p>2) Localisation layer - (Bounding box regression with 4 outputs)</p>
</ul>
<ul>
  <h5>Loss function</h5>
  <li>1) Binary cross entropy loss </li>
  <li>2) Localization loss</li>
</ul>






