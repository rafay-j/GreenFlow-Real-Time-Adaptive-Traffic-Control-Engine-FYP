# GreenFlow-Real-Time-Adaptive-Traffic-Control-Engine
# Final Year Project
# Under Development...

## Overview
This Final Year Project focuses on improving urban traffic management by using computer vision to analyze road congestion and estimate optimal traffic signal timings.

The system uses a YOLOv8 object detection model trained on a custom dataset constructed from multiple traffic datasets and camera angle images relevant to Karachi’s urban road environment. The detected vehicles are then processed through a counting and density estimation pipeline to produce congestion metrics, which are finally used by a rule-based timing model to predict adaptive traffic signal durations.


## Problem Statement
Urban traffic congestion is a major issue in large cities such as Karachi. Traditional traffic signals operate on fixed timing schedules and do not adapt to real-time traffic conditions.

This project explores whether computer vision-based vehicle detection can be used to estimate congestion levels and dynamically adjust signal timings.


## Dataset Construction
To train a robust vehicle detection model, a custom dataset was constructed.

Steps involved:

- Filtering camera-angle images relevant to urban intersections
- Consolidating multiple publicly available traffic datasets
- Preserving and standardizing bounding box annotations across datasets
- Preparing the final dataset in YOLO format for training

The resulting dataset represents heterogeneous traffic conditions similar to those observed in Karachi.


## Model Training
The object detection model used in this project is YOLOv8.

Training involved:

- Multi-class vehicle detection including cars, buses, trucks, and motorcycles
- Training on the consolidated dataset
- Evaluating detection performance across varying traffic densities and camera angles

The trained model performs frame-level detection of vehicles in traffic footage.


## Vehicle Counting and Density Estimation
A processing pipeline was developed to convert frame-level detections into structured traffic metrics.

This pipeline:

- Counts detected vehicles per frame
- Aggregates counts across time windows
- Estimates traffic density and congestion scores

These metrics serve as the input to the signal timing model.


## Adaptive Signal Timing Model
A rule-based timing model was designed to map congestion levels to traffic signal timing predictions.

The model:

- Takes congestion scores as input
- Applies predefined rules to estimate optimal green light duration
- Outputs adaptive signal timings intended to reduce waiting time and congestion buildup


## System Architecture
The overall pipeline of the system is as follows:

Traffic Image / Video Input  
↓  
YOLOv8 Vehicle Detection  
↓  
Bounding Box Extraction  
↓  
Vehicle Counting per Frame  
↓  
Traffic Density Calculation  
↓  
Congestion Score Generation  
↓  
Adaptive Signal Timing Prediction


## Model Details

Model: YOLOv8  
Framework: Ultralytics / PyTorch  

Classes Detected:

- Car
- Bus
- Truck
- Motorcycle

Training Data:

A consolidated multi-dataset traffic image collection filtered for urban intersection viewpoints.



## Results
The trained YOLOv8 model detects multiple vehicle classes under heterogeneous traffic conditions including cars, buses, trucks, and motorcycles.

Key outputs of the system include:

- Vehicle detection bounding boxes for each frame
- Aggregated vehicle counts across time intervals
- Traffic density estimation
- Predicted green light durations based on congestion levels

Example outputs include detected vehicles in traffic frames and computed congestion metrics used for signal timing predictions.



## Technologies Used

- Python
- YOLOv8 
- OpenCV
- PyTorch
- NumPy



