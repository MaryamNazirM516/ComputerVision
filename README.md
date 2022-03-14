# <h1> Computer Vision </h1>
 
 **Project Title: An Automated Method for Counting Red Blood Cells using Image Processing**
 
**<h2> REQUIREMENTS:</h2>**

**import numpy of version:** 1.20.3

**import cv2 of version:** 4.5.4

**import matplotlib  of version:** 3.4.3

**<h2> Steps to follow:</h2>**
**Step 1:Removal of White blood cells:**


Removal of White blood cells is the preliminary step of proposed method. Dataset contain three types of Blood cells i-e
RBCS , WBCS and platelets. Our main focus is on segmentation and counting of RBCS . So we will have to remove
WBCS from images.


**Steps:**

• We created a separate file of python to select upper and lower ranges of white blood cells

• Then convert RGB image to HSV image

• We created a mask of white blood cells

• Then removed the mask from the original image

• We have image without white blood cells



**Step 2: Pre-Processing Techniques:**


**2.1 Gaussian Blurring:**


We apply a low pass blurring filter (gaussian filter) to smooth edges and remove noise from images.We used this blurring
to get better results.


**2.2 Median filtering:**


Median filtering is a non-linear smoothing spatial filter often used for noise reduction, thereby enhancing the quality of
the edges in an image. In median filtering, each input pixel is replaced by the median of the gray levels in the m-by-n
neighborhood around the corresponding pixels i.e. as given by the following equation:


Out put pixel = med f ilt2(image,[m,n]) (1)


where, [m, n] is the size of the mask, ‘image’ is the input image on which filtering is applied.



**2.3 Histogram equalization:**


Histogram Equalization is an image processing technique that adjusts the contrast of an image by using its histogram


**2.4 Contrast stretching:**


Contrast stretching (often called normalization) is a simple image enhancement technique that attempts to improve the
contrast in an image by ‘stretching’ the range of intensity values.This is normally done to accent image details that may
be difficult for the human viewer to observe. Our main goal to apply a contrast enhancement technique is to recover an
image from blurred images, also improve image quality of it.

**2.5 Canny Edge Detection:**


The Canny operator is an optimal edge detector [4] that uses a grayscale image as the input and produces an output
image showing the positions of edges tracked by the discontinuousness of the intensity. The Canny detector is applied
here because it satisfies three criteria: a low error rate, edge localization, and displaying one response to a single image 
The Canny detector allows the extraction of useful structural information from different angles of RBCs from the
image and reduces the amount of data to be processed


**Step 3: Hough Transform:**


The most popular method used for counting the number of Red Blood Cells is Hough Transformation technique. Red
Blood Cells are estimated and detected using this technique by determining the center point of the circle. The circular
Hough transform is then applied to detect and draw circles. The circle is described by two following equations:


**x = a +rcosθ(2)
y = b +rsinθ(3)**


where, a and b are the center of the circle in x and y direction respectively and r is the radius of circle. Parametric form
of circle can be given by the following equation:


**(x −a)2 +(y −b)2 = r2 (4)**


where a and b are the center of circle in x and y direction respectively.
Once the boundaries of red blood cells are detected, number of cells can be counted
