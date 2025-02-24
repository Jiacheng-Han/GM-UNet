<div align="center">
<h1>GM-UNet</h1>
<h3>GAN-based VM-UNet Achieves Higher Accuracy</h3>
</div>

This is the official code repository for "GM-UNet: GAN-based VM-UNet Achieves Higher Accuracy" [paper](https://ieeexplore.ieee.org/abstract/document/10780733). 

**1. Abstract** </br>
In the field of medical image segmentation, the
Ushape architecture model has been widely explored. Recently,
a novel architecture called Mamba, based on the State Space
Models (SSMs), has emerged. Subsequently, a Visual State Space
(VSS) block based on visual Mamba has also become a new core
module of Ushape architecture models represented by VM-UNet.
Although VSS block possesses linear computational complexity, it
constructs only four directional linear sequences when processing
images, thus inherently lacking the capability to capture local
features of the target image effectively. To enhance the capability
of VM-UNet in capturing image details, this paper introduces a
GM-UNet model, which integrates VM-UNet into the framework
of Generative Adversarial Networks (GANs): using VM-UNet as
the generator network for image segmentation and employing the
encoder of U-Net as the discriminator network. By incorporating
the image features extracted by the discriminator and introducing
weighted adversarial loss into the network training, the network
is trained until the discriminator struggles to distinguish the
source of segmented images, thereby obtaining an image segmentation network with superior capability in capturing image
details. Experimental results on segmenting liver CT images
demonstrate that the GM-UNet model outperforms VM-UNet in
various performance metrics and exhibits strong competitiveness
compared to other classic segmentation models based on Ushape
architecture.

**2. Main Environments** </br>
The environment installation procedure can be followed the steps below (python=3.10):</br>

```
conda create -n cfmunet python=3.10
conda activate cfmunet
pip install torch==2.1.1 torchvision==0.16.1 torchaudio==2.1.1 --index-url https://download.pytorch.org/whl/cu118
pip install packaging
pip install timm==0.4.12
pip install pytest chardet yacs termcolor
pip install submitit tensorboardX
pip install triton==2.0.0
pip install causal_conv1d
pip install mamba_ssm
pip install scikit-learn matplotlib thop h5py SimpleITK scikit-image medpy yacs
```

**3. Datasets** </br>
We utilized the open-source liver dataset LiTS2017, selecting 613 large-area liver CT images randomly. These images were divided into training and testing sets in an 8 : 2 ratio.

You can download our dataset in this repository.

**4. Train Your GM-UNet** </br>
You can try using the model in `GM-UNet.py`.

## Acknowledgement
Thanks to [VMamba](https://github.com/MzeroMiko/VMamba) and [VM-UNet](https://github.com/JCruan519/VM-UNet) for their outstanding work.
