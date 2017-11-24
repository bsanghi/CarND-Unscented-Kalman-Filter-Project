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
This means the RMSE is going to be lower and our predictions more accurate. please compare RMSEs for the extended kalman fitter

![alt text][image2]

Using the unscented filter required to tune two parameters, the process noises standard deviations of linear and angular acceleration. 
we calculated NIS(Normalized Innovation Squared) values and compared them with the 95% confidence of the corresponding 
Chi Square distribution. This is the result for the final tuned version of my project:

![alt text][image3]

