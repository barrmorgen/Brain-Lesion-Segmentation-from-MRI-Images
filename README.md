# Brain-Lesion-Segmentation-from-MRI-Images
This work aims to segment the BraTS 2015 dataset of brain tumor images, and label the different regions. This is part of the “Multimodal Brain Tumor Segmentation Challenge 2015”

MRI scannings are essential in the effort of diagnosing and treating brain tumours. Often, the MRI data includes artifacts added as a result of several reasons. They can happen due to a movement of the patient during the scan, metallic implants the patient has or foreign bodies. Also it can be affected by the MRI machine itself. One possibility is inhomogeneity in the magnetic field applied. These artifacts result in bias to the scans, which may affect the segmentation and the diagnostic process models. Other types of artifacts can occur due to Finite sampling, k-space encoding, and Fourier transformation that may cause aliasing and Gibbs phenomena. Characteristics of pulse sequences may cause black boundary, Moiré, and phase-encoding artifacts. Hardware issues may cause central point and RF overflow artifacts. 

Computer algorithms for brain lesion segmentation aim to isolate malignant tumorous regions from the healthy tissue, in a quick and more accurate manner, compared to the manual segmentation process, helping to provide a successful treatment.
This project aims to compare three published deep learning segmentation models using 
FCN: Fully convolutional network
U-Net: Convolutional networks image segmentation
CE-Net: Context encoder networks image segmentation
This work aims to segment the BraTS 2015 dataset of brain tumor, and label the different regions. This is part of the “Multimodal Brain Tumor Segmentation Challenge 2015” [http://www.braintumorsegmentation.org/]. The brain regions are to be segmented and labeled to: 1) necrosis, 2) edema, 3) non-enhancing tumor, 4) enhancing tumor, 5) else. The dataset contains fully anonymized images from the Cancer Imaging Archive, subdivided to high grade and low grade images. Each patient is modeled using 4 images T1, T1-C, T2 and FLAIR. A fifth image contains the true labels to each pixel.

Implementation of the segmentation models was implemented to randomly-selected 33x33 patches of brain MRI images. In this work we examine three possible methods for the implementation:
Method 1)  Application of a fully convolutional neural network (FCN) with 4 convolutional, max-pooling layers followed by convolution and softmax layers. This model implements a pixel-wise segmentation problem as a classification problem [2]. This model aims to label, pixel-by-pixel, patches around the central pixels to be: necrosis, edema, non-enhancing tumor, enhancing tumor, else (Fig.1).
Method 2) Implementation of a U-Net [3]. In this implementation successive layers are downsampled until a determined ‘depth’ of the network. Then the layers are upsampled, concatenated and convolved with the previous layers consecutively, increasing the resolution of the output. (Fig.2). 
Method 3) Implementation of a CE-Net [4]. (Fig.3). This model relies on a novel  dense atrous convolution (DAC) block and a  residual multi-kernel pooling (RMP) block to get more features out of the input and preserve more of their spatial information in order to increase the output accuracy.


### Refrences
1. Havaei, M., Davy, A., Warde-Farley, D., Biard, A., Courville, A., Bengio, Y., ... & Larochelle, H. (2017). Brain tumor segmentation with deep neural networks. Medical image analysis, 35, 18-31
2. Menze, B. H., Jakab, A., Bauer, S., Kalpathy-Cramer, J., Farahani, K., Kirby, J., ... & Lanczi, L. (2014). The multimodal brain tumor image segmentation benchmark (BRATS). IEEE transactions on medical imaging, 34(10), 1993-2024
3. Ronneberger, O., Fischer, P., & Brox, T. (2015, October). U-net: Convolutional networks for biomedical image segmentation. In International Conference on Medical image computing and computer-assisted intervention (pp. 234-241). Springer, Cham
4. Gu, Z., Cheng, J., Fu, H., Zhou, K., Hao, H., Zhao, Y., ... & Liu, J. (2019). CE-Net: context encoder network for 2D medical image segmentation. IEEE transactions on medical imaging, 38(10), 2281-2292
