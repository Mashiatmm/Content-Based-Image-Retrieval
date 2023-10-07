# Content-Based-Image-Retrieval

## Dataset
[CBIR Dataset](https://www.kaggle.com/datasets/theaayushbajaj/cbir-dataset)

***Size :*** 4738 Images of animals  

## Pipeline

This is a *partial* implementation of the pipeline of this [paper](https://www.sciencedirect.com/science/article/pii/S0893608023001867) with some modifications and a new dataset. 

![Pipeline](https://github.com/Mashiatmm/Content-Based-Image-Retrieval/blob/main/Picture1.jpg)

The images are first trained on the following convolutional AutoEncoder model as the backbone network to extract local features of size 256 * 32 * 32. The loss is minimized by calculating MSE of the decoded output and the original image. 

![AutoEncoder](https://github.com/Mashiatmm/Content-Based-Image-Retrieval/blob/main/1_op0VO_QK4vMtCnXtmigDhA.png)

The highlights of the pipeline for image retrieval are summarized below.

* __Generalized Mean Pooling__ : The outputs of the network is passed through a  generalized mean pooling (GeM) layer.
* __L2 norm feature selection__ : 200 out of 256 2D local featurea are selected based on high L2 norm values.
* __Cosine Similarity__ : The similarity of two images are computed by calculating the cosine similarity between them.

__Note :__ K-means clustering is not implemented here as shown in the pipeline and many steps are also excluded. This is a very simplified and modified pipeline.

## Output
![Output](https://github.com/Mashiatmm/Content-Based-Image-Retrieval/blob/main/Picture2.png)

This project is done as a part of the Advanced Digital Image Processing Course.

## Credits

The codebase is modified from this [work](https://www.kaggle.com/code/theaayushbajaj/content-based-image-retrieval-pytorch) here.


