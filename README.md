# To run the file in your system:
1. Install Tensorflow ,scipy , matplotlib and numpy libraries<br>
2. Replace the 'base_image_path' and 'style_image_path' with the path of your images.<br>
3. Load vgg19 with weights pre-trained on ImageNet dataset. Replace path of 'vgg19_weights' with the path of your dowloaded vgg_19 weights.<br>
The above python file is written in Kaggle notebook with accelerator setting as 'GPU P100'<br> 

# Step followed to implement Art_Style_Transfer model are:
1.Load and Preprocess Images:<br>
Load the base image and style image.<br>
Preprocess the images to make them compatible with the VGG19 model.<br>

2.Build the VGG19 Model:<br>
Use the VGG19 model (pre-trained on ImageNet) as a feature extractor.<br>
Remove the fully connected layers at the top since we're only interested in convolutional feature maps.<br>

3.Define Style and Content Layers:<br>
Choose layers from the VGG19 model to extract style features and content features.<br>
Typically, style features are extracted from multiple convolutional layers, while content features are extracted from one specific layer.<br>

4.Compute Gram Matrix for Style:<br>
For each style layer, compute the Gram matrix of the feature maps. The Gram matrix encodes style information.<br>

5. Define Loss Functions:<br>
Define the style loss and content loss. The total loss is a combination of both.<br>
The style loss is the mean squared difference between the Gram matrices of the style features of the base and generated images.<br>
The content loss is the mean squared difference between the content features of the base and generated images.<br>

6. Optimization:<br>
Use an optimization algorithm (e.g., L-BFGS, Adam) to minimize the total loss.<br>
Update the pixels of the generated image to minimize the loss.<br>

7. Generate Stylized Image:<br>
Run the optimization process to generate a stylized image that combines the content of the base image with the style of the style image.<br>

## Conclusion<br>
Our model can be improved through increasing the number of iteration, or by trying out a different syle transfer algorithm which could preseve the edges of the base image, or by trying out with different optimizer to minimize gradient and loss.<br>

## References<br>
TensorFlow Documentation
