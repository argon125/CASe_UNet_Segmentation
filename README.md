# CASe_UNet_Segmentation
Official Repository of the Best Paper winning paper titled "CASE_UNet: Multilevel Multiscale UNet for Medical Image Segmentation" at the 4th International Conference on Computer Vision, High Performance Computing, Smart Devices and Networks (CHSN 2023)

Abstract: Encoder-decoder architectures have been extensively used for semantic segmentation tasks, including biomedical image segmentation. Most architectures utilize UNet as the base deep learning encoder-decoder network for biomedical image segmentation. Multi-scale feature extraction using convolution involving different kernel sizes is very important for an effective analysis of global and local features. UNet3+ can extract multilevel features from different layers of the encoder-decoder, which could be appropriately concatenated with decoder blocks. This paper leverages the combination of multi-scale features from convolution to extract higher-level semantics and multi-level hierarchical features from different blocks of the encoder-decoder as performed with UNet3+. We also incorporate multi-head attention in the bottleneck to further enhance extracted features from convolution, thus making a  UNet architecture combining Convolution and Attention for Segmentation (CASe\_UNet), combined with a hybrid loss for reducing precision and recall in pixel classification. The proposed architecture also tries to encounter class imbalance by assigning class weights inversely proportional to the probability distribution of each class. The approach is trained and validated on LiTS 2017 to identify tumors in the Liver and EndoVis 2018 Medical Instrument Segmentation data. Experimental results, along with ablation experiments, show that the proposed architecture achieves good results with an IOU and Dice coefficient of 0.9438 and 0.8684, respectively, on the EndoVis 2018 dataset and the benchmark IoU and Dice coefficient of 0.9166 and 0.9482 on LiTS 2017 data. 

## Proposed Methodology:

<img width="869" alt="image" src="https://github.com/argon125/CASe_UNet_Segmentation/assets/64146402/2af9fc6f-bab3-4956-ad33-5ba7d1b5fc5f">

## Experimental Setup:

The images of both datasets were resized to a dimension of 512*512*3. The architectures were trained on an Nvidia A6000 GPU with 32GB RAM and 48GB vRAM. The cost function minimized during backpropagation of the model weights is a combination of Weighted Categorical Cross Entropy (CCE) for multiclass segmentation (class weights inversely proportional to the pixel probability distribution), Structural Similarity Index (SSIM) for evaluating the structural similarity between the predicted map and the ground truth and dice and dice loss to reduce false positive and false negative predictions. The optimizer used is Adamax to perform adaptive gradient descent. 

## Results and Discussion

