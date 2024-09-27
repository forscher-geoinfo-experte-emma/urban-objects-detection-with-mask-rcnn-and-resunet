<h3 align="left">Pre-train globally but fine-tune and apply locally</h3>

Open global datasets often fall short of meeting the precision requirements for local applications. To address this, we propose a pipeline that integrates extensive publicly available annotated datasets from around the world to train a base model, which can then be fine-tuned using a limited set of locally sourced samples. This approach allows for the generation of customised data, over which full control can be maintained, thereby enhancing local accuracy. Since deep learning models, utilizing various segmentation approaches, demonstrate differing levels of effectiveness in extracting urban objects such as buildings, in our paper [Local Evaluation of Large-scale Remote Sensing Machine Learning-generated Building and Road Dataset: The Case of Rwanda](https://link.springer.com/article/10.1007/s41064-024-00297-9), we explored [ResUNet](https://arxiv.org/abs/1711.10684) and [Mask R‑CNN](https://github.com/matterport/Mask_RCNN) to examine the performance variations across distinct building detection methodologies: bottom-up, end-to-end, and a hybrid approach combining the two. The shapes generated by our models were then compared to the ones provided by Microsoft's and Google's global datasets, allowing for a comprehensive evaluation of performance and accuracy in the local context.  

<h3 align="left"> Installation</h3>
<ul>
  <li > Mask R-CNN: You simply need to download or clone the Mask R-CNN TensorFlow 2 repository, as explained 
<a href="https://github.com/ahmedfgad/Mask-RCNN-TF2" style="cursor: pointer;">here</a> to your local directory and follow the installation instructions. 
Depending on the resources available, you may need to install TensorFlow for either GPU or CPU. 
Detailed instructions can be found <a href="https://www.tensorflow.org/install/pip" style="cursor: pointer;">here</a>.</li>
  </ul>
  


<ul>
  <li > ResUNet:The installation, based on TensorFlow 2, can be found 
    <a href="https://github.com/edwinpalegre/EE8204-ResUNet" style="cursor: pointer;">here</a>, 
    and is derived from the implementation of the Deep Residual U-Net for Road Extraction by Zhang et al., 
    which you can explore <a href="https://arxiv.org/abs/1711.10684" style="cursor: pointer;">here</a>.</li>
  </ul>

<h3 align="left"> Get started</h3>

After installation, the pipeline can be executed by downloading data from open-access benchmark repositories. Aerial imagery and building shapefiles from the WHU dataset, Open Cities dataset, and locally annotated samples in Rwanda can be obtained through direct contact @ <a href="https://www.linkedin.com/in/emmanuel-nyandwi-5ab81829 style="cursor: pointer;">here</a>. The data should be preprocessed by tiling the images into patches (e.g., 512x512) and cropping the shapefiles containing building information to match the extent of these patches. Labels are generated by rasterising the building shapes to create binary labels, which can then be converted into instance labels using the binary2instance code.

To train and perform inference, run the mask_rcnn_train_predict.py and resunet_train_predict.py scripts for training and inference with Mask R-CNN and ResUNet, respectively.    

<h3 align="left"> Citation</h3>

You may cite our paper for reference as follow:  Nyandwi, E., Gerke, M. & Achanccaray, P. Local Evaluation of Large-scale Remote Sensing Machine Learning-generated Building and Road Dataset: The Case of Rwanda. PFG (2024). https://doi.org/10.1007/s41064-024-00297-9
