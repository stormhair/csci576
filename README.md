## CSCI576 course project

#### The goal of the project
* Indexing a video
* Given an image, query the image in the video and generate a short video segment which is relevant to the image

#### Method[1]
1. Index each key frame with histogram of each color channel and SURF[1].
2. When querying an image, calculate its histogram of each color channel and SURF. Compare its feature vector to each key frame and return the most similar key frame. To measure the similarity of histogram, KL divergence is used to measure the similarity of each historgram. For SURF, we use the summation of the number of well matched points and the average distance of each well matched points. Let this quantity be $S$ and let the KL divergence of _ith_ histogram be $D_i$. Then the measurement for a whole frame is $1/S+\sigma{D_i}$.
3. Generate the retrieved video clip whose frames are centered at the key frame retrieved.

#### Dependencies
OpenCV 2.4.12

#### Reference
[1] A. Araujo, D. Chen, P. Vajda, etc, Real-Time Query-by-Image Video Search System. _MM'14_. (2014)



[2] H. Bay, T. Tuytelaars and L. V. Gool, SURF: Speeded Up Robust Features. _Computer Vision and Image Understanding 110(3)_. p.346 - p.359, (2008)
