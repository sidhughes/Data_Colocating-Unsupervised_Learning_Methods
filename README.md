# Data_Colocating-Unsupervised_Learning_Methods
GEOL0069 - Week 4 Pactical

## 1. Set up 

Here we introduce a series of setting up tools including Google Colab and Google Drive that are needed before undertaking the tasks.

## Google Colaboratory

Google Colaboratory, is a cloud-based service provided by Google that allows users to write, execute, and share Python code through a web browser. It offers free access to a machine equipped with a GPU, making it a popular choice for machine learning and data science projects. This is an user-freindly way to test, excecute machine learning tasks, without any environment set-up on your device. Below are the steps to get started with Google Colab:

## Google Drive

Google Drive is a cloud-based storage service provided by google which alllows users to store, organise,share and access files from any device. 

### Firstly we must mount our drive to give our code access to the downloaded data:

 ```sh
from google.colab import drive
drive.mount('/content/drive')
 ```

## Material to install/download

To streamline our data fetching and processing, we’ll first load the essential functions. These functions are identical to what we have for the data_fetching notebook in week 3. These functions essentially help you get metadata for the 2 satellites you care about.

### These are the packages we need to download to complete this practical:

   ```sh
!pip install rasterio
!pip install netCDF4
!pip install basemap
!pip install cartopy

   ```
### We aso have to download the following data sets:

[1. Sentinel-2 optical data ](https://drive.google.com/drive/folders/1CbKYPrN7wpPX-RhqRbb_9V-lRWTTU-it?usp=drive_link)

[2. Sentinel-3 OLCI data](https://drive.google.com/drive/folders/1SydvKe7V0ythxcu66_NTMHqE8HSxGA_z?usp=drive_link)



## 2. Introduction to Unsupervised Learning Methods {cite}`bishop2006pattern`

## Introduction to K-means Clustering

K-means clustering is a type of unsupervised learning algorithm used for partitioning a dataset into a set of k groups (or clusters), where k represents the number of groups pre-specified by the analyst. It classifies the data points based on the similarity of the features of the data {cite}`macqueen1967some`. The basic idea is to define k centroids, one for each cluster, and then assign each data point to the nearest centroid, while keeping the centroids as small as possible.

### Why K-means for Clustering?

K-means clustering is particularly well-suited for applications where:

- **The structure of the data is not known beforehand**: K-means doesn’t require any prior knowledge about the data distribution or structure, making it ideal for exploratory data analysis.
- **Simplicity and scalability**: The algorithm is straightforward to implement and can scale to large datasets relatively easily.

### Key Components of K-means

1. **Choosing K**: The number of clusters (k) is a parameter that needs to be specified before applying the algorithm.
2. **Centroids Initialization**: The initial placement of the centroids can affect the final results.
3. **Assignment Step**: Each data point is assigned to its nearest centroid, based on the squared Euclidean distance.
4. **Update Step**: The centroids are recomputed as the center of all the data points assigned to the respective cluster.

### The Iterative Process of K-means

The assignment and update steps are repeated iteratively until the centroids no longer move significantly, meaning the within-cluster variation is minimised. This iterative process ensures that the algorithm converges to a result, which might be a local optimum.

### Advantages of K-means

- **Efficiency**: K-means is computationally efficient.
- **Ease of interpretation**: The results of k-means clustering are easy to understand and interpret.

## Gaussian Mixture Models (GMM) {cite}`bishop2006pattern`

### Introduction to Gaussian Mixture Models

Gaussian Mixture Models (GMM) are a probabilistic model for representing normally distributed subpopulations within an overall population. The model assumes that the data is generated from a mixture of several Gaussian distributions, each with its own mean and variance {cite}`reynolds2009gaussian, mclachlan2004finite`. GMMs are widely used for clustering and density estimation, as they provide a method for representing complex distributions through the combination of simpler ones.

### Why Gaussian Mixture Models for Clustering?

Gaussian Mixture Models are particularly powerful in scenarios where:

- **Soft clustering is needed**: Unlike K-means, GMM provides the probability of each data point belonging to each cluster, offering a soft classification and understanding of the uncertainties in our data.
- **Flexibility in cluster covariance**: GMM allows for clusters to have different sizes and different shapes, making it more flexible to capture the true variance in the data.


### Key Components of GMM

1. **Number of Components (Gaussians)**: Similar to K in K-means, the number of Gaussians (components) is a parameter that needs to be set.
2. **Expectation-Maximization (EM) Algorithm**: GMMs use the EM algorithm for fitting, iteratively improving the likelihood of the data given the model.
3. **Covariance Type**: The shape, size, and orientation of the clusters are determined by the covariance type of the Gaussians (e.g., spherical, diagonal, tied, or full covariance).


### The EM Algorithm in GMM

The Expectation-Maximization (EM) algorithm is a two-step process:

- **Expectation Step (E-step)**: Calculate the probability that each data point belongs to each cluster.
- **Maximization Step (M-step)**: Update the parameters of the Gaussians (mean, covariance, and mixing coefficient) to maximize the likelihood of the data given these assignments.

This process is repeated until convergence, meaning the parameters do not significantly change from one iteration to the next.

### Advantages of GMM

- **Soft Clustering**: Provides a probabilistic framework for soft clustering, giving more information about the uncertainties in the data assignments.
- **Cluster Shape Flexibility**: Can adapt to ellipsoidal cluster shapes, thanks to the flexible covariance structure.



# Contact information

Sid Hughes - zcfbhug@ucl.ac.uk 

Project Link: [Data_Colocating-Unsupervised_Learning_Methods](https://github.com/sidhughes/Data_Colocating-Unsupervised_Learning_Methods)


# Acknowledgments
- This project represents 'GEOL0069 - week 4 practical' for 'AI for Earth Observation' module, taught by the UCL Earth Sciences Department.  
