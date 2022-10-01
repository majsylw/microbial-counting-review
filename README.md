# Microbial colony detection and classification - review of useful resources

A list of useful resources in the microbial colony detection and counting, such as datasets, papers, links to open source projects.

## Contributing

Feel free to add **issue** with short description of new publication or create a **pull request** - add the new resource or fill missing description.
⭐️ the repository if you like it! 

## Table of Contents

* [Relevant projects](https://github.com/majsylw/microbial-counting-review/blob/master/README.md#Relevant-projects)
* [Datasets](https://github.com/majsylw/microbial-counting-review/blob/master/README.md#Datasets)
* [Papers](https://github.com/majsylw/microbial-counting-review/blob/main/README.md#Papers)

## Relevant projects

- [AGAR](https://agar.neurosys.com/) -- entire dataset contains 18k images with 5 different microbial species with bounding box level annotations,
- [DIBaS](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5599001/) -- entire dataset contains 660 microscopic images with 33 different genera and species,
- [MikrobIA](http://www.microbia.org/index.php/resources) -- MicrobIA Haemolysis Dataset (classification of hemolysis type on segmented colonies); MicrobIA Segments Enumeration Dataset (classification by number of colonies on blood agar in segmented aggregation); MicrobIA Images Dataset (chromatic solid agar plates without annotations); MicrobIA Hyperspectral Dataset,
- [Project BacXeption](https://github.com/universvm/BacXeption) -- based on Xception: Deep Learning with Depthwise Separable Convolutions, 2016; mainly localize separete cells on Microscope images.
- [Capstone project](https://github.com/deibyrios/bacteria-classification) -- project to count bacteria from dish: divide into patches, classify positive (with colonies) and negative (no colonies) and then try to segment bacteria from patches with colonies.

## Datasets

| Name                               	| No. categories 	                             | No. subcategories                             | No. images            | Annotation                	| Comment                              	| Website                                                             	|
|------------------------------------	|----------------	                             |-------------------                            |------------           |---------------------------	|--------------------------------------	|---------------------------------------------------------------------	|
| AGAR                                  | 3 (empty, countable, and uncountable)              | 7 (5 microbes + defects + contamination class)| 18 000  plates        | Detection   (in COCO format)     | microbial colonies on agar plates     | https://agar.neurosys.com/                                            |
| MicrobIA Segments Enumeration Dataset | 2 (segments, and outliers)                         | 8 (7 enumeration segments + outliers)         |~29 000 segments       | Segmentation masks               | microbial colonies on agar plates     | http://www.microbia.org/index.php/resources                           |
| MicrobIA Haemolysis Dataset           | 2 (countable colony and confluent growth segments) | 3 (alpha, beta, gamma hemolysis)              | ~2 400 segments (from 235 plates)    | Classification    | segmented colonies on blood agar      | http://www.microbia.org/index.php/resources                           |
| DIBaS                                 | 33 (different microbial genera and species)        | -                                             | 660                   | Classification                   | microscopic images                    | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5599001/                 |

## Papers

| Paper | Task        | Comment     |
|:-----:|:-----------:|:-----------:|
| [K. M. Graczyk et al., 2022](https://arxiv.org/pdf/2203.09474.pdf) | Counting | Authors studied statistical properties of the density map (DM) approach to counting microbiological objects on images using the bootstrap and the Monte Carlo (MC) dropout. The detailed analysis of the uncertainties for the DM predictions leads to a deeper understanding of the DM model's deficiencies. Authors proposed a self-normalization module in the U2Net. [example code for DM](https://github.com/NeuroSYS-pl/objects_counting_dmap) [example code for statistical analysis](https://github.com/kgraczyk/objects_counting_dmap) |
| [J. Pawłowski et al., 2021](https://arxiv.org/pdf/2111.03789.pdf) | Synthetic Data Generation | Authors introduced an effective strategy to generate an annotated synthetic dataset of microbiological images of Petri dishes that can be used to train deep learning models in a fully supervised fashion. [code for studies](https://github.com/jarek-pawlowski/microbial-dataset-generation) |
| [S. Majchrowska et al., 2021](https://arxiv.org/abs/2108.10103)| Detection | Comparison of the performance of three well-known deep learning approaches for object detection on the AGAR dataset (high resolution subset), namely two-stage, one-stage and transformer based neural networks. |
| [S. Majchrowska et al., 2021](https://arxiv.org/abs/2108.01234)| Detection | This paper introduces the Annotated Germs for Automated Recognition (AGAR) dataset, an 18k image database of five different species of microbial colonies cultured on agar plates. |
| [T. Naets et al., 2021](https://arxiv.org/abs/2103.05337)| Instance segmentation | This paper presents an application of the Mask R-CNN to the counting of different types of bacterial colony forming units that were cultured in Petri dishes. |
| [K. Dijkstra et al., 2021](https://www.sciencedirect.com/science/article/pii/S0925231220316647#s0070)| Segmentation & Counting | This paper presents CentroidNetV2, a novel hybrid Convolutional Neural Network (CNN) that has been specifically designed to segment and count many small and connected object instances - used on bacterial plates (Legionella colonies (with contaminations) which were cultivated on Buffered Charcoal Yeast Agar). |
| [H. Wang et al., 2020](https://www.nature.com/articles/s41377-020-00358-9)| Detection | Whole setup to measure bacterial colony growth, based on lense-free holographic microscopy. |
| [P. Andreini et al., 2020](https://www.sciencedirect.com/science/article/pii/S0169260719311216) | Synthetic data generation | Production of synthetic images of plate with GANs and style transfer, based on MicrobIA dataset on blood agar. |
| [J. Bär et al., 2020](https://www.nature.com/articles/s41598-020-72979-4) |  Detection | Also application, no CNN, but they account growth rate, colony forming shape ect. Creation of application ColTapp. |
| [T. Beznik et al., 2020](https://arxiv.org/pdf/2009.00926.pdf)| Semantic segmentation | Detection of colonies with U-Net and ResNet-152 with segmentation approaches, but only for 108 plates. |
| [M. Talo et al., 2019](https://arxiv.org/ftp/arxiv/papers/1912/1912.08765.pdf) | Classification |  Build CNN Classifier based on ResNet with few modification to classify images from DIBaS dataset (microscopic images). |
| [M. Savardi al., 2018](https://www.sciencedirect.com/science/article/pii/S0169260717307113) |  Classification | SVM to classify colonies growth on blood agar to distiguish by hemolysys type. Part of MicrobIA project. Python code available at MicrobIA site. |
| [G. Zhu et al., 2018](https://pubmed.ncbi.nlm.nih.gov/30195830/) | Semantic segmentation | Few lightning condition (near-infrared light), segmentation based on thresholding, only few plates as example. |
| [B. Zielinski et al., 2017](https://www.sciencedirect.com/science/article/pii/S0031320316301650)  | Classification |   Classification with CNN on microscopic images. Creation of DIBaS Dataset. |
| [A. Ferrari et al., 2017](https://www.sciencedirect.com/science/article/pii/S0031320316301650) |  Counting |  CNN to classify aglomerated colonies into 7 groups: 1 colony, 2 colonies, ..., 6 colonies, empty. The use blood agar plate. Part of MicrobIA project. Earlier the same gropu produces also MicrobIA Image Database with images of dish with a chromogenic substrate (some binary masks are also provided). |
| [D. Nie et al., 2015](https://dl.acm.org/doi/10.1145/2808719.2808751)| Segmentation & classification |   Model to classify into empty and occupied by bacteria patches, and then try to segment occupied pathes, and again use CNN to classify bacteria spieces. They use around 800 images, self-created (not accesible). [code](https://github.com/ginobilinie/BacteriaImageProcess) |
| [A. Ferrari et al., 2014](https://iris.unibs.it/retrieve/handle/11379/459131/13883/IST-2014.pdf)|  Counting |  Using Zernike moments to distinguish isolated colonies from aglomerata on chromagar solid agar plate.   | 
| [S. Brugger et al., 2012](https://pubmed.ncbi.nlm.nih.gov/22448267/) | Counting | Some ML thresholding method (binarization of image) with few samples of plates and Matlab application.   |
| [S. Sutton et al., 2011](http://www.microbiologynetwork.com/content/file/JVT_2011_v17n3_Accuracy-of-Plate-Count.pdf)| Counting | The linear range for common bacterial counts on standard sized plates is established (Poisson distribiution). They use wathershed to distinguish aglomerated colonies. |
| [C. Zhang et al., 2008](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=4545762) | Counting | One of the first 'serious' article based on thresholding with photos of agar plate, with special setup. |
| [D. Tomasiewicz et al., 1980](https://pubmed.ncbi.nlm.nih.gov/30822862/)| Counting | Set countable range for manual counting, which generally for a 100 mm Petri dish is placed between 30 and 300 CFUs. |
