# Fundamental Matrix Calculation

### [Specification](resources/ass3-spec.pdf)

### [Dataset](resources/kusvod2.tar)



## Introduction

* In this project you will implement the **calculation of a Fundamental matrix using your own algorithms**. 

* You can use the keypoint detection and matching approach used in the week 8 Workshop, as well as code for drawing lines on images, but the implementation of the Fundamental Matrix calculation must be your own work.



## Tasks

* Find keypoints and correspondences between two images ✔
* To implement the 8 point algorithm you will need to:
  * a. Shift and scale the pixel coordinates ✔
  * b. Compute the design matrix from sets of (at least) 8 points ✔
  * c. Perform an SVD of the design matrix to find its null space (you can use a library function for the SVD) ✔
  * d. Compose the draft fundamental matrix F ✔
  * e. Perform an SVD of the draft fundamental matrix, set the smallest singular value to zero and reassemble so that F now has determinant = 0 ✔
  * f. Calculate which correspondences are inliers and which are outliers using this F. You will need to allow for some error because the keypoint coordinates won’t lie exactly on the epipolar line so you will need to allow for 1-2 pixels error for a correct correspondence. Also remember to take into account any scaling you applied at step a. ✔
  * g. Wrap steps b-f in a RANSAC loop that runs enough times that you have a probability > 99% of finding 8 inliers and computing a good quality F. ✔
  * h. Re-estimate F using all the inliers. ✔
  * i. Compute F in terms of the original pixel coordinates (ie undo the effects of step a). ✔
* Randomly sample ten keypoint pairs from correspondences you have detected as inliers to your best F estimate and display these on the images, together with their epipolar lines. ✔
  * If you make this a separate cell in your jupyter notebook, you can run the cell more than once to see different random samplings. ✔



## Report

* Why you need each of these steps. 

* Design choices you have made along with numerical quantities. 

  * Choice of error tolerance at step f

  * Calculation needed to determine the number of RANSAC iterations at step g.

* Discuss whether there are images that work better than others in the dataset and why.
