## CSCI576 course project

#### The goal of the project
* Indexing a video
* Given an image, query the image in the video and generate a short video segment which is relevant to the image

#### Method
1. Index each key frame with histogram of each color channel and SURF[1].
2. When querying an image, calculate its histogram of each color channel and SURF. Compare its feature vector to each key frame and return the most similar key frame. To measure the similarity of histogram, KL divergence is used to measure the similarity of each historgram. For SURF, we use the summation of the number of well matched points and the average distance of each well matched points. Let this quantity be $S$ and let the KL divergence of _ith_ histogram be $D_i$. Then the measurement for a whole frame is $1/_S_+\sigma{D_i}$
.
3. Generate the retrieved video clip whose frames are centered at the key frame retrieved.

#### Reference
[1] H. Bay, T. Tuytelaars and L. V. Gool. SURF: Speeded Up Robust Features. _Computer Vision and Image Understanding_, Volume 110, Issue3, June 2008, pp346 - 359.