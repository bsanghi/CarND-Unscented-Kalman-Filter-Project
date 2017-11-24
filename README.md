# CarND-Unscented-Kalman-Filter-Project

[image1]: ./image/data_unkf.png "data1"
[image2]: ./image/data_extkf.png "data1"
[image3]: ./image/NIS.png "nis"

## The Project results

In this project, I completed unscented Kalman filter in C++ to estimate position and speed of moving object using lidar and radar measurements. 


My px, py, vx, and vy RMSE are less than the required values [.09, .10, 0.40, 0.30]. Changes are made in 
src/ukf.cpp and src/tools.cpp. The code presented here is designed to work with the Udacity term 2 simulation executable, and so cannot
 be run standalone. However, here's some example(data1) output.

![alt text][image1]

We improved upon the Extended Kalman Filter by using a non-linear model which is better prepared to deal with complex movement patterns. 
This means the RMSE is going to be lower and our predictions more accurate. please compare the above RMSEs with the following RMSE 
for the extended kalman fitter

![alt text][image2]

Using the unscented filter required to tune two parameters, the process noises standard deviations of linear and angular acceleration. 
The hardcoded variance of the random linear and yaw rate accelerations applied during the predict step. The chosen values should be 
physically reasonable. A good way to check if the noise values are physically reasonable is to use the "normalized information squared" 
or NIS statistic. 
If much more than 5% of the NIS values computed from measurements exceed the threshold, it means that our measurements are actually 
being drawn from a distribution with a greater variance than we assumed. In other words, we have underestimated the process noise, and 
should increase it.

![alt text][image3]

