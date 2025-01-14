# adeleine

## Update
- 03/20/2023: Change repository's name from Colorization to adeleine

## Overview
This repository is about the deep-learing based automatic line art colorization with or without hints. There are mainly three types of hints.
  
- Atari: Colorization with hints that include some lines in desired color (ex. PaintsChainer)
- Tag: Colorization with tags (ex. Tag2Pix)
- Reference: Colorization with reference images (ex. style2paints V1)
  
## Line extraction method
There are many kinds of line extraction methods, such as XDoG or SketchKeras. If we train the model with only single type of the line art, trained model tends to overfit and cannot colorize other types of line art properly (ref Tag2Pix). Therefore, three types of line art are mainly used.

- XDoG: Line extraction using two Gaussian distributions difference to standard deviations
- SketchKeras: Line extraction using UNet. Lines obtained by SketchKeras are like pencil drawings.
- Sketch Simplification: Line extraction using Fully-Convolutional Networks. Lines obtained by Sketch Simplification are like digital drawings.

An example obtained by these line extraction methods is as follows.  

![](./Data/lineart.png)

Moreover, I usually add two types of data augmenation to line arts to avoid overfitting.

- Randomly morphology transformation to take various thicks of lines
- Randomly RGB values of lines to incorporate various depths of lines

## Experiments without hints

### Methods
- [x] pix2pix
- [x] pix2pixHD
- [X] bicyclegan

### Results
| Method | Result |
| ---- | ---- |
| pix2pix & pix2pixHD | ![](./Data/nohint_comparison.png) |
| bicyclegan | ![](./nohint_bicyclegan/data/result1.png) |

## Experiment with atari

### Methods
- [x] userhint
- [x] userhint v2
- [x] whitebox
- [x] spade

### Results
| Method | Result |
| ---- | ---- |
| userhint | ![here](./atari_userhint/data/result2.png) |
| userhint v2 | ![](./atari_userhint_v2/data/11859.png) ![](./atari_userhint_v2/data/12008.png) |
| whitebox | ![](./atari_whitebox/data/result2.png) |
| spade | ![](./atari_spade/data/result1.png) |

## Experiment with reference

### Methods
- [x] adain
- [x] scft
- [x] video

### Results
| Method | Result |
| ---- | ---- |
| adain | ![here](./reference_adain/data/res1.png)
| scft | ![](./reference_scft/data/result2.png)![](./reference_scft/data/result4.png)
| video | ![](./reference_video/data/never_color1.gif)![](./reference_video/data/sakura1_color1.gif)![](./reference_video/data/rayearth1_color1.gif) |

## GUI application
![](./Adeleine/data/result1.png)

## LICENSE
MIT License on only Adeleine. The license is not effective on other implementations.

## References
- [XDoG: An eXtended difference-of-Gaussians compendium including advanced image stylization](https://users.cs.northwestern.edu/~sco590/winnemoeller-cag2012.pdf)
- [sketchKeras](https://github.com/lllyasviel/sketchKeras)
- [Learning to Simplify: Fully Convolutional Networks for Rough Sketch Cleanup](https://esslab.jp/~ess/publications/SimoSerraSIGGRAPH2016.pdf)
- [Image-to-Image Translation with Conditional Adversarial Networks](https://arxiv.org/pdf/1611.07004.pdf)
- [High-Resolution Image Synthesis and Semantic Manipulation with Conditional GANs](https://arxiv.org/pdf/1711.11585.pdf)
- [Toward Multimodal Image-to-Image Translation](https://arxiv.org/pdf/1711.11586.pdf)
- [Arbitrary Style Transfer in Real-time with Adaptive Instance Normalization](https://arxiv.org/pdf/1703.06868.pdf)
- [Mode Seeking Generative Adversarial Networks for Diverse Image Synthesis](https://arxiv.org/pdf/1903.05628.pdf)
- [Semantic Image Synthesis with Spatially-Adaptive Normalization](https://arxiv.org/pdf/1903.07291.pdf)
- [Real-Time User-Guided Image Colorization with Learned Deep Priors](https://arxiv.org/pdf/1705.02999.pdf)
- [Style Transfer for Anime Sketches with Enhanced Residual U-net and Auxiliary Classifier GAN](https://arxiv.org/pdf/1706.03319.pdf)
- [Two-stage Sketch Colorization](http://www.cse.cuhk.edu.hk/~ttwong/papers/colorize/colorize.pdf)
- [Tag2Pix: Line Art Colorization Using Text Tag With SECat and Changing Loss](https://openaccess.thecvf.com/content_ICCV_2019/papers/Kim_Tag2Pix_Line_Art_Colorization_Using_Text_Tag_With_SECat_and_ICCV_2019_paper.pdf)
- [Reference-Based Sketch Image Colorization using Augmented-Self Reference and Dense Semantic Correspondence](https://arxiv.org/pdf/2005.05207.pdf)
- [Learning to Cartoonize Using White-box Cartoon Representations](https://github.com/SystemErrorWang/White-box-Cartoonization/blob/master/paper/06791.pdf)
- [Deep Line Art Video Colorization with a Few References](https://arxiv.org/pdf/2003.10685.pdf)
- [DanbooRegion: An Illustration Region Dataset](https://lllyasviel.github.io/DanbooRegion/paper/paper.pdf)
