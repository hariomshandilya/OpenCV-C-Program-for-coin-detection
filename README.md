# OpenCV-C-Program-for-coin-detection
Things to know:  The code will only compile in Linux environment. To run in windows, please use the file: ‘coin.o’ and run it in cmd. However if it does not run(problem in system architecture) then compile it in windows by making suitable and obvious changes to the code like: Use in place of . Compile command: g++ -w coin.cpp -o coin.exe `pkg-config –libs opencv` Run command: ./coin The image containing coin/coins has to be in the same directory as the code. Before you run the code, please make sure that you have OpenCV installed on your // system.
#include "opencv2/highgui/highgui.hpp"
// highgui - an interface to video and image capturing.
#include "opencv2/imgproc/imgproc.hpp"
// imgproc - An image processing module that for linear and non-linear
 image filtering, geometrical image transformations, color space conversion and so on.
#include <iostream>
#include <stdio.h>
// The header files for performing input and output.
 
using namespace cv;
// Namespace where all the C++ OpenCV functionality resides.
using namespace std;
// For input output operations.
 
int main()
{
    Mat image;
    // Mat object is a basic image container. image is an object of Mat.
 image=imread("coin-detection.jpg",CV_LOAD_IMAGE_GRAYSCALE);
    // Take any image but make sure its in the same folder.
    // first argument denotes the image to be loaded. 
    // second argument specifies the image format as follows: 
  // CV_LOAD_IMAGE_UNCHANGED (<0) loads the image as it is.      
    // CV_LOAD_IMAGE_GRAYSCALE ( 0) loads the image in Gray scale.      
    // CV_LOAD_IMAGE_COLOR (>0) loads the image in the BGR format. 
    // If the second argument is not there, it is implied CV_LOAD_IMAGE_COLOR.
vector coin;
    // A vector data type to store the details of coins.
