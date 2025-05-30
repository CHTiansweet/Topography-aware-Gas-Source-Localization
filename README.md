Gas Source Localization
=====
This is the repository of paper _Deep Learning Based Topography Aware Gas Source localization with Mobile Robots_
https://github.com/CHTiansweet/CHTian/blob/master/files/GSL_preprint.pdf
![image](https://github.com/CHTiansweet/Topography-aware-Gas-Source-Localization/blob/main/overallperformance.png)

This repository includes four parts：


Data: Tha data collected for training, one epoch means a full experiment form starting to the gas source. Normalcondintion includes epoches with stable wind direction, windchange includes epoches from evaluation epoch with changing wind driection in one epoch:  
    Map[n] is the occpuancy grid map at the time of plume encounter n  
    Wind[n] is observed wind direction at the time and location of plume encounter n, wind data is in the format of (x,q), where x is speed(m/s), q is the clockwise rotation Angle pointed by the robot(°).  
    baselink_to_map_[n], baselink_to_odom_[n], odom_to_map_[n] are coordinates transformation at the time and location of plume encounter n, indicating robot's location and pose.  
    gassource_baselink_to_map, gassource_baselink_to_odom, gassource_odom_to_map are coordinates transformation of gas source, indicating real gas source location.    
      


Train: The ipynb file for training and evaluation process, all origin code is run on colab,   
      labeler: the code used to labeling the data and generate ground truth, referring to the "loss function with dynamic detection range" part in our paper.  
      GSL_train: the main training part, including defination of dataset class  
      GSLinference: the evaluation part of model  
      resultvis: the visualization module based on the result of GSLinference  
      For detailed Notes, please refer to GSL_train   

Model: The model described in our paper, several models have slite difference  

Robotcontrol: The code used during data collection, including data filter and human-in-the-loop control  
