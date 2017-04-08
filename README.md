## DukeMTMC_reID Description
![](https://github.com/layumi/Duke_evaluation/blob/master/DukeMTMC_reID_mosaic.jpg)
DukeMTMC_reID is a subset of the [DukeMTMC](http://vision.cs.duke.edu/DukeMTMC/) for image-based re-ID, in the format of the Market-1501 dataset. The original dataset contains 85-minute high-resolution videos from 8 different cameras. Hand-drawn pedestrain bounding boxes are available. 

** What's new: We update the name of the dataset from 'Duke' to 'DukeMTMC_reID' and we add the original license from DukeMTMC.**

We crop pedestrain images from the videos every 120 frames, yielding in total 36,411 bounding boxes with IDs. There are 1,404 identities appearing in more than two cameras and 408 identities (distractor ID) who appear in only one camera. We randomly select 702 IDs as training set and the remaining 702 IDs as the testing set. In the testing set, we pick one query image for each ID in each camera and put the remaining images in the gallery. 

**As a result, we get 16,522 training images of 702 identities, 2,228 query images of the other 702 identities and 17,661 gallery images.** 

### About Dataset
|File  | Description | 
| --------   | -----  |
|/bounding_box_test  | The gallery images. We retrieve a query from this image pool.|
|/bounding_box_train  | The training images. This dir contains the images from 702 different identities.|
|/query  | The query images. Each of them is from different identities in different cameras.|

**Naming Rule of the images** In bbox "0005_c2_f0046985.jpg", "0005" is the identity. "c2" means the image from Camera 2. "f0046985" is the 46985th frame in the video of Camera 2.

### Dataset Licence
Please follow the [DukeMTMC LICENSE](https://github.com/layumi/DukeMTMC_reID_evaluation/blob/master/DukeMTMC_LICENSE.txt). You are free to share, creat and share the dataset, in the manner specified in the license. 

The DukeMTMC_reID evaluation code is under the MIT License.

### Download Dataset

You can download the DukeMTMC_reID dataset from [GoogleDriver](https://drive.google.com/open?id=0B0VOCNYh8HeRV2FGSFNxSDhYR0E)
or ([BaiduYun](https://pan.baidu.com/s/1jHLbPB4) password:yw2u).

If these links are unavailable, please don't hesitate to contact me to update links. Thank you.
### Evaluation
To evaluate, you need to calculate your gallery and query feature (i.e., 17661x2048 and 2228x2048 matrix) and save them in advance. Then download the codes in this repository. You just need to change the image path and the feature path in the `evaluation_res_duke_fast.m` and run it to evaluate.

### Baseline
|Methods | Rank@1 | mAP| Reference|
| -------- | ----- | ---- | ---- |
|BoW+kissme | 25.13% | 12.17% | "Scalable person re-identification: a benchmark", Liang Zheng, Liyue Shen, Lu Tian, Shengjin Wang, Jingdong Wang, Qi Tian, ICCV 2015|
|LOMO+XQDA | 30.75% | 17.04% | "Person Re-identification by Local Maximal Occurrence Representation and Metric Learning", Shengcai Liao, Yang Hu, Xiangyu Zhu, and Stan Z. Li, CVPR 2015|
|Basel.  | 65.22% | 44.99%| "Unlabeled Samples Generated by GAN Improve the Person Re-identification Baseline in vitro", Zheng, Zhedong and Zheng, Liang and Yang, Yi, arXiv:1701.07717|
|Basel. + LSRO   | 67.68% | 47.13%| "Unlabeled Samples Generated by GAN Improve the Person Re-identification Baseline in vitro", Zheng, Zhedong and Zheng, Liang and Yang, Yi, arXiv:1701.07717|
### Sample Retrieval
![](https://github.com/layumi/Duke_evaluation/blob/master/duke_rank.jpg)

### Citation
DukeMTMC Dataset [Bibtex](https://raw.githubusercontent.com/layumi/DukeMTMC_reID_evaluation/master/citation_dataset.txt)

DukeMTMC_reID Protocol, Baseline [Bibtex](https://raw.githubusercontent.com/layumi/DukeMTMC_reID_evaluation/master/citation_protocol.txt)
