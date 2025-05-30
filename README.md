# Topography-aware Gas Source Localization
=====
This is the repository of paper _Deep Learning Based Topography Aware Gas Source localization with Mobile Robots_
https://github.com/CHTiansweet/CHTian/blob/master/files/GSL_preprint.pdf
![image](https://github.com/CHTiansweet/Topography-aware-Gas-Source-Localization/blob/main/overallperformance.png)


This repository includes four parts:

---

## **1. Data**

The data collected for training. One epoch means a full experiment from starting point to the gas source.

- `normalcondition/`: contains epochs with stable wind direction  
- `windchange/`: contains epochs with changing wind direction within one epoch  

Each epoch includes the following files:

> - `Map[n]`: Occupancy grid map at the time of plume encounter *n*  
> - `Wind[n]`: Observed wind direction at the time and location of plume encounter *n*. Wind data is formatted as `(x, q)`, where:
>     - `x`: wind speed (m/s)  
>     - `q`: clockwise rotation angle (°) pointed by the robot  
> - `baselink_to_map_[n]`, `baselink_to_odom_[n]`, `odom_to_map_[n]`: Coordinate transformations at the time and location of plume encounter *n*, indicating the robot's location and pose  
> - `gassource_baselink_to_map`, `gassource_baselink_to_odom`, `gassource_odom_to_map`: Coordinate transformations of the gas source, indicating the ground-truth gas source location  

---

## **2. Train**

IPython Notebook files for training and evaluation. All original code runs on Google Colab.

- `labeler.ipynb`: Labels the data and generates ground truth (see "loss function with dynamic detection range" in our paper)  
- `GSL_train.ipynb`: Main training module, including dataset class definition  
- `GSLinference.ipynb`: Evaluation module for the model  
- `resultvis.ipynb`: Visualization module based on the output of `GSLinference`  
- For detailed notes and comments, please refer to `GSL_train.ipynb`  

---

## **3. Model**

The models described in our paper. Several versions are included with slight differences.

---

## **4. Robotcontrol**

Code used during data collection, including data filtering and human-in-the-loop control mechanisms.
